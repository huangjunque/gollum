#Redis

官网：http://redis.io/

安装文档: http://redis.io/download

## 安装

     cd /usr/local/src/
     wget http://redis.googlecode.com/files/redis-2.6.13.tar.gz
     tar xzf redis-2.6.13.tar.gz
     cd redis-2.6.13
     make && make install
     # 添加init script
     vim /etc/init.d/redis-server
     chmod +x /etc/init.d/redis-server
     
     # 添加redis配置文件
     cd /usr/local/src/redis-2.6.13
     mkdir -p /etc/redis
     cp redis.conf /etc/redis/
     # 编辑redis配置文件，将其修改为守护进程模式
     vim /etc/redis/redis.conf
     编辑文件 daemonize yes
     
     # 添加服务
     chkconfig --add redis-server
     # 添加到自启动
     chkconfig redis-server on       

用这个脚本管理之前，需要先配置下面的内核参数，否则Redis脚本在重启或停止redis时，将会报错，并且不能自动在停止服务前同步数据到磁盘上：

    vi /etc/sysctl.conf
     
     编辑文件 vm.overcommit_memory = 1
     
     # 应用生效
     sysctl -p

##init script



      #!/bin/sh
      #
      # redis - this script starts and stops the redis-server daemon
      #
      # chkconfig:   - 85 15 
      # description:  Redis is a persistent key-value database
      # processname: redis-server
      # config:      /etc/redis/redis.conf
      # config:      /etc/sysconfig/redis
      # pidfile:     /var/run/redis.pid
      
      # Source function library.
      . /etc/rc.d/init.d/functions
      
      # Source networking configuration.
      . /etc/sysconfig/network
      # Check that networking is up.
      [ "$NETWORKING" = "no" ] && exit 0
      redis="/usr/local/sbin/redis-server"
      prog=$(basename $redis)
      REDIS_CONF_FILE="/etc/redis/redis.conf"
      [ -f /etc/sysconfig/redis ] && . /etc/sysconfig/redis
      lockfile=/var/lock/subsys/redis
      start() {
            [ -x $redis ] || exit 5
            [ -f $REDIS_CONF_FILE ] || exit 6
            echo -n $"Starting $prog: "
            daemon $redis $REDIS_CONF_FILE
            retval=$?
            echo
             [ $retval -eq 0 ] && touch $lockfile
            return $retval
    }
    stop() {
            echo -n $"Stopping $prog: "
            killproc $prog -QUIT
            retval=$?
             echo
            [ $retval -eq 0 ] && rm -f $lockfile
             return $retval
    }

    restart() {
            stop
            start
    }     

    reload() {
            echo -n $"Reloading $prog: "
             killproc $redis -HUP
            RETVAL=$?
            echo
    }

    force_reload() {
             restart
    }

     rh_status() {
         status $prog
     }

      rh_status_q() {
    rh_status >/dev/null 2>&1
    }

     case "$1" in
           start)
              rh_status_q && exit 0
              $1
              ;;
           stop)
             rh_status_q || exit 0
             $1
              ;;
            restart|configtest)
              $1
              ;;
             reload)
              rh_status_q || exit 7
              $1
               ;;
             force-reload)
             force_reload
              ;;
              status)
               rh_status
               ;;   
             condrest    rh_status_q || exit 0
                  ;;
           *)
                echo $"Usage: $0 {start|stop|status|restart|condrestart|try-restart|reload|force-reload}"
        exit 2
     esac
 
