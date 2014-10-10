# git-scripts

Just some git scripts which are quite handy

## Clean untracked files

Sometimes you end up with lots of untracked files that you really want to get 
rid of. Git features a small commandline command for that purpose called 'git clean'.

Remove all untracked files:

    git clean -f

Remove all untracked files and directories:

    git clean -f -d

more on git clean: http://git-scm.com/docs/git-clean

## Reset history to a given commit

Sometimes you may push a bad merge, in such cases going back in time to cleanup the mess if very easy. Just hard reset the remote to the commit before your merge.

**NOTE: This will break any sync options if some of your developers are already working using the broken merge!**

    git reset --hard <commit>
    git push --force

## Merge with theirs

    git merge test-development
    # Automatic merge failed, a bunch of conflicts!
    git checkout --theirs .
    git add .
    git commit

or 

    git merge -X theirs branchB

the second command might complain about some deleted files, to to fix that you do

    git rm {DELETED-FILE-NAME}

## Submodules

Work In Progress
