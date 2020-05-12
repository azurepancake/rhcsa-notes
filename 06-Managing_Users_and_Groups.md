### Understanding User Properties

* `/etc/passwd` is where users and their properties are defined
  * An example of an entry is: `student:x:1000:1000:student:/home/student:/bin/bash`
  * Each line represents a user and each property is seperated by a colon
    1. username
    1. password (`x` means see `/etc/shadow`)
    1. UID
    1. primary GID
    1. additional information
    1. home directory
    1. shell
* `/etc/shadow` contains additional user password properties
  * An example entry is: `root:password::0:99999:7:::`
  * Each line represents a user and each property is seperated by a colon
    1. username
    1. encrypted password hash
    1. number of days since 1/1/1970 that the password was set
    1. minimal amount of days the password must be used
    1. maximum amount of days the password must be used
    1. the number of days before expiration that the user will be warned
* `/etc/group` contains group properties
  * An example entry is: `wheel:x:10:tristan`
  * Each line represents a user and each property is seperated by a colon
    1. group name
    1. group password
    1. GID
    1. members

### Creating and Managing Users

* `useradd` creates user accounts
* `usermod` modifies existing user accounts
  * `-G` adds user to supplementary groups
    * `-a` appends group to current list of supplementary groups, instead of overwritting
* `userdel` deletes user accounts
  * `-r` removes home directory
* `passwd` sets specified user's password and password settings
  * `-l` locks account 
  * `-u` unlocks account
  * `-e` expires account password
  * `-x` set maximum password lifetime
  * `-S` shows status of password

### Managing User Default Settings

* `useradd -D` shows and specifies default settings for user creation
* `/etc/default/useradd` contains default user creation settings
* `/etc/login.defs` contains additional default configurations for users
  * `PASS_MAX_DAYS`
  * `PASS_MIN_DAYS`
  * `PASS_MIN_LEN`
  * `PASS_WARN_AGE`
* `/etc/skel` contains directories and configuration files to be placed in new user's home directory
* `.bash_profile` script in home directory executed upon login
* `.bash_rc` script in home directory executed upon start of new shell

### Understanding Group Membership

* Each user is a member of a primary group
  * Primary group membership is managed through `/etc/passwd`
  * The user primary group becomes group-owner of newly created files
* Addtional secondary/supplemental groups can be defined
  * Supplemental groups are managed through `/etc/groups`
* `id` can query a user to see which groups they are a member of

### Creating and Managing Groups

* `groupadd` creates a group
* `groupdel` deletes a group
* `groupmod` modifies a group
* `lid -g` lists all users that are a member of a specified group

### Managing Password Properties

* `chage` manages the below password aging properties for specified user
  * Set minimum password age
  * Set maximum password age
  * Last password age
  * Password expiration warning
  * Password inactive
  * Account expiration date
