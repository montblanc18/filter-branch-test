# filter-branch-test

## 初期状態

```bash
$ tree
.
├── README.md
├── hoge
│   └── test3.txt
├── test1.txt
└── test2.txt
$ git log --stat
commit 0b2257027ee6decdc2ec2c4522aa30d138bf566f (HEAD -> main)
Author: montblanc18 <skurita.phys@gmail.com>
Date:   Sat Mar 6 00:53:07 2021 +0900

    add files.

 hoge/test3.txt | 0
 test1.txt      | 0
 test2.txt      | 0
 3 files changed, 0 insertions(+), 0 deletions(-)

commit 25792b09d2188c5cb6ef3ac9bdf0054c6a4f8c6b (origin/main)
Author: montblanc18 <skurita.phys@gmail.com>
Date:   Sat Mar 6 00:46:26 2021 +0900

    first commit

 README.md | 1 +
 1 file changed, 1 insertion(+)
 $ 
```

```bash
$ tree
.
├── README.md
├── hoge
│   ├── test2.txt
│   └── test3.txt
└── test1.txt

1 directory, 4 files
$
$
$ git log --stat
commit 4433447789a117280a58056a3d85df31fe30f795 (HEAD -> main)
Author: montblanc18 <skurita.phys@gmail.com>
Date:   Sat Mar 6 01:03:37 2021 +0900

    mv file

 test2.txt => hoge/test2.txt | 0
 1 file changed, 0 insertions(+), 0 deletions(-)

commit 77e139e3d7db6cc532b72a7dc33293ce0731002d (origin/main, origin/HEAD)
Author: montblanc18 <skurita.phys@gmail.com>
Date:   Sat Mar 6 00:54:14 2021 +0900

    update README.md

 README.md | 34 ++++++++++++++++++++++++++++++++++
 1 file changed, 34 insertions(+)

commit 0b2257027ee6decdc2ec2c4522aa30d138bf566f
Author: montblanc18 <skurita.phys@gmail.com>
Date:   Sat Mar 6 00:53:07 2021 +0900

    add files.

 hoge/test3.txt | 0
 test1.txt      | 0
 test2.txt      | 0
 3 files changed, 0 insertions(+), 0 deletions(-)

commit 25792b09d2188c5cb6ef3ac9bdf0054c6a4f8c6b
Author: montblanc18 <skurita.phys@gmail.com>
Date:   Sat Mar 6 00:46:26 2021 +0900

    first commit

 README.md | 1 +
 1 file changed, 1 insertion(+)
```

```bash
$ tree
.
├── README.md
├── hoge
│   ├── test2.txt
│   └── test3.txt
└── test1.txt

1 directory, 4 files
[montblanc18@Ava ~/hikaru/program/filter-branch-test]$ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
[montblanc18@Ava ~/hikaru/program/filter-branch-test]$ git add README.md 
[montblanc18@Ava ~/hikaru/program/filter-branch-test]$ git commit
[main e1da02d] update README.md
 1 file changed, 52 insertions(+)
[montblanc18@Ava ~/hikaru/program/filter-branch-test]$ git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
[montblanc18@Ava ~/hikaru/program/filter-branch-test]$ tree
.
├── README.md
├── hoge
│   ├── test2.txt
│   └── test3.txt
└── test1.txt

1 directory, 4 files
[montblanc18@Ava ~/hikaru/program/filter-branch-test]$ git log --stat
commit e1da02d2dc8fd507c55bfe90f037457563f7624a (HEAD -> main)
Author: montblanc18 <skurita.phys@gmail.com>
Date:   Sat Mar 6 01:04:57 2021 +0900

    update README.md

 README.md | 52 ++++++++++++++++++++++++++++++++++++++++++++++++++++
 1 file changed, 52 insertions(+)

commit 4433447789a117280a58056a3d85df31fe30f795
Author: montblanc18 <skurita.phys@gmail.com>
Date:   Sat Mar 6 01:03:37 2021 +0900

    mv file

 test2.txt => hoge/test2.txt | 0
 1 file changed, 0 insertions(+), 0 deletions(-)

commit 77e139e3d7db6cc532b72a7dc33293ce0731002d (origin/main, origin/HEAD)
Author: montblanc18 <skurita.phys@gmail.com>
Date:   Sat Mar 6 00:54:14 2021 +0900

    update README.md

 README.md | 34 ++++++++++++++++++++++++++++++++++
 1 file changed, 34 insertions(+)

commit 0b2257027ee6decdc2ec2c4522aa30d138bf566f
Author: montblanc18 <skurita.phys@gmail.com>
Date:   Sat Mar 6 00:53:07 2021 +0900

    add files.

 hoge/test3.txt | 0
 test1.txt      | 0
 test2.txt      | 0
 3 files changed, 0 insertions(+), 0 deletions(-)

commit 25792b09d2188c5cb6ef3ac9bdf0054c6a4f8c6b
Author: montblanc18 <skurita.phys@gmail.com>
Date:   Sat Mar 6 00:46:26 2021 +0900

    first commit

 README.md | 1 +
 1 file changed, 1 insertion(+)
```

