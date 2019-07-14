# TestRegistry

## How to get the `git-tree-sha1` value:

### Example: `Foo.jl`

```bash
$ git clone https://github.com/DilumAluthge/FooBar.git
$ cd FooBar
$ git checkout master
$ git log --pretty=format:'%T %s' | head -n 1
b9fe84c86a11503f3fffcc822856c2c98508e07b Add tests
$ git cat-file -p b9fe84c86a11503f3fffcc822856c2c98508e07b
100644 blob ab97e63beea7c5f0b2415ccab456ceb12b0eb412	.gitignore
040000 tree 9bc8a6fea95c8e8d25cb678bff610079110754f9	myfolder # myfolder contains Foo
040000 tree 6ecee1c4537bbc20e024c1c6194933c3f4269414	otherfolder
$ git cat-file -p 9bc8a6fea95c8e8d25cb678bff610079110754f9
040000 tree 4cc2b397c52bee060648fade86ea638c53c6fe22	Foo
```
So the `git-tree-sha1` for `Foo.jl` is `4cc2b397c52bee060648fade86ea638c53c6fe22`.

### Example: `Bar.jl`

```bash
$ git clone https://github.com/DilumAluthge/FooBar.git
$ cd FooBar
$ git checkout master
$ git log --pretty=format:'%T %s' | head -n 1
b9fe84c86a11503f3fffcc822856c2c98508e07b Add tests
$ git cat-file -p b9fe84c86a11503f3fffcc822856c2c98508e07b
100644 blob ab97e63beea7c5f0b2415ccab456ceb12b0eb412	.gitignore
040000 tree 9bc8a6fea95c8e8d25cb678bff610079110754f9	myfolder
040000 tree 6ecee1c4537bbc20e024c1c6194933c3f4269414	otherfolder # otherfolder contains subfolder
$ git cat-file -p 6ecee1c4537bbc20e024c1c6194933c3f4269414
040000 tree a8fc0a42d5b3165ef81bb030a40edc954356a29b	subfolder # subfolder contains Bar
$ git cat-file -p a8fc0a42d5b3165ef81bb030a40edc954356a29b
040000 tree 6f4acda473ceb8759c52f8931e7a8db81d727475	Bar
```

So the `git-tree-sha1` for `Bar.jl` is `6f4acda473ceb8759c52f8931e7a8db81d727475`.
