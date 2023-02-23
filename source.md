<section id="themes">
	<h2>Themes</h2>
		<p>
			Set your presentation theme: <br>
			<!-- Hacks to swap themes after the page has loaded. Not flexible and only intended for the reveal.js demo deck. -->
                        <a href="#" onclick="document.getElementById('theme').setAttribute('href','css/theme/black.css'); return false;">Black (default)</a> -
			<a href="#" onclick="document.getElementById('theme').setAttribute('href','css/theme/white.css'); return false;">White</a> -
			<a href="#" onclick="document.getElementById('theme').setAttribute('href','css/theme/league.css'); return false;">League</a> -
			<a href="#" onclick="document.getElementById('theme').setAttribute('href','css/theme/sky.css'); return false;">Sky</a> -
			<a href="#" onclick="document.getElementById('theme').setAttribute('href','css/theme/beige.css'); return false;">Beige</a> -
			<a href="#" onclick="document.getElementById('theme').setAttribute('href','css/theme/simple.css'); return false;">Simple</a> <br>
			<a href="#" onclick="document.getElementById('theme').setAttribute('href','css/theme/serif.css'); return false;">Serif</a> -
			<a href="#" onclick="document.getElementById('theme').setAttribute('href','css/theme/blood.css'); return false;">Blood</a> -
			<a href="#" onclick="document.getElementById('theme').setAttribute('href','css/theme/night.css'); return false;">Night</a> -
			<a href="#" onclick="document.getElementById('theme').setAttribute('href','css/theme/moon.css'); return false;">Moon</a> -
			<a href="#" onclick="document.getElementById('theme').setAttribute('href','css/theme/solarized.css'); return false;">Solarized</a>
		</p>
</section>

H:

# Introduction to git

