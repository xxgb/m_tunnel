
[![MIT licensed][1]][2]  [![Build Status][3]][4]

[1]: https://img.shields.io/badge/license-MIT-blue.svg
[2]: LICENSE

[3]: https://travis-ci.org/lalawue/m_tunnel.svg?branch=master
[4]: https://travis-ci.org/lalawue/m_tunnel



# About

m_tunnel was a secure TCP tunnel with sock5 proxy interface, action like shadowsocks. It's lightweight and play well with https://github.com/lalawue/m_kcptun or https://github.com/xtaci/kcptun.

only support IPV4, under MacOS/Linux/Windows. 

using RC4 crypto from cloudwu's mptun https://github.com/cloudwu/mptun/.





# Features

- only one tcp connection between local and remote
- authentication only once, speed up every request
- socks5 proxy interface 
- support Windows




# QuickStart

Download precompiled [Release](https://github.com/lalawue/m_tunnel/releases).





# Compile & Running

1. in MacOS/Linux, first compile the source

```
# git clone https://github.com/lalawue/m_tunnel.git
# cd m_tunnel
# git submodule update --init --recursive
# make release
```

in Windows, using VS2017 under vc dir, the .vcxproj just ready for client side.



2. run remote & local
```
# ./tun_remote.out config/remote_conf.txt # in server
# ./tun_local.out config/local_conf.txt   # in local
```





# Configure

Under config dir, something like:

```
# file name for output
DEBUG_FILE=stdout

# local addr
LOCAL_ADDR=127.0.0.1:1080

# remote addr
REMOTE_ADDR=192.168.2.101:9871

# login info
USER_NAME=112233
PASS_WORD=123456

# 'NO' to disable RC4 crypto
#CRYPTO_RC4=NO

# 0 ~ 10, 0 to disable power save
POWER_SAVE=10
```
