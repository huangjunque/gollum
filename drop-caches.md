### linux 清除缓存

Linux下清理内存和Cache方法 /proc/sys/vm/drop_caches

频繁的文件访问会导致系统的Cache使用量大增

```
$ free -m
total used free shared buffers cached
Mem: 3955 3926 28 0 55 3459
-/+ buffers/cache: 411 3544
Swap: 5726 0 5726

free内存减少到几十兆，系统运行缓慢
```

运行sync将dirty的内容写回硬盘
$sync

通过修改proc系统的drop_caches清理free的cache
$echo 3 > /proc/sys/vm/drop_caches

drop_caches的详细文档如下：

```
Writing to this will cause the kernel to drop clean caches, dentries and inodes from memory, causing that memory to become free.
To free pagecache:
* echo 1 > /proc/sys/vm/drop_caches
To free dentries and inodes:
* echo 2 > /proc/sys/vm/drop_caches
To free pagecache, dentries and inodes:
* echo 3 > /proc/sys/vm/drop_caches
As this is a non-destructive operation, and dirty objects are notfreeable, the user should run "sync" first in order to make sure allcached objects are freed.
This tunable was added in 2.6.16.
```

	$sync
	$sudo sysctl -w vm.drop_caches=3
	$sudo sysctl -w vm.drop_caches=0 #recovery drop_caches

操作后可以通过sudo sysctl -a | grep drop_caches查看是否生效。

3. 修改/proc/sys/vm/vfs_cache_pressure，调整清理inode/dentry caches的优先级（默认为100），LinuxInsight中有相关的解释：

```
At the default value of vfs_cache_pressure = 100 the kernel will attempt to reclaim dentries and inodes at a “fair” rate with respect to pagecache and swapcache reclaim. Decreasing vfs_cache_pressure causes the kernel to prefer to retain dentry and inode caches. Increasing vfs_cache_pressure beyond 100 causes the kernel to prefer to reclaim dentries and inodes.
```

具体的设置方法，可以参考方法1或者方法2均可。

参考资料

[kernel.org](https://www.kernel.org/doc/Documentation/sysctl/vm.txt)

[major.io](http://major.io/2008/12/03/reducing-inode-and-dentry-caches-to-keep-oom-killer-at-bay/)

[linix-mm](http://linux-mm.org/Drop_Caches)


上面的设置比较粗暴，使cache的作用基本无法发挥。需要根据机器的状况进行适当的调节寻找最佳的折衷。