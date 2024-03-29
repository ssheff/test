How to create a new repository and sync to git hub

Step 1. 
Open terminal and change the current working directory to your local project.

Step 2.
List the current configured remote repository for your fork.
$ git remote -v
origin https://github.com/YOUR_USERNAME/YOUR_FORK.git (fetch)
origin https://github.com/YOUR_USERNAME/YOUR_FORK.git (push)


Step 3.
Specify a new remote upstream repository that will be synced with the fork.

$ git remote add upstream https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git

P.S. If wrong repositoiry added, it can be deleted by using:

$ git remote rm upstream
$ git remote -v

 origin https://github.com/YOUR_USERNAME/YOUR_FORK.git (fetch)
 origin https://github.com/YOUR_USERNAME/YOUR_FORK.git (push)
 upstream https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git (fetch)
 upstream https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git (push)

Step 5.
Fetch the branches and their respective commits from the upstream repository. Commits to master will be stored in a local branch, upstream/master.
 $ git fetch upstream
 
 remote: Counting objects: 75, done.
 remote: Compressing objects: 100% (53/53), done.
 remote: Total 62 (delta 27), reused 44 (delta 9)
 Unpacking objects: 100% (62/62), done.
 
 From https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY
 * [new branch] master -> upstream/master


Step 6.
Check out your fork’s local master branch.

$ git checkout master

 Switched to branch ‘master’


Step 7. Merge the changes from upstream/master into your local master branch. This brings your fork’s master branch into sync with the upstream repository, without losing your local changes.

$ git merge upstream/master

 Updating a422352..5fdff0f
 Fast-forward
 README | 9 — — — -
 README.md | 7 ++++++

 2 files changed, 7 insertions(+), 9 deletions(-)
 delete mode 100644 README
 create mode 100644 README.md


Step 8. Adding a file to a staging

$ git add README.md

P.S. If you want all files to be added

$ git commit -A


Step 9. commiting chnages

$ git commit


Step 10.

Push your changes

$ git push


