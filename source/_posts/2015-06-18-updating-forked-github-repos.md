---
title: Updating Forked Repositories on GitHub
date: 2015-06-18 11:35:00
meta:
  description: I just had to update a repo that I forked on GitHub. This is how I did it. Did I do it the correct way?
tags:
  - git
  - github
  - sculpin
---
{% block content %}
## Sculpin

People may or may not know, but this site runs on [Sculpin](https://sculpin.io/), a PHP based static site generator (this may be the first time that I've mentioned it on this site). The source code is hosted on [GitHub](https://github.com/opdavies/oliverdavies.uk), and I've listed the site on the [Community page](https://sculpin.io/community/) on the Sculpin website.

To get it there, I forked the [main sculpin.io repository](https://github.com/sculpin/sculpin.io) so that I had [my own copy](https://github.com/opdavies/sculpin.io), created a branch, made my additions and submitted a pull request. Easy enough!

## New Domain

In the last week or so, I've changed this site URL from .co.uk to just .uk, and also updated the GitHub repo URL to match, so I wanted to update the Community page to use the correct URL.

There had been commits to the main repo since my pull request was merged, I didn't want to delete my repo and fork again, and making any changes against and old codebase isn't best practice, so I wanted to merge the latest changes into my forked repo before I did anything else - just to check that I didn't break anything!

## Updating my Local Repo

I had a quick look for a *Update my fork* button or something, but couldn't see one to I added the main repository as an additional remote called `upstream` and fetched the changes.

    $ git remote add upstream https://github.com/sculpin/sculpin.io.git

    $ git fetch upstream
    remote: Counting objects: 33, done.
    remote: Total 33 (delta 6), reused 6 (delta 6), pack-reused 27
    Unpacking objects: 100% (33/33), done.
    From https://github.com/sculpin/sculpin.io
    * [new branch]      master     -> upstream/master
    * [new branch]      pr/4       -> upstream/pr/4

Now my local site knows about the upstream repo, and I could rebase the changes (`git pull upstream master` should have worked too) and push them back to origin.

    $ git rebase upstream/master
    First, rewinding head to replay your work on top of it...
    ...
    Fast-forwarded master to upstream/master.

    $ git push origin master

This seems to have worked OK - the commits are still authored by the correct people and at the correct date and time - and I went ahead and created a new feature branch and pull request based on that master branch.

<figure>
  <img src="/assets/images/blog/forked-github-repo-commits.png" alt="The commits on my master branch after rebasing">
  <figcaption>The commits on my forked master branch after rebasing and pushing. All good!</figcaption>
</figure>

<figure>
  <img src="/assets/images/blog/my-commit-to-the-rebased-branch.png" alt="The new feature branch with my additional commit.">
  <figcaption>The new feature branch with the new commit.</figcaption>
</figure>

## Is There a Better Way?

Did I miss something? Is there a recommended and/or better way to update your forked repos, maybe through the UI? Please <a href="https://twitter.com/?status=Rebasing GitHub Forks: @{{ site.twitter.name }}">send me a tweet</a> with any comments.
{% endblock %}
