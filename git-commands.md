# Git Commands

Common Git commands.

Git Cheatsheet
------------------------
Before editing any file, ensure the local repo is synchronized with the remote:

  ~~~
  git pull
  git status
  ~~~

After editing an ***existing*** file, and after testing out any changes you made,
synchronize it with the remote repo:

  ~~~
  vi myscript.sh
  git commit -m "<Change description>." myscript.sh
  git push
  git status
  ~~~

After creating a ***new*** file, and after completing any necessary testing, synchronize
it with the remote repo:

  ~~~
  vi mynewscript.sh
  git add mynewscript.sh
  git commit -m "Initial creation." mynewscript.sh
  git push
  git status
  ~~~

If you want to keep a local backup copy of a file before changing it (for example
the "myservers.dat" file), and you don't want the change tracked by git, do
this (assumes there is an "archive_pastebin" directory and it has been added to
the .gitignore file):

  ~~~
  bk myservers.dat
  mv myservers.dat.YYMMDD archive_pastebin
  vi myservers.dat
  ...
  git add myservers.dat
  git commit -m "Adjusted server list." myservers.dat
  ~~~

To delete a file that is currently being tracked in git:

  ~~~
  git rm <filename>
  ~~~

To rename a file that is currently being tracked in git:

  ~~~
  git move <filename> <new-filename>
  ~~~

To prevent a file from be tracked by git (data files, password vaults, etc.),
append it to the .gitignore file and confirm git ignores it:

  ~~~
  # Update .gitignore file
  echo myscript.json >> .gitignore
  echo '*.xml' >> .gitignore
  # Confirm it is being ignored
  git status --ignored
  git status
  ~~~

<br><br>
__________
###### Markdown syntax used in this file:
* [CommonMark Spec](https://spec.commonmark.org/0.30/)
* [Standard Markdown Reference](https://daringfireball.net/projects/markdown/syntax)
* [GitLab Flavored Markdown Reference](https://docs.gitlab.com/ee/user/markdown.html)

