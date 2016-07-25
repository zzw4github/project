mvn archetype:generate -DgroupId=me.zzw.app -DartifactId=akka -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
git init
touch .gitignore
touch readme.MD
git add .
git commit -m "创建结构"
git remote add origin https://github.com/zzw4github/akka.git
git pull origin master (github创建项目的时候有 .gitignore 和 reademe.MD 不能提交，要先和本地分支合并才能提交)
git push  origin master
