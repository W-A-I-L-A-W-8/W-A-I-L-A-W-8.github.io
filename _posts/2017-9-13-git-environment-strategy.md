---
layout: post
title: Sketch of our GIT branch environment strategy
published: false
---

[![ENV](/images/work/git-env-strategy.jpg)]({{ site.baseurl }}/images/work/git-env-strategy.jpg)

After several rounds, we finally decided on a Git and Continuous Deployment Strategy that we'll apply to all our projects from now.

## Quick Explanation in bullets

- 3 slots as we have always maintained.  Development, Staging and Live Production.  Staging being our UAT.
- Under development we would have a number of feature branches (As many as required).
- On completion of features on feature branches a pull request would be made to development.
- Sprint release (merge) to release and deployed into staging.
- If any fixes are required at release stage and pull requests made into development and master.
- Once in master Continuous Deployment would publish into production.

## For Hotfix

 - New hotfix branch from master.
 - A pull request to master and published live.
 - Also needs merging back into development so everything is up to date. Beware of conflicts.

## Summary

We always had three slots as a smaller team but it was a very manual process and to make changes and fixes could be time consuming. With this new strategy and workflow we are able to continuously make updates with ease avoiding confusion and reducing the number of bugs experienced.
