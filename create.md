1. mvn archetype:generate -DgroupId=me.zzw.app -DartifactId=akka -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
2. git init
3. touch .gitignore
4. touch readme.MD
5. git add .
6. git commit -m "创建结构"
7. git remote add origin https://github.com/zzw4github/akka.git
8. git pull origin master (github创建项目的时候有 .gitignore 和 reademe.MD 不能提交，要先和本地分支合并才能提交)
9. 修改后 push 怎么没用
10. git push  origin master
