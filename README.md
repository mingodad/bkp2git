# bkp2git

A shell script to create a git repository from a set of backup files.

It comes with settings to test with the "indent" GNU project as example (please use a mirror near you).

The script will create a folder to hold the git repository and use a specific type of backup files:

```
bkp_ext=".tar.gz"
git_folder=src
```

Then it proceeds by reading an ordered list of backup files without extension:

```
indent-1.9.1
indent-1.10.0
indent-2.1.0
indent-2.1.1
indent-2.2.0
indent-2.2.1
indent-2.2.2
indent-2.2.3
indent-2.2.4
indent-2.2.5
indent-2.2.6
indent-2.2.7
indent-2.2.8
indent-2.2.9
indent-2.2.10
indent-2.2.11
indent-2.2.12
```

Then each backup file is extracted and a symbolic link is created for the ".git" folder previoulsy created,
then execute the needed git commands to add/commit the changes found.

After each backup file has been processed it's removed, except the last one to allow check the final result.

For your specific case you'll need to make some adjusts to this script, mainly the backup extension and the program to extract the contents of it.
