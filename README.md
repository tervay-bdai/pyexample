```
13:02 | ~/workspace/rpv | $ bazel run //src:main
INFO: Analyzed target //src:main (0 packages loaded, 0 targets configured).
INFO: Found 1 target...
Target //src:main up-to-date:
  bazel-bin/src/_main
INFO: Elapsed time: 0.203s, Critical Path: 0.00s
INFO: 1 process: 1 internal.
INFO: Build completed successfully, 1 total action
INFO: Running command line: bazel-bin/src/main
3.9.16
13:02 | ~/workspace/rpv | $ bazel run //src:main --config=bzlmod
INFO: Analyzed target //src:main (66 packages loaded, 515 targets configured).
INFO: Found 1 target...
Target //src:main up-to-date:
  bazel-bin/src/_main
INFO: Elapsed time: 2.131s, Critical Path: 0.00s
INFO: 7 processes: 7 internal.
INFO: Build completed successfully, 7 total actions
INFO: Running command line: bazel-bin/src/main
3.10.6
```