by Jean Pierre Charalambos  
[Universidad Nacional de Colombia](https://unal.edu.co/)

H:

# Index

 1. Introduction <!-- .element: class="fragment" data-fragment-index="1"-->
 2. Getting started <!-- .element: class="fragment" data-fragment-index="2"-->
 3. Git basics <!-- .element: class="fragment" data-fragment-index="3"-->
 3. Git branching <!-- .element: class="fragment" data-fragment-index="4"-->
 3. Github-based projects <!-- .element: class="fragment" data-fragment-index="5"-->
 5. References <!-- .element: class="fragment" data-fragment-index="6"-->
 6. Workshop <!-- .element: class="fragment" data-fragment-index="7"-->
 
H:

## Introduction

1. The problem
2. Version control system types
3. What's git?
4. Why use git?

V:

## Introduction: The problem

working on a project comprising _several source files_

<figure>
    <img height='350' src='fig/presentation.png' />
    <figcaption>A presentation</figcaption>
</figure>

V:

## Introduction: The problem

working on a project comprising _several source files_

<figure>
    <img height='350' src='fig/book.png' />
    <figcaption>A book</figcaption>
</figure>


V:

## Introduction: The problem

working on a project comprising _several source files_

<figure>
    <img height='350' src='fig/code.png' />
    <figcaption>Any other software</figcaption>
</figure>

V:

## Introduction: The problem

and wanna keep track of history

Why?

V:

## Introduction: The problem

To time travel...

V:

## Introduction: The problem

... in order to:

1. Go back in time and check out a previous state <!-- .element: class="fragment" data-fragment-index="1"-->
 * Recover it undoing a mistake
 * Explore it
 * Make edits starting from it (creating a _branched_ history)
2. Come back to the present <!-- .element: class="fragment" data-fragment-index="2"-->
 * _merge_ other _branches_ 
 * (or do it the other way around)
 
V:

## Introduction: The problem

Conclusion

'Creativity' (as when writting a book, coding a program) is:
 > a non-linear iterative process of experimentation towards *an open goal*<sup>*</sup>

<sup>*</sup> no matter how you do it, a goal that can anytime be _revised_ and/or broken up into _accomplishable stages_

V:

## Introduction: VCS types

<figure>
    <img height='400' src='fig/local.png' />
    <figcaption><a href="https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control#Local-Version-Control-Systems">Local Version Control Systems</a></figcaption>
</figure>

V:

## Introduction: VCS types

<figure>
    <img height='400' src='fig/centralized.png' />
    <figcaption><a href="https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control#Centralized-Version-Control-Systems">centralized Version Control Systems</a></figcaption>
</figure>

N:

Disadvantages:
1. Remote nature of versioning commands
2. Data corruption

V:

## Introduction: VCS types

<figure>
    <img height='400' src='fig/distributed.png' />
    <figcaption><a href="https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control#Distributed-Version-Control-Systems">Distributed Version Control Systems</a></figcaption>
</figure>


V:

## Introduction: What is git

> Git is a [free and open source](https://git-scm.com/about/free-and-open-source) [distributed](https://en.wikipedia.org/wiki/Distributed_revision_control) [version control system](https://en.wikipedia.org/wiki/Revision_control) designed to handle everything from small to very large projects with speed and efficiency.

V:

## Introduction: What is git

```git``` is British English slang meaning "unpleasant person"

> I'm an egotistical bastard, and I name all my projects after myself. First 'Linux', now 'git' -- Torvalds
<!-- .element: class="fragment" data-fragment-index="1"-->

V:

## Introduction: Why use git?

1. Private creativity affairs
2. Team creativity affairs

V:

## Introduction: Why use git?
### Private creativity affairs

To safely keep track of some project sources sequence of _commits_ (previous explicitly recorded states)

V:

## Introduction: Why use git?
### Team creativity affairs

<figure>
    <img height='380' src='fig/svn_workflow.png' />
    <figcaption><a href="https://git-scm.com/about/distributed">Subversion-Style Workflow</a></figcaption>
</figure>

N:

Works like subversion

V:

## Introduction: Why use git?
### Team creativity affairs

<figure>
    <img height='380' src='fig/manager_workflow.png' />
    <figcaption><a href="https://git-scm.com/about/distributed">Integration Manager Workflow</a></figcaption>
</figure>

N:

1. The project maintainer pushes to their public repository
1. A contributor clones that repository and makes changes
1. The contributor pushes to their own public copy
1. The contributor sends the maintainer an email asking them to pull changes
1. The maintainer adds the contributor’s repo as a remote and merges locally
1. The maintainer pushes merged changes to the main repository

V:

## Introduction: Why use git?
### Team creativity affairs

<figure>
    <img height='380' src='fig/dictator_workflow.png' />
    <figcaption><a href="https://git-scm.com/about/distributed">Dictator and Lieutenants Workflow</a></figcaption>
</figure>

N:

1. Regular developers work on their topic branch and rebase their work on top of master. The master branch is that of the reference directory to which the dictator pushes
1. Lieutenants merge the developers' topic branches into their master branch
1. The dictator merges the lieutenants' master branches into their master branch
1. The dictator pushes their master to the reference repository so the other developers can rebase on it

V:

## Introduction: Why use git?
### Team creativity affairs

<figure>
    <img height='260' src='fig/pullrequest.png' />
    <figcaption><a href="https://help.github.com/articles/using-pull-requests/">Pull requests</a></figcaption>
</figure>

H:

## Getting started

1. Recorded history
2. File states
3. First time setup
4. Getting help

V:

## Getting started: Recorded history

<figure>
    <img height='400' src='fig/history.png' />
    <figcaption><a href="https://git-scm.com/book/en/v2/Getting-Started-Git-Basics">Sequence of snapshots</a></figcaption>
</figure>

V:

## Getting started: File states

A file may be in one out of three 'states':

<li class="fragment"> _Committed_ -> safely stored in your local database
<li class="fragment"> _Modified_ -> changed but not yet committed
<li class="fragment"> _Staged_ -> prepared to go into your next commit

V:

## Getting started: File states

<figure>
    <img height='400' src='fig/areas.png' />
    <figcaption><a href="https://git-scm.com/book/en/v2/Getting-Started-Git-Basics">Git project sections</a></figcaption>
</figure>

V:

## Getting started: [first time setup](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)

<li class="fragment"> User name and email:

```sh
$ git config --global user.name Falcao
$ git config --global user.email falcao@gmail.com
```

<li class="fragment"> much more like _editor_, _diff tool_, ...

<li class="fragment"> check it:

```sh
$ git config --list
```

V:

## Getting started: Getting help

```sh
$ git help <command>
```

H:

## Git basics

1. Getting a repository
2. Recording changes
3. Viewing the history
4. Undoing things
5. Working with remotes

V:

## Git basics: Getting a repository

<li class="fragment"> [Init](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository#Initializing-a-Repository-in-an-Existing-Directory)
```sh
$ git init
```

<li class="fragment"> Add and commit some files
```sh
$ git add *.md
$ git add fig/
$ git commit -m 'initial project version'
```

V:

## Git basics: Getting a repository

From now on, I will be referring to the presentation itself git [source code repository](https://github.com/objetos/git.git)

<li class="fragment"> [Cloning an existing repository](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository#Cloning-an-Existing-Repository)
```sh
$ git clone https://github.com/objetos/git.git
```
<li class="fragment"> or using a different name:
```sh
$ git clone https://github.com/objetos/git.git git_slides
```

V:

## Git basics: Recording changes

<figure>
    <img height='400' src='fig/lifecycle.png' />
    <figcaption>The lifecycle of the status of your files</figcaption>
</figure>

V:

## Git basics: Recording changes

[Checking the status of your files](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository#Checking-the-Status-of-Your-Files)

```sh
$ git status

On branch gh-pages
Your branch is up-to-date with 'origin/gh-pages'.
nothing to commit, working directory clean
```

V:

## Git basics: Recording changes

[Checking the status of your files](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository#Checking-the-Status-of-Your-Files)

Suppose you edit the ```source.md``` file:


```sh
$ git status
On branch gh-pages
Your branch is up-to-date with 'origin/gh-pages'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   source.md

no changes added to commit (use "git add" and/or "git commit -a")
```

V:

## Git basics: Recording changes

[Viewing your staged and unstaged changes](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository#Viewing-Your-Staged-and-Unstaged-Changes)

To see what you've changed but not yet staged:

```sh
$ git diff
diff --git a/source.md b/source.md
index 02dd0b3..5891ca3 100644
--- a/source.md
+++ b/source.md
...
```

V:

## Git basics: Recording changes

[Viewing your staged and unstaged changes](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository#Viewing-Your-Staged-and-Unstaged-Changes)

To see what you've _staged_ that will go into your next commit

```sh
$ git diff --staged 

```

V:

## Git basics: Recording changes

[Checking the status of your files](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository#Checking-the-Status-of-Your-Files)

Suppose you create a ```fig/lifecycle.png``` file:


```sh
$ git status

On branch gh-pages
Your branch is up-to-date with 'origin/gh-pages'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   source.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        fig/lifecycle.png

no changes added to commit (use "git add" and/or "git commit -a")
```

V:

## Git basics: Recording changes

[Tracking new files](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository#Tracking-New-Files)

```sh
git add fig/lifecycle.png
```

```sh
$ git status
On branch gh-pages
Your branch is up-to-date with 'origin/gh-pages'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   fig/lifecycle.png

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   source.md
```
<!-- .element: class="fragment" data-fragment-index="1"-->

V:

## Git basics: Recording changes

[Commiting your changes](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository#Committing-Your-Changes)

```sh
$ git commit -m 'life-cycle figure added'
[gh-pages fa1ffed] life-cycle figure added
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 fig/lifecycle.png
```

```sh
$ git status
On branch gh-pages
Your branch is ahead of 'origin/gh-pages' by 1 commit.
  (use "git push" to publish your local commits)
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   source.md

no changes added to commit (use "git add" and/or "git commit -a")
```
<!-- .element: class="fragment" data-fragment-index="1"-->

V:

## Git basics: Recording changes

[Skipping the stagging area](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository#Skipping-the-Staging-Area)

Instead of:
```sh
$ git add source.md
$ git commit -m 'source update'
```
you can do:

```sh
$ git commit -am 'source update'
```
<!-- .element: class="fragment" data-fragment-index="1"-->


```sh
$ git status
On branch gh-pages
Your branch is ahead of 'origin/gh-pages' by 2 commits.
  (use "git push" to publish your local commits)
nothing to commit, working directory clean
```
<!-- .element: class="fragment" data-fragment-index="2"-->

V:

## Git basics: Recording changes

[Skipping the stagging area](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository#Skipping-the-Staging-Area)

Adding the ```-a``` option to the ```git commit``` command makes Git automatically stage every file that is already tracked before doing the commit

V:

## Git basics: Recording changes

[Removing files](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository#Removing-Files)


```sh
$ rm PROJECTS.md
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes not staged for commit:
  (use "git add/rm ..." to update what will be committed)
  (use "git checkout -- ..." to discard changes in working directory)

        deleted:    PROJECTS.md

no changes added to commit (use "git add" and/or "git commit -a")
```

V:

## Git basics: Recording changes

[Removing files](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository#Removing-Files)

Remove it from your staging area and then commit (```git rm```)

```sh
$ git rm PROJECTS.md
rm 'PROJECTS.md'
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD ..." to unstage)

    deleted:    PROJECTS.md
```

V:

## Git basics: Recording changes

[Moving files](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository#Moving-Files)

```sh
$ git mv file_from file_to
```

```sh
$ git mv README.md README
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD ..." to unstage)

    renamed:    README.md -> README
```
<!-- .element: class="fragment" data-fragment-index="1"-->

```sh
$ mv README.md README
$ git rm README.md
$ git add README
```
<!-- .element: class="fragment" data-fragment-index="2"-->

V:

## Git basics: Viewing the history

```sh
$ git log
commit b6545c874fdc622ecc35d28747cd2f7a0be268f2
Author: Jean Pierre Charalambos <nakednous@gmail.com>
Date:   Fri Aug 28 11:28:14 2015 -0500

    source update

commit fa1ffed1052dd9a0dc26b5211aadd0b93fdfb7c7
Author: Jean Pierre Charalambos <nakednous@gmail.com>
Date:   Fri Aug 28 11:19:28 2015 -0500

    life-cycle figure added

commit 4e65f72a195de0322fe943ed561a6e826d4b7991
Author: Jean Pierre Charalambos <nakednous@gmail.com>
Date:   Thu Aug 27 19:24:56 2015 -0500

    intro and getting started sections completed
```

V:

## Git basics: Viewing the history

```sh
git log --stat
commit b6545c874fdc622ecc35d28747cd2f7a0be268f2
Author: Jean Pierre Charalambos <nakednous@gmail.com>
Date:   Fri Aug 28 11:28:14 2015 -0500

    source update

 source.md | 195 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++-
 1 file changed, 194 insertions(+), 1 deletion(-)

commit fa1ffed1052dd9a0dc26b5211aadd0b93fdfb7c7
Author: Jean Pierre Charalambos <nakednous@gmail.com>
Date:   Fri Aug 28 11:19:28 2015 -0500

    life-cycle figure added

 fig/lifecycle.png | Bin 0 -> 95510 bytes
 1 file changed, 0 insertions(+), 0 deletions(-)
```

V:

## Git basics: Viewing the history

```sh
$ git log --pretty=oneline
6545c874fdc622ecc35d28747cd2f7a0be268f2 source update
fa1ffed1052dd9a0dc26b5211aadd0b93fdfb7c7 life-cycle figure added
4e65f72a195de0322fe943ed561a6e826d4b7991 intro and getting started sections completed
```

V:

## Git basics: Viewing the history

```sh
git log --pretty=format:"%h - %an, %ar : %s"
b6545c8 - Jean Pierre Charalambos, 5 hours ago : source update
fa1ffed - Jean Pierre Charalambos, 5 hours ago : life-cycle figure added
4e65f72 - Jean Pierre Charalambos, 21 hours ago : intro and getting started sections completed

```

V:

## Git basics: Viewing the history

Useful options for ```git log --pretty=format```

| Option | Description output                              |
|--------|-------------------------------------------------|
| %H     | Commit hash                                     |
| %h     | Abbreviated commit hash                         |
| %T     | Tree hash                                       |
| %t     | Abbreviated tree hash                           |
| %P     | Parent hashes                                   |


V:

## Git basics: Viewing the history

Useful options for ```git log --pretty=format```

| Option | Description output                              |
|--------|-------------------------------------------------|
| %p     | Abbreviated parent hashes                       |
| %an    | Author name                                     |
| %ae    | Author email                                    |
| %ad    | Author date (format respects the --date=option) |
| %ar    | Author date, relative                           |

V:

## Git basics: Viewing the history

Useful options for ```git log --pretty=format```

| Option | Description output                              |
|--------|-------------------------------------------------|
| %cn    | Committer name                                  |
| %ce    | Committer email                                 |
| %cd    | Committer date                                  |
| %cr    | Committer date, relative                        |
| %s     | Subject                                         |

V:

## Git basics: Viewing the history

```sh
$ git log --pretty=format:"%h %s" --graph
* b6545c8 source update
* fa1ffed life-cycle figure added
* 4e65f72 intro and getting started sections completed
* 0c12be1 credits
* 72cbdb0 readme update
* 005edd9 readme update
* 83d5c80 adding figs
* 7639103 source update
*   9120f43 Merge branch 'master' of https://github.com/hakimel/reveal.js into gh-pages
|\  
| * b390e66 add bower json #1067
| *   96bef35 Merge pull request #1287 from obilodeau/patch-1
| |\  
| | * 98bdeae README: suggest decktape as an alternative for PDF rendering
| |/  
| *   7225d84 Merge pull request #1260 from pierreozoux/master
| |\
```

V:

## Git basics: Viewing the history

Common options to git log

| Option          | Description                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------|
| -p              | Show the patch introduced with each commit                                                                                         |
| --stat          | Show statistics for files modified in each commit                                                                                  |
| --shortstat     | Display only the changed/insertions/deletions line from the --stat command                                                         |
| --name-only     | Show the list of files modified after the commit information                                                                       |
| --name-status   | Show the list of files affected with added/modified/deleted information as well                                                    |

V:

## Git basics: Viewing the history

Common options to git log

| Option          | Description                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------|
| --abbrev-commit | Show only the first few characters of the SHA-1 checksum instead of all 40                                                         |
| --relative-date | Display the date in a relative format (for example, 2 weeks ago) instead of using the full date format                             |
| --graph         | Display an ASCII graph of the branch and merge history beside the log output                                                       |
| --pretty        | Show commits in an alternate format. Options include oneline, short, full, fuller, and format (where you specify your own format)  |

V:

## Git basics: Viewing the history

```sh
$ git log --since=10.hours
commit b6545c874fdc622ecc35d28747cd2f7a0be268f2
Author: Jean Pierre Charalambos <nakednous@gmail.com>
Date:   Fri Aug 28 11:28:14 2015 -0500

    source update

commit fa1ffed1052dd9a0dc26b5211aadd0b93fdfb7c7
Author: Jean Pierre Charalambos <nakednous@gmail.com>
Date:   Fri Aug 28 11:19:28 2015 -0500

    life-cycle figure added
```

V:

## Git basics: Viewing the history

Options to limit the output of git log

| Option            | Description                                                                  |
|-------------------|------------------------------------------------------------------------------|
| -(n)              | Show only the last n commits                                                 |
| --since, --after  | Limit the commits to those made after the specified date                     |
| --until, --before | Limit the commits to those made before the specified date                    |

V:

## Git basics: Viewing the history

Options to limit the output of git log

| Option            | Description                                                                  |
|-------------------|------------------------------------------------------------------------------|
| --author          | Only show commits in which the author entry matches the specified string     |
| --committer       | Only show commits in which the committer entry matches the specified string  |
| --grep            | Only show commits with a commit message containing the string                |
| -S                | Only show commits adding or removing code matching the string                |

V:

## Git basics: Undoing things

To change the commit message:

```sh
$ git commit --amend
```

To add a missing file:
```sh
$ git commit -m 'initial commit'
$ git add forgotten_file
$ git commit --amend
```
<!-- .element: class="fragment" data-fragment-index="1"-->

V:

## Git basics: Undoing things

[Unstaging a Staged File](https://git-scm.com/book/en/v2/Git-Basics-Undoing-Things#Unstaging-a-Staged-File)

```sh
$ git add source.md
```

```sh
$ git status
On branch gh-pages
Your branch is up-to-date with 'origin/gh-pages'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   source.md
```
<!-- .element: class="fragment" data-fragment-index="1"-->

```sh
$ git reset HEAD source.md
Unstaged changes after reset:
M       source.md
```
<!-- .element: class="fragment" data-fragment-index="2"-->

V:

## Git basics: Undoing things

[Unstaging a Staged File](https://git-scm.com/book/en/v2/Git-Basics-Undoing-Things#Unstaging-a-Staged-File)

```sh
$ git status
On branch gh-pages
Your branch is up-to-date with 'origin/gh-pages'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   source.md

no changes added to commit (use "git add" and/or "git commit -a")
```

V:

## Git basics: Undoing things

[Unmodifying a Modified File](https://git-scm.com/book/en/v2/Git-Basics-Undoing-Things#Unmodifying-a-Modified-File)

Previously we got:
```sh
On branch gh-pages
Your branch is up-to-date with 'origin/gh-pages'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   source.md

no changes added to commit (use "git add" and/or "git commit -a")
```

V:

## Git basics: Undoing things

[Unmodifying a Modified File](https://git-scm.com/book/en/v2/Git-Basics-Undoing-Things#Unmodifying-a-Modified-File)

```sh
git checkout -- source.md
```
<!-- .element: class="fragment" data-fragment-index="1"-->

```sh
On branch gh-pages
Your branch is up-to-date with 'origin/gh-pages'.
nothing to commit, working directory clean
```
<!-- .element: class="fragment" data-fragment-index="2"-->

V:

## Git basics: Undoing things

*As a rule of thumb:* everything you commited can _almost_ always be recovered.
```git checkout -- [file]``` is thus a _dangerous_ command

V:

## Git basics: Remotes

[Showing Your Remotes](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes#Showing-Your-Remotes)

```sh
$ git clone https://github.com/objetos/git.git
```

```sh
$ git remote
origin
```
<!-- .element: class="fragment" data-fragment-index="1"-->

```sh
$ git remote -v
origin  https://github.com/objetos/git.git (fetch)
origin  https://github.com/objetos/git.git (push)
```
<!-- .element: class="fragment" data-fragment-index="2"-->

V:

## Git basics: Remotes

[Adding Remote Repositories](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes#Adding-Remote-Repositories)

```git remote add [shortname] [url]```

```sh
$ git remote add reveal https://github.com/hakimel/reveal.js.git
```
<!-- .element: class="fragment" data-fragment-index="1"-->

```sh
$ git remote -v
origin  https://github.com/objetos/git.git (fetch)
origin  https://github.com/objetos/git.git (push)
reveal  https://github.com/hakimel/reveal.js.git (fetch)
reveal  https://github.com/hakimel/reveal.js.git (push)
```
<!-- .element: class="fragment" data-fragment-index="2"-->

V:

## Git basics: Remotes

[Fetching and Pulling from Your Remotes](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes#Fetching-and-Pulling-from-Your-Remotes)

```sh
$ git fetch reveal
remote: Counting objects: 286, done.
remote: Total 286 (delta 118), reused 118 (delta 118), pack-reused 168
Receiving objects: 100% (286/286), 241.13 KiB | 348.00 KiB/s, done.
Resolving deltas: 100% (157/157), completed with 55 local objects.
From https://github.com/hakimel/reveal.js
 * [new branch]      dev        -> reveal/dev
 * [new branch]      embed      -> reveal/embed
 * [new branch]      flexbox    -> reveal/flexbox
 * [new branch]      gh-pages   -> reveal/gh-pages
 * [new branch]      master     -> reveal/master
 * [new tag]         0.3.0      -> 0.3.0
 * [new tag]         1.0.0      -> 1.0.0
 * [new tag]         1.1.0      -> 1.1.0
 * [new tag]         1.2.0      -> 1.2.0
```

V:

## Git basics: Remotes

[Fetching and Pulling from Your Remotes](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes#Fetching-and-Pulling-from-Your-Remotes)

```sh
$ git checkout reveal/master
Note: checking out 'reveal/master'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by performing another checkout.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -b with the checkout command again. Example:

  git checkout -b <new-branch-name>

HEAD is now at b390e66... add bower json #1067
```

```sh
$ git checkout master
Previous HEAD position was b390e66... add bower json #1067
Switched to branch 'master'`sh

```
<!-- .element: class="fragment" data-fragment-index="1"-->

V:

## Git basics: Remotes

[Pushing to Your Remotes](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes#Pushing-to-Your-Remotes)

```git push [remote-name] [branch-name]```

```sh
$ git push origin gh-pages
Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 6.54 KiB | 0 bytes/s, done.
Total 3 (delta 1), reused 0 (delta 0)
To https://github.com/objetos/git.git
   b6545c8..d203838  gh-pages -> gh-pages
```
<!-- .element: class="fragment" data-fragment-index="1"-->

V:

## Git basics: Remotes

[Inspecting a Remote](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes#Inspecting-a-Remote)

```git remote show [remote-name]```

```sh
$ git remote show origin
* remote origin
  Fetch URL: https://github.com/objetos/git.git
  Push  URL: https://github.com/objetos/git.git
  HEAD branch: master
  Remote branches:
    gh-pages tracked
    master   tracked
  Local branches configured for 'git pull':
    gh-pages merges with remote gh-pages
    master   merges with remote master
  Local refs configured for 'git push':
    gh-pages pushes to gh-pages (up to date)
    master   pushes to master   (up to date)
```
<!-- .element: class="fragment" data-fragment-index="1"-->

V:

## Git basics: Remotes

[Removing and Renaming Remotes](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes#Removing-and-Renaming-Remotes)

```git remote rename```

```sh
$ git remote rename reveal rv
```
<!-- .element: class="fragment" data-fragment-index="1"-->

```sh
$ git remote
origin
rv
```
<!-- .element: class="fragment" data-fragment-index="2"-->

V:

## Git basics: Remotes

[Removing and Renaming Remotes](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes#Removing-and-Renaming-Remotes)

```git remote rm```

```sh
$ git remote rm rv
```
<!-- .element: class="fragment" data-fragment-index="1"-->

```sh
$ git remote
origin
```
<!-- .element: class="fragment" data-fragment-index="2"-->


H:

## Git branching

1. [Basic Branching](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)
1. [Basic Merging](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)

V:

## Git branching: Intro

> Working on this presentation

1. *Create a branch* _struct_
1. Do some work in that branch

V:

## Git branching: Intro

> Working on this presentation

At this stage, you’d like to fix the formatting. You’ll do the following:

1. Switch to your production branch
1. Create a branch to do the _formatting_
1. After it’s tested, *merge* the _formatting_ branch
1. Switch back to _struct_ story and continue working

V:

## Git branching: Basic Branching

> Create the _struct_ branch

```sh
$ git checkout -b struct
```
<!-- .element: class="fragment" data-fragment-index="1"-->

```sh
$ git status
On branch struct
nothing to commit, working tree clean
```
<!-- .element: class="fragment" data-fragment-index="2"-->

V: 

## Git branching: Basic Branching

> Do some work in the _struct_ branch

```sh
$ git checkout status
On branch struct
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   source.md
```

V:

## Git branching: Basic Branching

> Create the _formatting_ branch

... but first finish work on _struct_ branch

```sh
$ git checkout gh-pages 
error: Your local changes to the following files would be overwritten by checkout:
        source.md
Please commit your changes or stash them before you switch branches.
Aborting
```
<!-- .element: class="fragment" data-fragment-index="1"-->

```sh
$ git commit -am'more updated'
[struct 798cdbe] more updated
 1 file changed, 51 insertions(+), 5 deletions(-)
```
<!-- .element: class="fragment" data-fragment-index="2"-->

V:

## Git branching: Basic Branching

> Create the _formatting_ branch

```sh
$ git checkout gh-pages 
Switched to branch 'gh-pages'
Your branch is up-to-date with 'origin/gh-pages'.
```
<!-- .element: class="fragment" data-fragment-index="1"-->

```sh
$ git checkout -b formatting
```
<!-- .element: class="fragment" data-fragment-index="2"-->

V: 

## Git branching: Basic Branching

> Do some work in the _formatting_ branch

```sh
$ git checkout status
On branch formatting
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   source.md
```
<!-- .element: class="fragment" data-fragment-index="1"-->

```sh
$ git commit -am'formatting done'
[formatting 587456f] formatting done
 1 file changed, 68 insertions(+), 28 deletions(-)
```
<!-- .element: class="fragment" data-fragment-index="2"-->

V: 

## Git branching: Basic Merging

> Merge the _formatting_ branch onto the _gh-pages_

```sh
$ git checkout gh-pages
Switched to branch 'gh-pages'
```
<!-- .element: class="fragment" data-fragment-index="1"-->

```sh
$ git merge formatting 
Updating b6b37b5..587456f
Fast-forward
 source.md | 96 ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++----------------------------
 1 file changed, 68 insertions(+), 28 deletions(-)
```
<!-- .element: class="fragment" data-fragment-index="2"-->

V: 

## Git branching: Basic Merging

> Merge the _struct_ branch onto the _gh-pages_

finish the work in the struct branch first...

```sh
$ git checkout struct
Switched to branch 'struct'
```
<!-- .element: class="fragment" data-fragment-index="1"-->

```sh
$ git commit -am'dev workflows notes'
[struct 1a13f5a] dev workflows notes
 1 file changed, 72 insertions(+), 17 deletions(-)
```
<!-- .element: class="fragment" data-fragment-index="2"-->

V: 

## Git branching: Basic Merging

> Merge the _struct_ branch onto the _gh-pages_

... now merge

```sh
$ git checkout gh-pages 
Switched to branch 'gh-pages'
Your branch is ahead of 'origin/gh-pages' by 1 commit.
  (use "git push" to publish your local commits)
```
<!-- .element: class="fragment" data-fragment-index="1"-->

```sh
$ git merge struct 
Auto-merging source.md
Merge made by the 'recursive' strategy.
 source.md | 189 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++----
 1 file changed, 185 insertions(+), 4 deletions(-)
```
<!-- .element: class="fragment" data-fragment-index="2"-->

V: 

## Git branching: Basic Merging

final result

```sh
$ git log --graph --pretty=oneline
* 7bd70d280d32fcdde1490aac8a57bbd33fac3d76 more updates
*   f70757509b3aa4d5d3e5e5cb4ade636461c4ca11 Merge branch 'struct' into gh-pages
|\  
| * b35c44b4e739801041bb372b60ca7341511a6d5a dev workflows notes
| * 1a13f5a34929e1a3ba10772bd3aea327e1eb5f9f dev workflows notes
| * 5cedde5d9995b11f40007adb6d29b11d564b816c more updated
| * 798cdbe61f66bb3b1807a97168211ab5e2b89098 more updated
| * b3874fa1e8fae62647265bcc76b7f6ee613b15de contents added to the new branch
* | 587456f1b4d7817cfac4c8c7319cfb6cf30c78eb formatting done
|/  
* b6b37b560dc39664bee74b60a6f6a63bc538e44a index and source updated to latest reveal
```

H:

## Github-based projects

<li class="fragment"> [Classroom](https://classroom.github.com/videos)
<li class="fragment"> [Github pages](https://pages.github.com/), see also [Top Open-Source Static Site Generators](https://www.staticgen.com/)
<li class="fragment"> [Gollum](https://github.com/gollum/gollum)
<li class="fragment"> [Gitbook](https://www.gitbook.com/)
<li class="fragment"> [electricbook](http://electricbook.works/)

N:

Pending: [third party hosted option](https://git.wiki.kernel.org/index.php/GitHosting)

H:

## References

* [Git site](http://git-scm.com/)
* [Pro Git book](https://git-scm.com/book/en/v2) by Scott Chacon and Ben Straub and published by Apress, where most of the material found on this presentation has been hacked (when not noticed otherwise)
* [Git reference](http://gitref.org/) quick most-used command reference
* [Git tips & tricks](http://gitready.com/)
* [Try Git online](https://try.github.io/levels/1/challenges/1)
* [Further Git references](https://help.github.com/articles/good-resources-for-learning-git-and-github/)
 
H:

### Workshop

* (level 1) <!-- .element: class="fragment" data-fragment-index="1"-->
 1. Create a local Git repo to track some source files
 1. Create the program of your choice
 2. Begin to track your program source files with Git
 1. Commit some changes
 1. Use ```git tool``` and/or ```git difftool``` to study some changes
* (level 2) <!-- .element: class="fragment" data-fragment-index="2"-->
 2. Create a branch to test an experimental feature
 3. Merge your ```test branch``` into your ```master branch```
* (level 3) <!-- .element: class="fragment" data-fragment-index="3"-->
 1. Find _new_ usages for ```git commands```
 1. Search for git-based projects such as [Github pages](https://pages.github.com/)
 
N:

Pending themes: [Git on the server](https://git-scm.com/book/en/v2/Git-on-the-Server-The-Protocols)
