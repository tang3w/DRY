* Firstly, you should have a virtual machine running Debian/Ubuntu.
* Install shadowsocks-libev. Refer to https://github.com/shadowsocks/shadowsocks-libev
* Edit configuration file /etc/shadowsocks-libev/config.json as follow:

```json
{
    "server":"{{SERVER_IP}}",
    "server_port":8388,
    "local_port":1080,
    "password":"naive",
    "method":"chacha20",
    "timeout":300
}
```

* Start service using command:

```sh
/etc/init.d/shadowsocks-libev restart
```

* Install shadowsocks-libev in client.
* Start proxy using command:

```sh
ss-local -s {{SERVER_IP}} -p 8388 -l 1080 -k naive -m "chacha20"
```
