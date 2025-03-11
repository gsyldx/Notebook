git push origin HEAD:refs/for/

git commit --amend 补充提交到最近一次提交

git log 文件提交记录

git config --system core.longpaths true 拉取长文件名文件

git lfs install --skip-smudge 跳过大文件

[git@github.com](mailto:git@github.com):porscheag/android-app-framework.git

git stash: 保存当前修改

git stash list: 查看存储的更改

git stash apply: 应用最近的存储

git stash apply stash@{index}: 应用指定的存储

git stash pop: 应用并删除最近的存储

git stash drop stash@{index}: 删除存储的更改

git stash clear: 清空所有存储的更改

git stash save "message": 保存带有消息的存储

git stash show stash@{index}: 查看存储的更改细节