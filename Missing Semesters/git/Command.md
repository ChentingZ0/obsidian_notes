```python
git clone https://github.com/graphdeco-inria/gaussian-splatting --recursive
```
The `--recursive` option is crucial if the repository contains submodules. Submodules are essentially child repositories included within the parent repository at specific paths. When you use `--recursive`, Git will initialize and update each submodule in the repository, including nested submodules if any. This means that along with the main repository, you'll also get the content of any submodules it uses, fully initialized and ready to use.


