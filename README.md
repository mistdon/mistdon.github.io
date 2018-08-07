
[大东哥的博客](https://mistdon.github.io/)

使用HEXO驱动，主题是[yilia](https://github.com/litten/hexo-theme-yilia)

关于使用Hexo deploy覆盖commit和README.md的问题，采用的方法是

1. 将README.md添加到source目录下

2. 在_config.yml中配置 

   ```yaml
   skip_render: README.md
   ```

   3. 自己写了一个deploy.sh

   ```shell
   hexo generate -w
   
   hexo clear
   
   hexo deploy -g -m $1
   ```

每次提交的时候执行 

```bash
sh deploy.sh "commit_message"
```

可以避免commits和README.md被覆盖