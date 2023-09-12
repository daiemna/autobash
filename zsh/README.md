## link docker executables in MacOS
1. remove docker related files in `/usr/local/bin`
```
ls /Applications/Docker.app/Contents/Resources/bin | awk '{ print "/usr/local/bin/"$1 }' | xargs rm -f
```
2. check docker files in `/usr/local/bin`
```
find /usr/local/bin -iname '*docker*'
```
3. link all the executables in source directory.
```
ln -s $(ls -d /Applications/Docker.app/Contents/Resources/bin/*) /usr/local/bin
```