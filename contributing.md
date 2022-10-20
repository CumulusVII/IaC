# How to Contribute

This Guide will outline some rules for working on this project. Be sure to follow these to the best of your ability as it will ensure mistakes can be easily fixed and will prevent broken code from being accidentally merged into master. Also be sure to read through this list of [useful git commands](https://dzone.com/articles/top-20-git-commands-with-examples).

## _Rules for developing new features_

Any time you are working on new features make sure you are working on a separate branch from master. This will allow you to freely make breaking changes to the codebase without harming the rest of the project. It will also allow you to save your local changes externally in a github branch so you won't lose your work if your computer crashes.

to create a new branch use this command:

```
git checkout -b example-branch
```

Because you specified `-b` This will create a new branch called `example-branch` that is an exact copy of whatever branch you just switch from. You can make changes to this branch without fear of breaking the current working code base.

You can push your changes on your local branch to github like this:

```
git push -u origin example-branch
```

the `-u` sets origin example-branch as your remote upstream branch which means in the future you will only need to type: `git push` to push your changes to your remote branch.

## _Rules for opening Pull Requests (PRs)_

Once you have finished creating a new feature for the project you can open a PR asking for another engineer to review your work and merge it into the master branch.

To do this you want to make sure your code is up to date with the current master branch that way when you open your PR it can be merged easily without extra work on the part of the reviewer.

To make sure you code is updated switch to your local master branch and pull any new changes:

```
git checkout master
```

```
git pull
```

Now your local copy of master is updated, you can switch back to the branch you were working on

```
git checkout example-branch
```

Now you will want to merge your new branch with master:

```bash
git merge master
```

This will merge master branch with your new changes. sometimes there will be conflicts so knowing how to resolve them is a good skill to have. I would recommend watching this [video](https://www.youtube.com/watch?v=__cR7uPBOIk) as it will explain better than I can.

After any conflicts have been successfully resolved, test your changes and make sure they still work after the merge. Once everything is working you can push your branches changes to github

```
git push
```

After that go to the Repo on GitHub and open a new PR for your branch. Another ENgineer with review and either approve the changes and merge it into master or ask for you to make some additional changes before it is approved.

If additional changes are required make them on the branch you have been working on so you can push them automatically to the PR. Just let whoever was reviewing know the changes have been made.

## _Rules for Reviewing Code_

First of all be respectful of others and give criticism in a constructive manner.

To review PRs go the Pull Requests tab in the GitHub Repo make sure you review the oldest PRs first. This will ensure that all changes are added chronologically and will decrease the chances of having conflicts in the code.

> Even if GitHub says a PR can be merged automatically you should still clone the branch locally to ensure everything is working before merging it into master.

The first thing you should do is go to the changes tab on the PR and look at the files that have been changed. If there are too many conflicts, as in every file has conflicts or there have been files edited that should not be you should request changes asking them to resolve the conflicts.

If everything looks good on GitHub you should clone the branch locally and test out the changes, Every PR should have instructions for testing the new changes.

to clone the new branch enter this command in your terminal:

```
git fetch origin example-branch
```

Then you can switch to it to view the changes locally:

```
git checkout example-branch
```

Make sure you master branch is updated my following the insructions I listed earlier for updating master and then merge it into the new branch

```
git merge master
```

Resolve any conflicts in the code base and make sure everything runs as expected and the code is organized and readable make sure any unnecessary code is removed. If things are broken or the code could be improved reach out to the engineer and ask them to make some changes and resubmit their PR.

If everything looks good and all tests are passing you can push the changes up to the PR like so:

```
git push
```

then go back to GitHub, Approve the PR and merge it into the master branch. Be sure to let the engineer know that their changes have been approved.

## End

That about sums it up! Be sure to read docs and look at the README of any projects as they might be able to answer question you have. And also feel free to reach out on Slack if you need help.
