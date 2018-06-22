# Rebasing

### Step 1: 

Switch to master and pull all of your changes before you make a new branch: 

* `git fetch` (read here for more info on [git fetch](https://stackoverflow.com/questions/292357/what-is-the-difference-between-git-pull-and-git-fetch))
* `git pull`

### Step 2: 

Now that master is up-to-date, you will need to create a branch to do your work in:

* `git checkout -b someBranchName`
* code code code...

### Step 3: 

Once work is complete, add and commit. It's best practice to have the latest version of master on your local before rebasing so we'll do a final fetch/pull:

* `git add _someFileName.scss && git commit -m 'I did x on y and fixed z as well'`
* `git checkout master`
* Repeat Step 1

### Step 4: 

Now we rebase. From your master branch run the following:

* `git checkout someBranchName`
* `git rebase master` (points your commit history to the base of master)
* `git checkout master`
* `git merge someBranchName`

### Step 5:

After all of that is complete and you've resolved all of your merge conflicts (if any) you are ready to push. With rebase, pull requests shouldn't be neccessary and can push directly to master from you local master branch.

* `git push`

## You made it!

![You made it gif](https://media.giphy.com/media/xUA7b5BKPR0x1ZzN5K/giphy.gif "You made it!") 

#### Here are a few resources for you to look into in case you ever get stuck using rebase:

* `git pull --rebase` - Helpful if the commits in you local master have diverged from origin/master. Should be rare since we normally do work in a branch.
* `git rebase --continue` - Run this after you've resolved any merge conflicts you've had with rebase.
* `git rebase --abort` - Abort the rebase and return to the original state.
* And of course, ask for help. 