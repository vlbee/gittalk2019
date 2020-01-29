# 10 things you didn't know you could do with git (but should!)

## 1. `git log` comes in many flavours
`git log --graph`

`git log --oneline`

combine them! `git log --graph --oneline`

[Explore the git docs here](https://www.git-scm.com/docs/git-log)

## 2. take the stress out of pairing: `co-author` your commits

```
git commit -m "Refactor component.

Co-authored-by: name <name@example.com>"
```
     
## 3. stage that hunk with `git add --patch`

short version: `git add -p`

The options for each hunk:
```
y - stage this hunk
n - do not stage this hunk
q - quit; do not stage this hunk or any of the remaining ones
a - stage this hunk and all later hunks in the file
d - do not stage this hunk or any of the later hunks in the file
g - select a hunk to go to
/ - search for a hunk matching the given regex
j - leave this hunk undecided, see next undecided hunk
J - leave this hunk undecided, see next hunk
k - leave this hunk undecided, see previous undecided hunk
K - leave this hunk undecided, see previous hunk
s - split the current hunk into smaller hunks
e - manually edit the current hunk
? - print help
```

## 4. don't panic! hit undo with `git reset`

`git reset HEAD <filename> // unstages specified file from your staging index`
 
`git reset // unstages all files from your staging index`
  
## 5. `git checkout` does more than switch branches

```
git checkout master // switch to master branch
rm -f index.js // delete a file in your working tree - oops! 
git checkout index.js // restore that file from the branch index
```
```
git checkout mybranch // switch to new branch
// make some changes to index.js
// commit those changes
// think better of it and decide to undo all those changes
git checkout master index.js // restore that file from master branch
```

## 6. get to the bottom of bugs with `git bisect`

Try it out here:

https://github.com/salcode/git-bisect-example

https://salferrarello.com/how-to-use-git-bisect

## 7. expand the possibilities: understand `git rebase`

git flow options:
- Merge master into your branch
- Rebase master onto your branch 
          
## 8. keep your commit history slick with interactive rebasing

#### Before trying out interactive rebase, learn to use `git commit --amend` which lets you edit the last commit on a branch

**Warning:** *Never rebase a branch someone else has pulled and is also working on. Only safe to use in "one branch, one owner" situations*

`git rebase -i HEAD~[number]` - can go back as many commits as you like, but start small!  

```
# Commands:
# p, pick <commit> = use commit
# r, reword <commit> = use commit, but edit the commit message
# e, edit <commit> = use commit, but stop for amending
# s, squash <commit> = use commit, but meld into previous commit
# f, fixup <commit> = like "squash", but discard this commit's log message
# x, exec <command> = run command (the rest of the line) using shell
# b, break = stop here (continue rebase later with 'git rebase --continue')
# d, drop <commit> = remove commit
# l, label <label> = label current HEAD with a name
# t, reset <label> = reset HEAD to a label
# m, merge [-C <commit> | -c <commit>] <label> [# <oneline>]
# .       create a merge commit using the original merge commit's
# .       message (or the oneline, if no original merge commit was
# .       specified). Use -c <commit> to reword the commit message.
#
# These lines can be re-ordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.
#
# However, if you remove everything, the rebase will be aborted.
#
# Note that empty commits are commented out
```

## 9. don’t panic part 2! there is always `git reflog` 

eg. the `ctrl-Z` of git on your local machine


## 10. hate the command line? git travels!

just set and use your favourite IDE's GUI interface for version control

## awesome git resources

1. git cheatsheet

http://ndpsoftware.com/git-cheatsheet.html#loc=workspace;

2. Getting more from Git / Alice Bartlett / ffconf 2019

https://www.youtube.com/watch?v=FQ4IdcrOUz0&list=PLXmT1r4krsTo5KtThq4dATD_ctsV8mdJQ&index=4&t=0s
