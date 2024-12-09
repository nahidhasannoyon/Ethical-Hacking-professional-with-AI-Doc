# Installing and Updating Tools

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

apt install cron-daemon-common -> brief about it.&#x20;

Vai bollo je update e problem hole ai package seta solve korbe but ai package to time to time run kichu command run kore.&#x20;

To install any software write "apt install \<package\_name>"&#x20;

To install form Git "git clone \<github\_clone\_url>&#x20;

