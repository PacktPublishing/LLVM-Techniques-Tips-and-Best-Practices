# Note
The sample code here is presented in the form of patches
(since they need to be put inside the LLVM code base). Please apply than to
the llvm-project repository via `git apply`.

For instance:
```
git apply SimpleLog.diff
```

If there are error messages showing conflict with the tree, it's possible that
the code base has been quite different since these code were developed. You can
choose to "rewind" to the time point when these two patches were created by using
the following command:
```
git checkout 9847023660467a4469b5667bcf7a4c73a4780037
```
After that you can execute the `git apply` command again.
