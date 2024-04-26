# Some of basic commands for git

克隆仓库
```
git clone (address of repo)
```

初始化仓库
```
git init
```

关联远程仓库
```
git remote add (connect name default:origin) (address of repo)
git remote remove (connect name)

git pull (connect name) (branch name) --allow-unrelated-histories // 关联非空远程仓库后
```

查看远程连接
```
git remote -v
```

pull
```
git pull (connect name) (branch name)
```

push
```
git push (connect name) (branch name)
```