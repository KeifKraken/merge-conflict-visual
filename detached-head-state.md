---
title: Detached HEAD in GitKraken Desktop
description: Learn how to safely enter, work in, and exit detached HEAD state in GitKraken Desktop. Includes recovery tips and commit preservation.
taxonomy:
    category: gitkraken-desktop
---

<kbd>Last updated: June 2025</kbd>

Detached HEAD state lets you check out any commit in GitKraken Desktop without creating a branch. This is useful for reviewing or experimenting with past changes without affecting your active branches.

***

## Viewing a Past Commit (Detached HEAD)

To explore a previous state of your repository without affecting branches:

1. Right-click the commit you want to inspect.
2. Choose **Checkout this commit** from the context menu.

![Right-clicking a commit to checkout](/wp-content/uploads/checkout-commit-2025.png)  
*This action checks out a specific commit directly—no new branch is created.*

Git will enter a **detached HEAD** state. You’ll see a `HEAD` label next to the selected commit.

![HEAD label on commit](/wp-content/uploads/HEAD-2025.png)  
*GitKraken highlights the current commit with a HEAD tag.*

While in this state, you can inspect the repo at that point in time. If you want to make changes or preserve work, create a branch before switching away.


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

## Leaving Detached HEAD State

To exit detached HEAD state, switch to any existing branch.

This restores your previous branch context and removes the `HEAD` marker from the commit view. Any changes made while detached will be discarded unless they were saved to a branch.

![Discarding commits on branch checkout](/wp-content/uploads/discard-commits.gif)  
*Unbranched commits disappear after switching branches.*

> ⚠️ **Warning:**  
> Commits created in detached HEAD state are not retained unless you branch from them.  
> If lost, they can sometimes be [recovered manually](https://help.gitkraken.com/gitkraken-desktop/detached-head-state/#recovering-lost-commits).

---

## Restoring Unbranched Commits

If you checked out a branch too soon:

- Use GitKraken’s [Undo](https://support.gitkraken.com/working-with-commits/undo-and-redo/) feature if it's enabled.
- Or run [`git reflog`](https://git-scm.com/docs/git-reflog) in your terminal to locate the lost commit.
- Then return to it with [`git checkout <SHA>`](https://git-scm.com/docs/git-checkout).
