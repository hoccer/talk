talk
====

### Overview

This repository aggregates a group of (maven) modules in [git submodules](http://git-scm.com/docs/git-submodule) for convenience. Each submodule has all branches of the former _hoccer-talk-spike_ repository even if there have not been any module changes on this branch. This is an artefact of the automatic repository splitting process.

Using git submodules for development has some pitfalls developers should be aware of. The submodules act as "independent" repositories within a repository and are conceptually detached from its parent state on file level. The parent repository only tracks the commit hash of its submodule. Every file update of a submodule must therefore explicitly trigger a commit on the parent repository with the new submodule commit hash.

If the parent repository switches to another branch the submodule needs to be explicitly updated as well.

There are some ways to automate this procedure a bit. E.g. _Sourcetree_ automatically switches submodule commits accordingly and changes to submodules are made apparent with an additional commit dialog for the submodule. Also [git hooks](http://www.gluster.org/2014/05/keeping-git-submodules-in-sync-with-your-branches/) can be used to automatically update submodules when switching branches.

### Usage
```bash
// clone this repository
git clone git@github.com:hoccer/talk.git

cd talk

// initialize submodules
git submodule init

// pull submodules
git submodule update
```


