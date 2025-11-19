---
layout:
  width: default
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
---

# ⏳ Queue Setup

The queue allows your application to run time consuming tasks in the background. While setting up a queue is optional, we highly recommend enabling it whenever possible.

### Importance of queue

When a quiz is assigned to a team, a notification email is sent to each member. For large teams, this can be time-consuming and may cause “request timed out” errors if it exceeds the PHP script’s maximum execution time. There are two solutions for this.

* Increase php script execution time.
* Setting up a queue

### Increase PHP Script Execution Time

To set up a Laravel queue in production, you first need to configure a queue driver in your `.env` file, such as `redis` or `database`, by setting `QUEUE_CONNECTION=redis` (or your chosen driver). Next, ensure your queue worker is running continuously in the background to process jobs. This is typically done using a process supervisor like **Supervisor** on Linux. Create a Supervisor configuration file for your Laravel queue worker, specifying the command `php /path-to-your-project/artisan queue:work --sleep=3 --tries=3`. Then, start and enable the Supervisor service to ensure the queue worker runs automatically on system boot. Finally, monitor the worker logs regularly to catch any failed jobs and ensure smooth operation of background tasks.

### Setup Queue&#x20;

To set up a Laravel queue in production, you first need to configure a queue driver in your `.env` file, such as `redis` or `database`, by setting `QUEUE_CONNECTION=redis` (or your chosen driver). Next, ensure your queue worker is running continuously in the background to process jobs. This is typically done using a process supervisor like **Supervisor** on Linux. Create a Supervisor configuration file for your Laravel queue worker, specifying the command `php /path-to-your-project/artisan queue:work --sleep=3 --tries=3`. Then, start and enable the Supervisor service to ensure the queue worker runs automatically on system boot. Finally, monitor the worker logs regularly to catch any failed jobs and ensure smooth operation of background tasks.



1. **Choose a Queue Driver**
   * Edit your `.env` file and set `QUEUE_CONNECTION=database` (simplest for shared hosting) or `redis` if your host supports it.
2. **Run the Queue Worker**
   * On cPanel, you don’t have access to `Supervisor`, but you can use **Cron Jobs** to run the queue worker periodically.
   * In cPanel, go to **Cron Jobs** → **Add New Cron Job**.
   *   Use a command like:

       ```bash
       /usr/local/bin/php /home/username/your-project/artisan queue:work --sleep=3 --tries=3
       ```

       * Adjust the path to your PHP binary and Laravel project.
       * Set the cron to run every minute (or a frequency suitable for your needs).
3. **Monitor Failed Jobs**
   * Make sure to run `php artisan queue:failed` and `php artisan queue:retry all` occasionally, either via cron or manually.
   * You can also log outputs to a file by appending `>> /home/username/queue.log 2>&1` to the cron command.
