# 🚧 Installing and Updating Tools

## "_sudo apt update && apt upgrade"_ why use && here?

The `&&` operator in a command line is used to run multiple commands sequentially, ensuring that the second command only executes if the first one is successful. Here's what happens in your example:

1. **`sudo apt update`**: This command updates the package index, fetching information about the latest versions of available packages.
2. **`&&`**: The logical AND operator checks the success of the previous command. If `sudo apt update` completes successfully (returns a 0 exit status), the next command will execute. If it fails (non-zero exit status), the subsequent command won't run.
3. **`sudo apt upgrade`**: This command upgrades the installed packages to their newest versions, based on the information fetched by `sudo apt update`.

#### Why use `&&`?

* **Safety**: It ensures that `sudo apt upgrade` is only run if `sudo apt update` completes successfully. If `apt update` fails (e.g., due to a network issue or misconfigured repository), running `apt upgrade` might not make sense.
* **Efficiency**: You avoid unnecessary errors or warnings from `apt upgrade` if the package index hasn't been updated properly.

If you used a semicolon (`;`) instead:

```bash
sudo apt update ; sudo apt upgrade
```

The second command (`sudo apt upgrade`) would run regardless of whether the first command (`sudo apt update`) succeeded or failed, which could lead to undesirable outcomes.

#### Understanding `apt install cron-daemon-common`

* The `cron-daemon-common` package is part of the `cron` utility in Linux.
* **What is `cron`?**\
  `cron` is a time-based job scheduler in Unix-like systems. It allows you to schedule tasks (scripts or commands) to run automatically at specific intervals.

#### Setting Up the Command to Run Daily

1.  **Install `cron`:** Run the following command to install `cron` and its dependencies:

    ```bash
    sudo apt install cron-daemon-common
    ```
2.  **Enable and Start the `cron` Service:**

    ```bash
    sudo systemctl enable cron
    sudo systemctl start cron
    ```
3.  **Schedule the `sudo apt update && sudo apt upgrade` Command:** Open the `crontab` editor for scheduling tasks:

    ```bash
    crontab -e
    ```

    If it’s your first time using `crontab`, it may ask you to select an editor (choose your preferred one).
4.  **Add the Daily Update and Upgrade Job:** At the bottom of the `crontab` file, add the following line:

    ```bash
    0 2 * * * sudo apt update && sudo apt upgrade -y
    ```

    * **Explanation of the syntax:**
      * `0 2 * * *` runs the command at **2:00 AM** every day.
      * `sudo apt update` updates the package list.
      * `sudo apt upgrade -y` upgrades installed packages without asking for confirmation (`-y`).
5. **Save and Exit:** After adding the line, save the file and exit the editor. The task will now run daily at the specified time.
6.  **Verify the Cron Job:** To confirm your cron job is set, run:

    ```bash
    crontab -l
    ```

#### Notes:

*   Ensure the user running this cron job has `sudo` privileges. You can avoid the need for a password prompt by editing the `sudoers` file:

    ```bash
    sudo visudo
    ```

    Add the line (replace `username` with your username):

    ```bash
    username ALL=(ALL) NOPASSWD: /usr/bin/apt
    ```

That's it! Your system will now automatically update and upgrade packages daily.

To install any software write "apt install \<package\_name>"&#x20;

To install form Git "git clone \<github\_clone\_url>&#x20;

