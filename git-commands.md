# Git Commands

Git cheatsheet

Git Cheatsheet
------------------------
Before editting any file, ensure the local repo is synchronized with the remote:

  ~~~
  git pull
  git status
  ~~~

After editting an existing file, and after testing out any changes you made,
synchronize it with the remote repo:

  ~~~
  git commit -a -m "<change description>."
  git push
  git status
  ~~~

After creating a new file, and after completing any necessary testing,synchronize
it with the remote repo:

  ~~~
  git add .
  git commit -m "<change description>."
  git push
  git status
  ~~~

If you want to keep a local backup copy of a file before changing it (for example
the "dental_servers.dat" file), and you don't want the change tracked by git, doi
this:

  ~~~
  bk dental_servers.dat
  mv dental_servers.dat.YYMMDD archive_pastebin
  vi dental_servers.dat
  ...
  git add .
  git commit -m "Adjusted server list in dental_servers.dat."
  ~~~

To delete a file that is currently being tracked in git:

  ~~~
  git rm <filename>
  ~~~

To rename a file that is currently being tracked in git:

  ~~~
  git move <filename> <new-filename>
  ~~~

<br><br>
__________
###### Markdown syntax used in this README.md file:
* [CommonMark Spec](https://spec.commonmark.org/0.30/)
* [Standard Markdown Reference](https://daringfireball.net/projects/markdown/syntax)
* [GitLab Flavored Markdown Reference](https://docs.gitlab.com/ee/user/markdown.html)

