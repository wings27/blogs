It seems that I am not the only one that thinks the git commands are poorly designed.[^1] To make things worse, git has a human-unreadable documentation as well.[^2]

But despite of the steep learning curve, the powerful and magical features of git make all the efforts worth it. :) 

However, everyone makes mistakes: It's not rare, especially for beginners, to leave a mess in the workspace after running a God-knows-what-it-means git command. Therefore I summarized several "reverse operations" for a few commonly used git commands, to (hopefully) save you from clueless.

<!-- MarkdownTOC -->

- [Undo a Git Command](#undo-a-git-command)
	- [Table Content](#table-content)
	- [Remarks](#remarks)

<!-- /MarkdownTOC -->

<a name="undo-a-git-command"></a>
# Undo a Git Command

<a name="table-content"></a>
## Table Content

The following table lists a couple of commonly used git commands, along with corresponding commands to undo or fixup the mess.

Also, the commands are labeled with numbers, the remarks on each command (if any) are listed below the table content.

| No. | **Git Command**  |     **How To Undo**      |
|-----|------------------|--------------------------|
|   0 | `git add <file>` | `git reset HEAD <file>`  |
|   1 | `git commit`     | `git reset head^ --soft` |
|   2 | `git commit`     | `git commit --amend`     |
|   3 | `git push`       |                          |

<a name="remarks"></a>
## Remarks

- No.0: haha

[^1]: [What I Hate About Git | Hacker News](https://news.ycombinator.com/item?id=4340595)
[^2]: [10 things I hate about Git](http://stevebennett.me/2012/02/24/10-things-i-hate-about-git/)
