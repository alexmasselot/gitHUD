Prompt Explained
================

The prompt built by gitHUD is made of 6 parts:
* [Git Repo Indicator](#git-repo-indicator)
* [Merge branch information](#merge-branch-information)
* [Local branch](#local-branch---detached-information)
* [Commits to push-pull](#commits-to-push-pull)
* [Local repository state](#local-repository-state)
* [Stashes](stashes)

Each of these parts are described below and each of these parts are actually
optional (all "on" by default). The specific documentation of each part tells
you how to hide it if you wish to.

### When not in a git repository

The gitHUD program exists promptly and does not display anything, i.e. leaves
your prompt empty of any git-related information

## Git Repo Indicator

_Hidden by:_ `show_part_repo_indicator=False`

| Output part | Description |
|:-----------:| ----------- |
| ![repo_indicator] | This is a small prefix to the gitHUD output that indicates that you are in a git repository and that therefore gitHUD is doing some output. |

## Merge Branch information

_Hidden by:_ `show_part_merge_branch_commits_diff=False`

This section is for branches that have a remote counterpart (typically long
lived branches). It tells you the difference between your remote
tracking branch and the branch it was created from (both of which can evolve
because of you or because of your colleagues.

By default, this count does not include merge commits (that are redundant
since the count includes the commits that are on the branch being merged)

### No merge branch

When there is no remote merge branch, this section of the prompt is empty.
This is typically the case when you work on master, or when you work on a
local __short lived__ feature branch that has no remote counterpart.

| Output part | Description |
|:-----------:| ----------- |
| ![no_upstream] | This means that the current branch (other than master) has no remote tracking branch (typically a short lived feature branch) |

### Merge branch

| Output part | Description | Viz |
|:-----------:| ----------- |:---:|
| ![merge_branch_pull] | This means that the remote parent of your current remote tracking branch has some commits that will need to be merged back in your branch | ![gitgraph_merge_branch_pull] |
| ![merge_branch_push] | This means that your remote tracking branch has some commits that have not yet been merged and pushed to its parent branch | ![gitgraph_merge_branch_push] |
| ![merge_branch_push_pull] | This means that both your remote tracking branch and its parent have evolved and you'll have some merge work to do | ![gitgraph_merge_branch_push_pull] |

## Local branch - detached information

_Hidden by:_ `show_part_local_branch=False`

| Output part | Description |
|:-----------:| ----------- |
| ![local_branch] | This is the name of the local branch you are working on |
| ![detached] | This is the commit sha on which you are, if you are not at the HEAD of a branch<br>(typically on rebase situations, conflict resolution, or exploration of an old repo state) |

## Commits to push-pull

_Hidden by:_ `show_part_commits_to_origin=False`

| Output part | Description | Viz |
|:-----------:| ----------- |:--- |
| ![commits_pull] | This means that some commits on you remote tracking branch have not been pulled (rebased?) locally | ![gitgraph_commits_pull] |
| ![commits_push] | This means that some local commits have not yet been pushed to the remote tracking branch | ![gitgraph_commits_push] |
| ![commits_push_pull] | This means that some commits are to be pulled (rebased?) and some have to be pushed | ![gitgraph_commits_pull_push] |

## Local repository state

_Hidden by:_ `show_part_local_changes_state=False`

| Output part | Description |
|:-----------:| ----------- |
| ![repo_changes] | The first group is for the status of files in the index:<br><ul><li>A: New files</li><li>D: Deleted files</li><li>M: Modified files</li><li>R: Renamed Files</li></ul>The second and third groups are about local unstaged file modifications:<br><ul><li>D: Deleted files</li><li>M: Modified files</li><li>A: New Files</li></ul> |
| ![conflicts] | This indicates files in a conflicted state (typically in the middle of a merge or rebase) |

## Stashes

_Hidden by:_ `show_part_stashes=False`

| Output part | Description |
|:-----------:| ----------- |
| ![stash] | This means that there are some stashes in your repo |

[repo_indicator]: ../images/prompt_repo_indicator.png
[commits_pull]: ../images/prompt_commits_pull.png
[commits_push]: ../images/prompt_commits_push.png
[commits_push_pull]: ../images/prompt_commits_push_pull.png
[conflicts]: ../images/prompt_conflicts.png
[detached]: ../images/prompt_detached.png
[local_branch]: ../images/prompt_local_branch.png
[no_upstream]: ../images/prompt_no_upstream.png
[merge_branch_pull]: ../images/prompt_merge_branch_pull.png
[merge_branch_push]: ../images/prompt_merge_branch_push.png
[repo_changes]: ../images/prompt_repo_changes.png
[repo_indicator]: ../images/prompt_repo_indicator.png
[stash]: ../images/prompt_stash.png
[merge_branch_push_pull]: ../images/prompt_merge_branch_push_pull.png

[gitgraph_merge_branch_pull]: ../images/gitgraph_merge_branch_pull.png
[gitgraph_merge_branch_push]: ../images/gitgraph_merge_branch_push.png
[gitgraph_merge_branch_push_pull]: ../images/gitgraph_merge_branch_push_pull.png

[gitgraph_commits_pull]: ../images/gitgraph_commits_pull.png
[gitgraph_commits_push]: ../images/gitgraph_commits_push.png
[gitgraph_commits_pull_push]: ../images/gitgraph_commits_pull_push.png