## コマンド実行

```bash
$ git filter-branch --tree-filter 'rm -rf ./hoge' HEAD
WARNING: git-filter-branch has a glut of gotchas generating mangled history
         rewrites.  Hit Ctrl-C before proceeding to abort, then use an
         alternative filtering tool such as 'git filter-repo'
         (https://github.com/newren/git-filter-repo/) instead.  See the
         filter-branch manual page for more details; to squelch this warning,
         set FILTER_BRANCH_SQUELCH_WARNING=1.
Proceeding with filter-branch...

Cannot rewrite branches: You have unstaged changes.
$ git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
[montblanc18@Ava ~/hikaru/program/filter-branch-test]$ git log --stat
commit e1da02d2dc8fd507c55bfe90f037457563f7624a (HEAD -> main)
Author: montblanc18 <skurita.phys@gmail.com>
Date:   Sat Mar 6 01:04:57 2021 +0900

    update README.md

 README.md | 52 ++++++++++++++++++++++++++++++++++++++++++++++++++++
 1 file changed, 52 insertions(+)

commit 4433447789a117280a58056a3d85df31fe30f795
Author: montblanc18 <skurita.phys@gmail.com>
Date:   Sat Mar 6 01:03:37 2021 +0900

    mv file

 test2.txt => hoge/test2.txt | 0
 1 file changed, 0 insertions(+), 0 deletions(-)

commit 77e139e3d7db6cc532b72a7dc33293ce0731002d (origin/main, origin/HEAD)
Author: montblanc18 <skurita.phys@gmail.com>
Date:   Sat Mar 6 00:54:14 2021 +0900

    update README.md

 README.md | 34 ++++++++++++++++++++++++++++++++++
commit e1da02d2dc8fd507c55bfe90f037457563f7624a (HEAD -> main)
Author: montblanc18 <skurita.phys@gmail.com>
Date:   Sat Mar 6 01:04:57 2021 +0900

    update README.md

 README.md | 52 ++++++++++++++++++++++++++++++++++++++++++++++++++++
 1 file changed, 52 insertions(+)

commit 4433447789a117280a58056a3d85df31fe30f795
Author: montblanc18 <skurita.phys@gmail.com>
Date:   Sat Mar 6 01:03:37 2021 +0900

    mv file

 test2.txt => hoge/test2.txt | 0
 1 file changed, 0 insertions(+), 0 deletions(-)

commit 77e139e3d7db6cc532b72a7dc33293ce0731002d (origin/main, origin/HEAD)
Author: montblanc18 <skurita.phys@gmail.com>
Date:   Sat Mar 6 00:54:14 2021 +0900

    update README.md

 README.md | 34 ++++++++++++++++++++++++++++++++++
 1 file changed, 34 insertions(+)

commit 0b2257027ee6decdc2ec2c4522aa30d138bf566f
Author: montblanc18 <skurita.phys@gmail.com>
Date:   Sat Mar 6 00:53:07 2021 +0900

    add files.

 hoge/test3.txt | 0
 test1.txt      | 0
 test2.txt      | 0
 3 files changed, 0 insertions(+), 0 deletions(-)

commit 25792b09d2188c5cb6ef3ac9bdf0054c6a4f8c6b
Author: montblanc18 <skurita.phys@gmail.com>
Date:   Sat Mar 6 00:46:26 2021 +0900

    first commit

 README.md | 1 +
 1 file changed, 1 insertion(+)
$ tree
.
├── README.md
├── hoge
│   ├── test2.txt
│   └── test3.txt
└── test1.txt

1 directory, 4 files
```

ファイルが残った。