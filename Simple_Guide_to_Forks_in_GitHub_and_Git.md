# Simple guide to forks in GitHub and Git

**MUST READ Simple guide to forks in GitHub and Git**
http://www.dataschool.io/simple-guide-to-forks-in-github-and-git/



## Install FusionPBX on your device


## Forking and updating a Repo

**One Time**

### 1-Fork

Go to https://github.com/fusionpbx/fusionpbx and click Fork (upper right)

### 2-Clone

On your local device:

``` cd /var/www/
git clone https://github.com/TekMason/fusionpbx.git
``` 

Configure git so it doesn’t commit file permission changes

```
nano /var/www/fusionpbx/.git/config
	filemode = false
```

Set Permissions

```
chown -R www-data:www-data /var/www/fusionpbx
chmod -R 775 /var/www/fusionpbx
```

### 3-Update a File

Edit files

### 4-Commit

```
git status
git add .
git commit -m "Summary of what is in this commit "
git push
GO to your repo and do a pull request
```

Repeat steps 3 and 4

## Synching a Fork

**One time**

```
git –v
**origin  https://github.com/TekMason/fusionpbx.git (fetch)**
**origin  https://github.com/TekMason/fusionpbx.git (push)**
git remote add upstream https://github.com/fusionpbx/fusionpbx.git
git remote -v
**origin  https://github.com/TekMason/fusionpbx.git (fetch)**
**origin  https://github.com/TekMason/fusionpbx.git (push)**
upstream        https://github.com/fusionpbx/fusionpbx.git (fetch)
upstream        https://github.com/fusionpbx/fusionpbx.git (push)
```

**Repeat with each sync**

```
git fetch upstream
git merge upstream/master
git reset upstream/master
git push --force
```

