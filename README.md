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

