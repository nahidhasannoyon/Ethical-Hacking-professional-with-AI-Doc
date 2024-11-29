# Users and Privileges

In Linux (including Kali Linux), users and permissions play a key role in managing access to files and directories. This system helps ensure that only authorized users can perform certain actions, such as reading, writing, or executing files. Below is a breakdown of how users and privileges work in Linux, with commands and explanations to manage them.

## **User Privileges on Files and Folders**

Each file and directory in Linux has **permissions** that determine what actions users can perform on them. These permissions are:

* **Read (r)** – Allows the user to view the contents of the file or directory.
* **Write (w)** – Allows the user to modify the contents of the file or add/remove files in a directory.
* **Execute (x)** – Allows the user to execute the file (if it is a program or script) or access the contents of a directory.

## Permissions are granted to **three types of users**:

1. **Owner (User)**: The creator or owner of the file.
2. **Group**: Users who belong to the same group as the file's owner.
3. **Others**: All other users who are not the owner or part of the group.

## **Viewing Hidden Files**

In Linux, files that start with a dot (e.g., `.hidden_file`) are considered **hidden files**. To view these files, use the `ls` command with the `-a` option:

```bash
ls -a
```

This will list all files, including hidden ones (those starting with a dot).

## Viewing File Permissions in Linux

In Linux, each file and directory has associated permissions that define what actions can be performed by different users (owner, group, and others). To view these permissions, you can use the `ls` command with the `-l` option.

The `-l` option (long listing format) will display detailed information about files, including permissions, ownership, size, and modification date.

**Example Command to View File Permissions:**

```bash
ls -l
```

This command will show a detailed listing of files and directories in the current directory, including their permissions. The output will look something like this:

```
-rwxr-xr-x 1 user group 1234 Nov 29 12:34 file1.txt
-rw-r--r-- 1 user group 5678 Nov 28 10:20 file2.txt
```

#### **Breaking Down the Output:**

* The first part of the output (`-rwxr-xr-x`) represents the file permissions.
* The permissions are displayed in **10 characters**:
  * The **first character** represents the **file type**:
    * `-` for a regular file.
    * `d` for a directory.
    * `l` for a symbolic link.
  * The next **9 characters** represent the file permissions, grouped as **3 sets**:
    * **Owner permissions** (first 3 characters).
    * **Group permissions** (next 3 characters).
    * **Others permissions** (last 3 characters).
  * Each set consists of:
    * `r` = Read permission.
    * `w` = Write permission.
    * `x` = Execute permission.
    * `-` = No permission.

**Example Breakdown:**

```
-rwxr-xr-x 1 user group 1234 Nov 29 12:34 file1.txt
```

* **`-`**: Regular file (not a directory).
* **`rwx`**: The owner (user) has read, write, and execute permissions.
* **`r-x`**: The group has read and execute permissions, but not write.
* **`r-x`**: Others have read and execute permissions, but not write.

***

## **Viewing Permissions of Hidden Files**

Hidden files in Linux are those that start with a dot (`.`), such as `.bashrc` or `.hidden_file`. To view these files, you can use the `ls` command with both the `-a` (show all files, including hidden ones) and `-l` (long format) options:

**Example Command:**

```bash
ls -la
```

This command will list all files in the current directory, including hidden files, and display their permissions along with other details.

**Example Output:**

```
drwxr-xr-x  2 user group 4096 Nov 29 12:30 .
drwxr-xr-x 10 user group 4096 Nov 29 12:30 ..
-rw-r--r--  1 user group   56 Nov 28 10:00 .bashrc
-rw-r--r--  1 user group  132 Nov 29 12:10 .hidden_file
```

* **`.`** and **`..`** are special directories (current directory and parent directory).
* **`.bashrc`** and **`.hidden_file`** are hidden files with their respective permissions.

## **Changing File Permissions with `chmod`**

The **`chmod`** (change mode) command is used to modify the permissions of a file or directory. Permissions can be set using either symbolic mode or numeric mode.

**Using `chmod` in Symbolic Mode:**

