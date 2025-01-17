---
title: "Making a merge request"
teaching: 10
exercises: 15
objectives:
- "Make a merge request to your friends repo"
- "Accept and merge request"
questions:
- "How do I fix someone else's code?"
keypoints:
- "You can fix someone else's code without direct edit rights to their repository"

hidden: false
---

> ## This episode assumes
>
> - You can run your code in a docker container.
> - You've forked and modified someone else's repository
> - Your changes are on a branch called `change-cuts`
{: .prereq}

This episode explains the standard ATLAS procedure for pushing changes
to code back to the original authors. Once you are comfortable with this procedure,
you will be in a position to start contributing to the ATLAS Athena code base
using the same procedure, described [here](https://atlassoftwaredocs.web.cern.ch/gittutorial/).
If you've contributed to open source projects on github the procedure should be familiar, with a few
"gitlab" specific differences.

# Pushing your changes to your fork

First let's make sure your remote repositories are set up properly:

~~~
git remote -v
~~~
{: .bash}

should print something like

~~~
origin	ssh://git@gitlab.cern.ch:7999/dguest/sam-example.git (fetch)
origin	ssh://git@gitlab.cern.ch:7999/dguest/sam-example.git (push)
~~~
{: .output}

From the part after the second to rightmost slash you can tell that:
- This is _your_ fork (`dguest/`)
- This is from your friend's example code (`sam-example`)

> ## Exercise: add another remote
>
> Try to add another remote that points to your _friend's_ repository.
>
> > ## Hint
> > you should be able to navigate to it from the "project" section
> > of the your fork on gitlab, click the little house on the upper left.
> > From there you should see the parent repo that you forked from.
> {: .solution}
{: .challenge}

Now push your code to your fork.
~~~
git push origin change-cuts
~~~
{: .bash}

git should tell you that it pushed a branch and print a URL that you
can visit to make a merge request into the parent fork. This is a
convenient shortcut but for demonstration purposes we'll set
everything up manually.

# Making a merge request

The URL for your fork will always be something like

~~~
https://gitlab.cern.ch/YOUR_USER_NAME/REPOSITORY_NAME
~~~

where `YOUR_USER_NAME` is your CERN login and `REPOSITORY_NAME` is
whatever your friend called their repository.

Go to this url and click the "merge requests" button on the left
side. Next click the big green button that says "new merge request". This will bring up a "New Merge Request" dialog.
