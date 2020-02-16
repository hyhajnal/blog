## crontab 定时任务

需求：每周四10:00和15:00发送一个消息提醒

`crontab.sh`  需要注意两点：环境变量 + 绝对路径

`index.js`  就是定时需要执行的内容

```
SHELL=/bin/bash
PATH=/sbin:/bin:/usr/sbin:/usr/bin:/usr/local/bin

# 在线测试: https://tool.lu/crontab/
# 计划任务定义的例子:
# .---------------- 分 (0 - 59)
# |  .------------- 时 (0 - 23)
# |  |  .---------- 日 (1 - 31)
# |  |  |  .------- 月 (1 - 12)
# |  |  |  |  .---- 星期 (0 - 7) (星期日可为0或7)
# |  |  |  |  |
# *  *  *  *  * 执行的命令
# * * * * * date >> /tmp/date.txt

# 每分钟发送一个消息
# * * * * * NODE_ENV=production node /home/mapp/ui-crontab/index.js

# 每周四 上午10:00一次，下午15:00一次
0 10,15 * * 4 NODE_ENV=production node /home/mapp/ui-crontab/index.js
```



命令

```bash
crontab -e	# 修改文件
crontab -r	# 删除文件（干掉所有内容）
crontab -l	#显示文件
```

