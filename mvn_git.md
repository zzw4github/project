mvn archetype:generate -DgroupId=me.zzw.app -DartifactId=akka -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false

git init

touch .gitignore

touch readme.MD

git add .

git commit -m "创建结构"

git remote add origin https://github.com/zzw4github/akka.git

git pull origin master (github创建项目的时候有 .gitignore 和 reademe.MD 不能提交，要先和本地分支合并才能提交)

git push  origin master

需要对.gitignore文件进行再次的修改。这次我们需要清除一下缓存cache，才能是.gitignore 生效
git rm -r --cached .  #清除缓存  
git add . #重新trace file  
git commit -m "update .gitignore" #提交和注释  
git push origin master #可选，如果需要同步到remote上的话  
