![usage](/pic/logo.jpg)
![usage](/pic/pic.png)

# BDSM (Bash Database SQL Manager)

Bash script to easily
- get DB credentials from your CMS/framework config file
- export DB,
- import DB,
- search in DB,
- search/replace in DB,
- pull database from remote server,
- and lot more. Look at the screenshot above!

# Supported engines
- WordPress
- Laravel
- Prestashop 1.6
- Prestashop 1.7
- ...

# Supported databases
- MySQL

Please request your engine by creating new issue on Github! Give me your engine's config file example and I'll add it to the script. 👍

# Installation
Fast way (in one step). Worked on Mac, Linux and Windows (terminals with bash support)
```shell
eval "$(curl "https://raw.githubusercontent.com/michaelradionov/gg_installer/master/gg_installer.sh")" && gg_installer bdsm
```
Since BDSM can install other usefull scripts, you can install ALL OF THEM simply running
```
bdsm --install-all
```

# Usage

1. `cd` in website root directory
2. Execute `bdsm`
3. Follow instructions. Enjoy! See features description below.
4. ~~💰 Donate~~. Nah! Just give this repo a star and I will appreciate it! ⭐️

## Features (options)

0. When you execute BDSM it will automatically detect you engine, check for config file and parses it to get DB credentials. Then all of that data will be stored in your current Bash session.
1. **Show credentials.** Pretty obvious, isn't it?
2. **Export DB locally.** This option will dump your database into file. If you are using Docker, then you should use option 12 before. See description below.
3. **Search in dump.** This option is responsible for searching in exported DB dump file.
4. **Search/Replace in dump.** Obviously, this option will search/replace any given data. First step will be search, then (optionally) replacement. Please keep in your mind that BDSM doesn't support RegExp for now, only simple string values.
5. **Import dump.** If BDSM successfully determined your DB credentials OR if your entered them manually (option 11), then "Import dump" option will... Guess what? It will import you dump file to database. What a surprise!
6. **Pull DB from remote server.** This is very cool feature that allows you do a bunch of stuff IN ONE RUN! What it will do is:
    1. SSH to a given remote server
    2. Check if there is a Docker container with "mysql" in its name
    3. Depending on previous step it will export DB to dump file from localhost or from Docker container
    4. SCP exported dump to you on youк local machine (depending where you launched BDSM)
    5. Delete exported dump from the remote server
7. **Delete dump.** Deletes local dump.
8. **Self-update.** You can update BDSM to the last version by this option.
9. **Install other scripts.** Convinious way to install or update:
    1. Micro Editor. GUI like editro in your terminal and alias it to "m" command. See more https://micro-editor.github.io/
    2. Hello Bash. My handy Bash prompt configurator. I use it everywhere. See more https://github.com/michaelradionov/helloBash
    3. My awesome Git aliases. See more here https://github.com/michaelradionov/aliases
    4. Other aliases for Jira, Laravel, Docker and other.
10. **Look for dump elsewhere locally.** This option will help you to point BDSM to already existing dump file.
11. **Enter credentials manually.** Manually input DB name, user and password.
12. **Choose/forget local Docker container.** In fact it means "enter Docker mode". Here you can:
    1. Let BDSM to find container with "mysql" in its name
    2. Explicitly input Docker container's name
    3. Quit Docker mode


# Requirements

- **Bash support.** Check by executing `bash --version`
- **Mysql CLI support.** Check by executing `mysql --version` and `mysqldump --version`
- **cURL CLI support.** Check by executing `curl --version`
- **Sourcing ~/.bashrc file** on session start. Check by:
    1. executing `echo 'echo "It works"' >> ~/.bashrc`
    2. then start new terminal session. If you see "It works!" then you good.
    3. Then **delete** this line from your ~/.bashrc.
- For the previous item. If you don't know where is ~/.bashrc, you should execute `cd` (without parameters), then `pwd`. Output will be your home path, it equals `~`.

If you have literally ANY trouble with installing and using script, please, create an issue in Github repo https://github.com/michaelradionov/bdsm.

# Changelog

[Changelog](https://github.com/michaelradionov/bdsm/blob/master/CHANGELOG.md)
