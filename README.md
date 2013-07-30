### Hugo source shot for 2013-07-29

#### To build hugo:

```
git clone https://github.com/krasin2/hugo-2013-07-29.git
PATH=`pwd`/hugo-2013-07-29 go get github.com/spf13/hugo
ls -l hugo-2013-07-29/bin/hugo
```

#### To create a source shot next time:

```
export HUGO_ROOT=`pwd`/hugo-`date --rfc-3339=date`
mkdir $HUGO_ROOT
GOPATH=$HUGO_ROOT go get github.com/spf13/hugo
cd $HUGO_ROOT
rm -rf bin pkg
find -type d -name .git | xargs rm -rf
find -type d -name .hg | xargs rm -rf
find -type d -name .bzr | xargs rm -rf
git add src
git commit -m "Add hugo with dependencies"
git remote origin add <destination git repo here>
git push origin master
```

