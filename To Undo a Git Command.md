It seems I'm not the only one who believes that git commands are poorly designed.[^1]

To make things worse, they also provide a human-unreadable documentation as well.[^2]
So it's very common for beginners to leave a mess in the workspace after running a God-knows-what-it-means git command. Therefore I wrote this blog. Hopefully this could save you from clueless.

## Table of Contents
<!-- MarkdownTOC -->

- [The Cheat Sheet](#the-cheat-sheet)
- [Remarks](#remarks)

<!-- /MarkdownTOC -->


<a name="the-cheat-sheet"></a>
## The Cheat Sheet

Some commonly used git commands are listed below, along with the corresponding commands to undo or fixup the mess.
The commands are labeled with numbers, and the remarks on some of the commands are listed under the table content.

| No. |   **Git Command**   |           **How To Undo**            |
|-----|---------------------|--------------------------------------|
| 0   | `git add <file>...` | `git rm --cached <file>...`          |
| 1*  | `git commit`        | `git reset head^ --soft`             |
| 2*  | `git commit`        | `git commit --amend`                 |
| 3*  | `git commit`        | `git revert <commit_sha>`            |
| 4   | `git merge`         | `git revert -m 1 <merge_commit_sha>` |
| 5   | `git pull`          | `git reset HEAD@{1}`                 |
| 6*  | `git push`          | `git push --force origin <refspec>`  |

<a name="remarks"></a>
## Remarks

- No.1: Only useful when the commit is not pushed yet and is not an "orphan commit". [^3]
- No.2: Only useful when the commit is not pushed yet. If the commit is already pushed to remote, use `git revert` instead. *Another (not recommanded) way is to add `--force` when performing next `git push`, use with caution![^4]*
- No.3: To "revert" a commit does not erase the commit in the commit history. Instead, it generates a new commit which reverses the effect of the specified commit. This is usually the recommend way to undo a commit.
- No.6: **Use with caution!** This may affect other people's work. If you don't know what you are doing, **DON'T** do it.
- 本来用英文写是为了好玩。。后来发现ghost-blog的英文字体渲染真的好漂亮。于是想以后都用英文写了（误。。）

[^1]: [What I Hate About Git | Hacker News](https://news.ycombinator.com/item?id=4340595)
[^2]: [10 things I hate about Git](http://stevebennett.me/2012/02/24/10-things-i-hate-about-git/)
[^3]: [How to remove the first commit in git?](http://stackoverflow.com/a/10911506/1294704)
[^4]: [How do I push amended commit to the remote git repo?](http://stackoverflow.com/a/432518/1294704)
