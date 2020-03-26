# 生成patch
```git
git log
git format-patch $commit-id //某次commit之后的所有都patch
# 从根到指定提交的所有patch
git format-patch --root $commit-id
# 当前分支所有超前master的提交
git format-patch -M master
# 两次提交之间的所有patch
git format-patch $commit-id...$commit-id
# 某次提交（含）之前的几次提交
git format-patch -n $commit-d
```

# 解决补丁失败
```shell
# f1
git am --abort
edit & commit
# f2
git am < 0....patch
git apply PATCH --reject
edit ...
git add .
git am --resolved
```
# 执行patch
```git
# 检查patch文件
git apply --stat 0....patch
# 检查patch能否执行
git apply --check 0....patch
# 打补丁
git am [--signoff] < 0....patch
# -s或--signoff commit是否加入Signed-off-by信息
```
