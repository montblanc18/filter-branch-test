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

