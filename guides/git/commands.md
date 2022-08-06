# Git Commands

## Getting Started

You can _initialize_ a local Git repository in any folder by running the following command in the terminal:

```
git init
```

With a local Git repository created (_there's now a hidden folder called `.git`_), you can check the state of the repository by running:

```
git status
```

_This command will be your best friend when using Git_, use it whenever you want to get an idea about what's going on.

## Staging Area

If the repository saved every single file on it's own, the changelog would be a mess. Instead, the repository saves a _commit_: a _commit_ is a set of changes to the code.

Let's say you are working on a webpage, and you want to integrate a new feature to the webpage. You probably know that a single file doesn't make an entire feature, so you won't modify a file, you will modify many files!

1. To add the feature you: create, modify and delete all the files you need to, then you add those files to the _staging area_ by running:

	```
	git add <file>
	```

	- Keep in mind that if you modify the files again, the changes will not be added to the _staging area_, you have to add them again!

2. Then you commit all those changes to the repository into a single _commit_ by running:

	```
	git commit -m "<your message here>"
	```

_Ta'dah! You just did a commit!_ No matter what you do to your code now, you can always get back to this point because _you just **versioned** your code_.

- Now that you have _commits_ made to the repository, you can see them in the log by running:

	```
	git log
	```

- _Or it's compact version:_

	```
	git log --oneline
	```


### Keep in Mind
In the example about the webpage, I mentioned doing the _commit_ **after** you implemented the feature.

- This is a good example because it shows you that a _commit_ is a set of all the changes you made, not just a single file.
- In reality this isn't a best practice, you should commit your changes every time you feel like you did a meaningful change to the code.

Remember that each _commit_ is a point you can go back to. At the end of the day, you decide how often you should make a _commit_.

## Branches

Developing isn't always a sequential task, it's parallel: you go do a bit of work on one feature, then you go and do a little work on another different feature. This is **one of the reasons** you should use branches. A branch is kind of like a copy of your _working directory_ inside your repository.

You can make a new _branch_ called `new-feature` that completely destroys the webpage for the time being, then go back to the `master/main` _branch_ and the webpage will work perfectly. This is possible because each branch has it's own _commit log_ and Git will know what changed between branches, and will change your _working directory_ accordingly.

- You can list the branches of your repo by running:

	```
	git branch
	```

- You can change to a new branch by running:

	```
	git checkout -b <branch-name>
	```

- You can go back to `master/main` by running:

	```
	git checkout <branch-name>
	```

Let's say you have a main branch called `development` and a secondary branch with a new feature you made called `new-feature`. Let's also say you recently committed twice to `development`, causing `new-feature` to be 2 _commits_ behind `development`.

1. You can integrate the 2 new _commits_ from `development` to `new-feature`, such as that the new _commits_ will be added "on top" of the base but "below" the work you did in `new-feature` by running:

	```
	git checkout new-feature
	git rebase development
	```

	- You can verify that the _commits_ from `development` were added below the ones from `new-feature` by checking the log.

2. Then, if the work is ready, you can merge `new-feature` to `development` by running:

	```
	git checkout development
	git merge new-feature
	```

3. And finally, you can delete `new-feature` by running:

	```
	git branch -D new-feature
	```

## Working Directory

I started talking about the _folder_ you work with, but eventually I switched to the _working directory_. The _working directory_ is just the files and folders you are managing with Git.

You might have noticed that if you switch _branches_, files appear and disappear from the folder you are working with. That is because the different _branches_ have different _working directories_.