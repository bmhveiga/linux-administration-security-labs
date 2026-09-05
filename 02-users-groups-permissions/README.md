# 02 — Linux Users, Groups & Permissions

Hands-on Linux administration lab focused on managing users, groups, ownership, permissions, and access to files and directories.

## Objective

Practice how Linux controls access to system resources through:

- user accounts
- groups
- file ownership
- directory ownership
- read, write, and execute permissions
- administrative privileges
- shared resources

The goal was to understand how access can be granted according to a user's role without giving unnecessary privileges.

---

## Areas Practiced

- Creating and managing Linux users
- Creating and managing groups
- Adding users to groups
- Checking user and group membership
- Changing file ownership
- Changing directory ownership
- Configuring file permissions
- Configuring directory permissions
- Using `sudo`
- Troubleshooting access problems
- Applying least-privilege principles

---

## Users and Groups

Linux uses users and groups to determine who can access system resources.

Typical commands include:

~~~bash
whoami
id
groups
getent passwd
getent group
~~~

These commands help identify:

- the current user
- the user ID
- group membership
- existing users
- existing groups

---

## Creating Users

User accounts can be created and managed from the command line.

Examples:

~~~bash
sudo adduser username
sudo useradd username
sudo passwd username
~~~

The exact command used depends on the environment and administrative workflow.

---

## Managing Groups

Groups allow multiple users to share access to files, directories, and other resources.

Examples:

~~~bash
sudo groupadd groupname
sudo usermod -aG groupname username
groups username
~~~

This is useful when several users require access to the same resources without giving them broader administrative privileges.

---

## File Ownership

Linux files and directories have an owner and a group.

Ownership can be inspected with:

~~~bash
ls -l
~~~

Ownership can be changed with:

~~~bash
sudo chown username file
sudo chown username:groupname file
~~~

For directories:

~~~bash
sudo chown -R username:groupname directory/
~~~

---

## Permissions

Linux permissions are based on three main access types:

- `r` — read
- `w` — write
- `x` — execute

And three permission scopes:

~~~text
Owner
Group
Others
~~~

Example:

~~~text
-rwxr-x---
~~~

This can be interpreted as:

~~~text
Owner:  read + write + execute
Group:  read + execute
Others: no access
~~~

---

## Changing Permissions

Permissions can be modified using `chmod`.

Examples:

~~~bash
chmod 644 file.txt
chmod 755 script.sh
chmod 750 directory/
~~~

Symbolic notation can also be used:

~~~bash
chmod u+x script.sh
chmod g+w shared-file.txt
chmod o-r file.txt
~~~

---

## Shared Access

One practical use of Linux groups is allowing several users to work with the same directory.

Example structure:

~~~text
/shared/
   |
   +-- user-a
   +-- user-b
   +-- group access
~~~

Instead of giving every user unrestricted access, permissions can be assigned according to the requirements of the group.

---

## Administrative Access

Administrative commands were performed using `sudo` where required.

Example:

~~~bash
sudo command
~~~

Using `sudo` allows a normal account to perform authorized administrative actions without operating continuously as the root user.

---

## Troubleshooting Permissions

When a user cannot access a file or directory, useful checks include:

~~~bash
whoami
id
groups
ls -l
ls -ld directory/
~~~

This helps determine whether the issue is related to:

- ownership
- group membership
- file permissions
- directory permissions
- administrative privileges

---

## Access Control Model

~~~text
User
  |
  +-- Group Membership
          |
          +-- File / Directory Ownership
                    |
                    +-- Permissions
                              |
                              +-- Allowed or Denied Access
~~~

This lab reinforced that Linux access problems should be investigated systematically rather than solved by simply giving broad permissions.

---

## Security Principle

A key concept practiced in this activity was **least privilege**.

Users should receive only the access required to perform their tasks.

For example, instead of using:

~~~bash
chmod 777 file
~~~

it is better to determine:

- who actually needs access
- what type of access they need
- whether access should be assigned to the owner or a group

This results in a more controlled and secure system.

---

## Skills Demonstrated

- Linux user administration
- Linux group administration
- file ownership
- directory ownership
- permissions
- `chmod`
- `chown`
- `sudo`
- access-control troubleshooting
- least-privilege concepts
- Linux command-line administration

---

## Key Takeaway

This lab helped build a practical understanding of how Linux controls access to files and system resources.

The focus was not only on using commands such as `chmod` and `chown`, but on understanding the relationship between:

~~~text
Users
   ↓
Groups
   ↓
Ownership
   ↓
Permissions
   ↓
Access
~~~

That foundation becomes important later when configuring services, securing servers, and troubleshooting Linux systems.
