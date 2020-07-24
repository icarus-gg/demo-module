# demo-module
git workflow for working with submodules

## initializing submodule repos
from project root
```
git submodule update --init --recursive
git submodule foreach --recursive git checkout master
```

## syncing main repo with any submodule changes
inside module folder (main repo)
```
git pull
git submodule update --remote --merge
```

# developing submodules :

### adding a new submodule to a git repo
```
git submodule add git@github.com:icarus-gg/demo-submodule.git
git commit -am "submodule added"
git push
```

### cloning a repo that contains submodules
```
git clone git@github.com:icarus-gg/demo-module.git
cd demo-module
git submodule update --init --recursive
git submodule foreach --recursive git checkout master
```

### making changes to submodule repo
inside demo-submodule folder = normal workflow
additional step : cd back to parent repo and `commit -am` to let it know the submodule repo has been updated 
```
git commit -am "submodule updates..."
git push
cd ..
git commit -am "updating submodule commit hash"
git push
```
