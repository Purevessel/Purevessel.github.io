flashback

回收站视图：RECYCLEBIN/USER_RECYCLEBIN

除了sysdb用户以外，其他用户只能看到自己的回收站信息

10G后拥有的功能，缺省设置为开启，查看：
SQL>show parameter recycle

删除之后使用命令:
flashback TABLE [表名] TO BEFORE DROP [RENAME TO...]

表名处除表的名字也可以使用其在RECYCLEBIN视图中的唯一约束“BIN$unique_id$version”，长度固定26位。这是用来防止解决因为多次删除同一个名字的表而导致的命名的冲突.比如:有一个用户删除了一个名字为 T1 的表,然后重新创建了这个表T1,然后又给删掉了.或者是有两个人删除了同名的两个表，那么为了区分，就必须有一个独立的键值。

采用purge命令清空回收站：purge recyclebin。或者是在drop的最后加入purge关键字，即可完全删除表。

以上的flashback是针对整张表的，针对行级的flashback可以通过scn和timestamp来实现