* **`+`**: Adds a permission.
* **`-`**: Removes a permission.
* **`=`**: Sets a permission exactly.

To add read (`r`), write (`w`), and execute (`x`) permissions to a file for all users, you would run:

```bash
chmod +rwx file_name
```

This adds **read**, **write**, and **execute** permissions for the **owner**, **group**, and **others**.

## **How `chmod 777` Works**

The numeric representation of file permissions consists of three digits (each ranging from 0 to 7), where:

* **Owner permissions** are represented by the first digit.
* **Group permissions** are represented by the second digit.
* **Others permissions** are represented by the third digit.

Each permission corresponds to a number:

* **Read (r) = 4**
* **Write (w) = 2**
* **Execute (x) = 1**

So, **`chmod 777 file_name`** assigns **read**, **write**, and **execute** permissions to the file for **owner**, **group**, and **others**.

**Breakdown:**

* `7` (Owner): Read (4) + Write (2) + Execute (1) = 7
* `7` (Group): Read (4) + Write (2) + Execute (1) = 7
* `7` (Others): Read (4) + Write (2) + Execute (1) = 7

### **Permission Table**:

| Permission      | Read (r) | Write (w) | Execute (x) | Numeric Value |
| --------------- | -------- | --------- | ----------- | ------------- |
| None            | ---      | ---       | ---         | 0             |
| Execute         | ---      | ---       | x           | 1             |
| Write           | ---      | w         | ---         | 2             |
| Write+Exec      | ---      | wx        | x           | 3             |
| Read            | r        | ---       | ---         | 4             |
| Read+Exec       | rx       | ---       | x           | 5             |
| Read+Write      | rw       | ---       | ---         | 6             |
| Read+Write+Exec | rwx      | ---       | x           | 7             |

## **Add a New User**

To add a new user in Kali Linux, you can use the `useradd` command. After adding the user, you can set a password using `passwd`.

**Steps:**

1.  **Add a new user**:

    ```bash
    sudo useradd new_user
    ```
2.  **Set a password for the new user**:

    ```bash
    sudo passwd new_user
    ```
3.  **Add the user to a group (optional)**:

    ```bash
    sudo usermod -aG group_name new_user
    ```

### **Switch User**

To switch to another user account, use the **`su`** (substitute user) command or **`sudo`** to run a command as another user.

*   To switch to another user:

    ```bash
    su - username
    ```
*   To run a command as another user (using `sudo`):

    ```bash
    sudo -u username command
    ```

## **What is the `/etc/sudoers` File?**

The **`/etc/sudoers`** file is a configuration file that defines which users and groups can run which commands with `sudo` privileges. It specifies user access and permissions for executing commands as the superuser (root) or other users.

It is important to edit the **`/etc/sudoers`** file carefully. A syntax error in this file can result in users being unable to use `sudo` properly.

To edit the sudoers file safely, use the `visudo` command, which performs syntax checking before saving the changes:

```bash
sudo visudo
```

## **What is `grep` and How Does It Work?**

**`grep`** (Global Regular Expression Print) is a powerful command-line tool for searching text using patterns (regular expressions). It searches the input for lines that match a specified pattern and prints those lines.

**Basic Usage:**

```bash
grep "pattern" file_name
```

*   **Example**: Search for the word "error" in a log file:

    ```bash
    grep "error" /var/log/syslog
    ```

**Common Options:**

*   **`-i`**: Ignore case (case-insensitive search).

    ```bash
    grep -i "error" /var/log/syslog
    ```
*   **`-r`**: Search recursively in directories.

    ```bash
    grep -r "error" /home/user/logs
    ```
*   **`-v`**: Invert the match (show lines that do not match the pattern).

    ```bash
    grep -v "error" /var/log/syslog
    ```
*   **`-l`**: Show only filenames of files with matches.

    ```bash
    grep -l "error" *.log
    ```
*   **`-n`**: Show line numbers with matching lines.

    ```bash
    grep -n "error" /var/log/syslog
    ```

