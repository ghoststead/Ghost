# GhostSteady

## Upgrade process

### Upgrade admin (using the submodule)
```
cd core/client
git checkout master
git pull
git checkout steady
git merge <ghost-tag-name> # e.g. 3.40.5
git push
yarn
cd ../..
```

### Upgrade Ghost itself
```
git checkout master
git pull
git checkout steady
git merge <ghost-tag-name> # e.g. 3.40.5
```

* Make sure core/client is the right commit
* Bump the version number in `package.json`

### Test it
```shell
grunt test-all
```

### Generate release zip file
```shell
grunt release
```

* copy zip from from `.dist/release` to root
* build `docker` image
