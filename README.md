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
Author: montblanc18 <montblanc18@example.com>
Date:   Sat Mar 6 00:53:07 2021 +0900

    add files.

 hoge/test3.txt | 0
 test1.txt      | 0
 test2.txt      | 0
 3 files changed, 0 insertions(+), 0 deletions(-)

commit 25792b09d2188c5cb6ef3ac9bdf0054c6a4f8c6b (origin/main)
Author: montblanc18 <montblanc18@example.com>
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
Author: montblanc18 <montblanc18@example.com>
Date:   Sat Mar 6 01:03:37 2021 +0900

    mv file

 test2.txt => hoge/test2.txt | 0
 1 file changed, 0 insertions(+), 0 deletions(-)

commit 77e139e3d7db6cc532b72a7dc33293ce0731002d (origin/main, origin/HEAD)
Author: montblanc18 <montblanc18@example.com>
Date:   Sat Mar 6 00:54:14 2021 +0900

    update README.md

 README.md | 34 ++++++++++++++++++++++++++++++++++
 1 file changed, 34 insertions(+)

commit 0b2257027ee6decdc2ec2c4522aa30d138bf566f
Author: montblanc18 <montblanc18@example.com>
Date:   Sat Mar 6 00:53:07 2021 +0900

    add files.

 hoge/test3.txt | 0
 test1.txt      | 0
 test2.txt      | 0
 3 files changed, 0 insertions(+), 0 deletions(-)

commit 25792b09d2188c5cb6ef3ac9bdf0054c6a4f8c6b
Author: montblanc18 <montblanc18@example.com>
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
$ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
$ git add README.md 
$ git commit
[main e1da02d] update README.md
 1 file changed, 52 insertions(+)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
$ tree
.
├── README.md
├── hoge
│   ├── test2.txt
│   └── test3.txt
└── test1.txt

1 directory, 4 files
$ git log --stat
commit e1da02d2dc8fd507c55bfe90f037457563f7624a (HEAD -> main)
Author: montblanc18 <montblanc18@example.com>
Date:   Sat Mar 6 01:04:57 2021 +0900

    update README.md

 README.md | 52 ++++++++++++++++++++++++++++++++++++++++++++++++++++
 1 file changed, 52 insertions(+)

commit 4433447789a117280a58056a3d85df31fe30f795
Author: montblanc18 <montblanc18@example.com>
Date:   Sat Mar 6 01:03:37 2021 +0900

    mv file

 test2.txt => hoge/test2.txt | 0
 1 file changed, 0 insertions(+), 0 deletions(-)

commit 77e139e3d7db6cc532b72a7dc33293ce0731002d (origin/main, origin/HEAD)
Author: montblanc18 <montblanc18@example.com>
Date:   Sat Mar 6 00:54:14 2021 +0900

    update README.md

 README.md | 34 ++++++++++++++++++++++++++++++++++
 1 file changed, 34 insertions(+)

commit 0b2257027ee6decdc2ec2c4522aa30d138bf566f
Author: montblanc18 <montblanc18@example.com>
Date:   Sat Mar 6 00:53:07 2021 +0900

    add files.

 hoge/test3.txt | 0
 test1.txt      | 0
 test2.txt      | 0
 3 files changed, 0 insertions(+), 0 deletions(-)

commit 25792b09d2188c5cb6ef3ac9bdf0054c6a4f8c6b
Author: montblanc18 <montblanc18@example.com>
Date:   Sat Mar 6 00:46:26 2021 +0900

    first commit

 README.md | 1 +
 1 file changed, 1 insertion(+)
