
[大东哥的博客](https://mistdon.github.io/)

使用HEXO驱动，主题是[Next5.1.4](https://github.com/iissnan/hexo-theme-next)

HEXO驱动代码托管在私人Gitlab上

关于使用Hexo deploy覆盖 *commit* 和 *README.md* 的问题，采用的方法是

1. 将README.md添加到source目录下

2. 在_config.yml中配置 

   ```yaml
   skip_render: README.md
   ```
   
3. 自己写了一个deploy.sh

   ```shell
   hexo generate
   
   hexo clean 
   
   hexo deploy -g -m $1
   ```

每次提交的时候执行  

```bash
sh deploy.sh "commit_message"
```
hexo server test的时候执行
```bash
sh hexo-server.sh 4000 // 后面的端口号是可选的
```
可以避免 *commits* 和 *README.md* 被覆盖
