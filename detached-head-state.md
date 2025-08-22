---
title: Detached HEAD in GitKraken Desktop
description: Learn how to safely enter, work in, and exit detached HEAD state in GitKraken Desktop. Includes recovery tips and commit preservation.
taxonomy:
    category: gitkraken-desktop
---

<kbd>Last updated: June 2025</kbd>

Detached HEAD state lets you check out any commit in GitKraken Desktop without creating a branch. This is useful for reviewing or experimenting with past changes without affecting your active branches.

***

## Check Out a Commit (Detached HEAD)

1. Right-click the commit you want to inspect.
2. Select **Checkout this commit**.

![Right-clicking a commit to checkout](/wp-content/uploads/checkout-commit-2025.png)
*Temporarily switch to a past commit without creating a new branch.*

GitKraken will mark the checked-out commit with a `HEAD` label, indicating you’ve entered detached HEAD state.

![HEAD label on commit](/wp-content/uploads/HEAD-2025.png)
*Detached HEAD is shown clearly in the commit graph.*

In this state, you can review file history, inspect diffs, or create a branch from the selected commit.


***

## Commit in Detached HEAD State

You can make changes and commit them while in this state. However, these commits won’t belong to any branch.

<figure class='figure center'>
  <img src='/wp-content/uploads/editing-detachedly-2025.png' class="help-center-img img-bordered" alt="Commit warning in detached state">
  <figcaption style="text-align: center; color: #888;">GitKraken shows a warning when you commit in detached HEAD state.</figcaption>
</figure>

To preserve your work, create a branch from the current commit:

1. Right-click the commit tagged as HEAD.
2. Select <kbd><strong>Create branch here</strong></kbd>.

<figure class='figure center'>
  <img src='/wp-content/uploads/create-branch-from-HEAD-2025.png' class="help-center-img img-bordered" alt="Create branch from detached HEAD">
  <figcaption style="text-align: center; color: #888;">Start a branch from your current detached commit to keep your changes.</figcaption>
</figure>

***

## Exit Detached HEAD State

To leave detached HEAD state, simply check out any local branch.

This will remove the `HEAD` label and discard any commits made while detached, unless they were saved to a branch.

![Discarding commits on branch checkout](/wp-content/uploads/discard-commits.gif)  
*Unbranched commits are removed when switching to another branch.*

> ⚠️ **Important:**  
> Commits made while in detached HEAD state will be lost unless you create a branch.  
> You may still be able to [recover them manually](https://help.gitkraken.com/gitkraken-desktop/detached-head-state/#recovering-lost-commits).

---

## Recover Lost Commits

If you switched branches before saving your work:

- Try clicking [**Undo**](https://support.gitkraken.com/working-with-commits/undo-and-redo/) in GitKraken if it's available.
- Or, use the CLI:  
  Run [`git reflog`](https://git-scm.com/docs/git-reflog) to find the lost commit's SHA.  
  Then restore it with [`git checkout <SHA>`](https://git-scm.com/docs/git-checkout).