```

## コマンド実行

```bash
$ $ git filter-branch --tree-filter 'rm -rf ./hoge && rm -rf test2.txt' HEAD
WARNING: git-filter-branch has a glut of gotchas generating mangled history
         rewrites.  Hit Ctrl-C before proceeding to abort, then use an
         alternative filtering tool such as 'git filter-repo'
         (https://github.com/newren/git-filter-repo/) instead.  See the
         filter-branch manual page for more details; to squelch this warning,
         set FILTER_BRANCH_SQUELCH_WARNING=1.
Proceeding with filter-branch...

Cannot rewrite branches: You have unstaged changes.
$ git log --stat
commit 978d16ea7103dc95a414a49fc101c5d59dc6f226 (HEAD -> main)
Author: montblanc18 <montblanc18@example.com>
Date:   Sat Mar 6 01:13:05 2021 +0900

    update README.md

 README.md | 192 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 1 file changed, 192 insertions(+)

commit 0da54ae491b2282f1ec48523d8bebbf8280b026c
Author: montblanc18 <montblanc18@example.com>
Date:   Sat Mar 6 01:04:57 2021 +0900

    update README.md

 README.md | 52 ++++++++++++++++++++++++++++++++++++++++++++++++++++
 1 file changed, 52 insertions(+)

commit f61fcc19944d46e5f21711a784ccd552f2b32393
Author: montblanc18 <montblanc18@example.com>
Date:   Sat Mar 6 01:03:37 2021 +0900

    mv file

 test2.txt | 0
 1 file changed, 0 insertions(+), 0 deletions(-)

commit de71bc42f5cca05d4d0c0ced9640a49942241264
Author: montblanc18 <montblanc18@example.com>
Date:   Sat Mar 6 00:54:14 2021 +0900

    update README.md

 README.md | 34 ++++++++++++++++++++++++++++++++++
 1 file changed, 34 insertions(+)

commit 2d18cee0322f7d5fab0f4f2dc80e4b11fd0c94fe
Author: montblanc18 <montblanc18@example.com>
Date:   Sat Mar 6 00:53:07 2021 +0900

    add files.

 test1.txt | 0
 test2.txt | 0
 2 files changed, 0 insertions(+), 0 deletions(-)

commit 25792b09d2188c5cb6ef3ac9bdf0054c6a4f8c6b
Author: montblanc18 <montblanc18@example.com>
Date:   Sat Mar 6 00:46:26 2021 +0900

    first commit

 README.md | 1 +
 1 file changed, 1 insertion(+)
.
├── README.md
└── test1.txt

0 directories, 2 files

1 directory, 4 files
```

ファイルは消えたがコミットが残った。

```
$ git filter-branch -f --tree-filter 'rm -rf ./hoge && rm -rf *2.txt' HEAD
WARNING: git-filter-branch has a glut of gotchas generating mangled history
         rewrites.  Hit Ctrl-C before proceeding to abort, then use an
         alternative filtering tool such as 'git filter-repo'
         (https://github.com/newren/git-filter-repo/) instead.  See the
         filter-branch manual page for more details; to squelch this warning,
         set FILTER_BRANCH_SQUELCH_WARNING=1.
Proceeding with filter-branch...

Rewrite 978d16ea7103dc95a414a49fc101c5d59dc6f226 (6/6) (0 seconds passed, remaining 0 predicted)    
Ref 'refs/heads/main' was rewritten
$ git log --stat
commit 25c72106d75f924f45f51514b86edcf10e815053 (HEAD -> main)
Author: montblanc18 <montblanc18@example.com>
Date:   Sat Mar 6 01:13:05 2021 +0900

    update README.md

 README.md | 192 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 1 file changed, 192 insertions(+)

commit 04edd75651740e3e8abe1b6aeff43d35e379ae29
Author: montblanc18 <montblanc18@example.com>
Date:   Sat Mar 6 01:04:57 2021 +0900

    update README.md

 README.md | 52 ++++++++++++++++++++++++++++++++++++++++++++++++++++
 1 file changed, 52 insertions(+)

commit 6c9854712ef5f1b9b0cf16daffd4977f9a137aad
Author: montblanc18 <montblanc18@example.com>
Date:   Sat Mar 6 01:03:37 2021 +0900

    mv file

commit 5fdaed73546af015e54c0619a5657dcc9a4525fa
Author: montblanc18 <montblanc18@example.com>
Date:   Sat Mar 6 00:54:14 2021 +0900

    update README.md

 README.md | 34 ++++++++++++++++++++++++++++++++++
 1 file changed, 34 insertions(+)

commit 4d6a6cf38ddac77235c4ddc4d28d3b5101412c1f
Author: montblanc18 <montblanc18@example.com>
Date:   Sat Mar 6 00:53:07 2021 +0900

    add files.

 test1.txt | 0
 1 file changed, 0 insertions(+), 0 deletions(-)

commit 25792b09d2188c5cb6ef3ac9bdf0054c6a4f8c6b
Author: montblanc18 <montblanc18@example.com>
Date:   Sat Mar 6 00:46:26 2021 +0900

    first commit

 README.md | 1 +
 1 file changed, 1 insertion(+)
```

データが消えたことを確認した。