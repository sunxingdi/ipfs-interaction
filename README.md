# IPFS交互实践

### IPFS简介
IPFS（InterPlanetary File System）是一个点对点的分布式文件系统，旨在连接所有计算设备，具有相同的文件系统。IPFS提供了一个高吞吐量、块存储模型、内容寻址的超链接，这些特性使得它成为创建分布式应用程序的理想工具。

IPFS的核心概念包括：

- 内容寻址：每个文件和所有块都有一个唯一的哈希，通过这个哈希可以找到文件。这意味着你可以从网络中的任何节点获取文件，并且可以验证文件内容是否完整无损。

- 分布式：没有中央服务器或管理节点，文件是在网络中不同节点之间传输和复制的，这使得IPFS非常抗审查并且具有高度冗余。

- 可持久性：一旦某个文件被上传到IPFS网络，只要全球范围内有节点持续提供该文件，它就会一直存在。

- 版本控制：IPFS支持历史快照，因此可以回退到文件的早期版本。

🔹在智能合约中，直接存储文件费用太高，可以通过存储IPFS文件哈希来达到存储文件的目的。

### 命令行交互

#### 下载IPFS

以kubo (go-ipfs)版本为例，下载地址：https://dist.ipfs.tech/#kubo

下载压缩包kubo_v0.25.0_windows-amd64.zip，解压后文件：
```
install.sh
ipfs.exe
LICENSE
LICENSE-APACHE
LICENSE-MIT
README.md
```

#### 查看IPFS版本
```shell
>ipfs --version
ipfs version 0.25.0
```

#### 初始化IPFS
```shell
>ipfs init
generating ED25519 keypair...done
peer identity: 12D3KooWGczjWKaez2EDHyfmd6BLYua7R23EkKy7Szk2naCapbKu
initializing IPFS node at C:\Users\Administrator\.ipfs
```

#### 节点上线
```shell
>ipfs daemon
Swarm listening on /ip6/240e:399:e6f:eef0:14f9:df1d:1520:d609/udp/4001/quic-v1/webtransport/certhash/uEiCHkZgcWZIKtJfe7giEim1CwxGW7UfQobMXttCXKwzEZA/certhash/uEiAFLT2bqTDr7UL-MSLoyt1nZCapT5DEubXvzaKaQoLGrg
Swarm listening on /ip6/240e:399:e6f:eef0:7bb:80a9:80bc:9bbe/tcp/4001
Swarm listening on /ip6/240e:399:e6f:eef0:7bb:80a9:80bc:9bbe/udp/4001/quic-v1
Swarm listening on /ip6/240e:399:e6f:eef0:7bb:80a9:80bc:9bbe/udp/4001/quic-v1/webtransport/certhash/uEiCHkZgcWZIKtJfe7giEim1CwxGW7UfQobMXttCXKwzEZA/certhash/uEiAFLT2bqTDr7UL-MSLoyt1nZCapT5DEubXvzaKaQoLGrg
Swarm listening on /ip6/240e:399:e6f:eef0::2/tcp/4001
Swarm listening on /ip6/240e:399:e6f:eef0::2/udp/4001/quic-v1
Swarm listening on /ip6/240e:399:e6f:eef0::2/udp/4001/quic-v1/webtransport/certhash/uEiCHkZgcWZIKtJfe7giEim1CwxGW7UfQobMXttCXKwzEZA/certhash/uEiAFLT2bqTDr7UL-MSLoyt1nZCapT5DEubXvzaKaQoLGrg
Swarm listening on /ip6/::1/tcp/4001
Swarm listening on /ip6/::1/udp/4001/quic-v1
Swarm listening on /ip6/::1/udp/4001/quic-v1/webtransport/certhash/uEiCHkZgcWZIKtJfe7giEim1CwxGW7UfQobMXttCXKwzEZA/certhash/uEiAFLT2bqTDr7UL-MSLoyt1nZCapT5DEubXvzaKaQoLGrg
Swarm listening on /p2p-circuit
Swarm announcing /ip4/110.185.93.205/udp/11889/quic-v1
Swarm announcing /ip4/110.185.93.205/udp/11889/quic-v1/webtransport/certhash/uEiCHkZgcWZIKtJfe7giEim1CwxGW7UfQobMXttCXKwzEZA/certhash/uEiAFLT2bqTDr7UL-MSLoyt1nZCapT5DEubXvzaKaQoLGrg
Swarm announcing /ip4/127.0.0.1/tcp/4001
Swarm announcing /ip4/127.0.0.1/udp/4001/quic-v1
Swarm announcing /ip4/127.0.0.1/udp/4001/quic-v1/webtransport/certhash/uEiCHkZgcWZIKtJfe7giEim1CwxGW7UfQobMXttCXKwzEZA/certhash/uEiAFLT2bqTDr7UL-MSLoyt1nZCapT5DEubXvzaKaQoLGrg
Swarm announcing /ip4/192.168.2.5/tcp/4001
Swarm announcing /ip4/192.168.2.5/udp/4001/quic-v1
Swarm announcing /ip4/192.168.2.5/udp/4001/quic-v1/webtransport/certhash/uEiCHkZgcWZIKtJfe7giEim1CwxGW7UfQobMXttCXKwzEZA/certhash/uEiAFLT2bqTDr7UL-MSLoyt1nZCapT5DEubXvzaKaQoLGrg
Swarm announcing /ip6/240e:399:e6f:eef0:14f9:df1d:1520:d609/tcp/4001
Swarm announcing /ip6/240e:399:e6f:eef0:14f9:df1d:1520:d609/udp/4001/quic-v1
Swarm announcing /ip6/240e:399:e6f:eef0:14f9:df1d:1520:d609/udp/4001/quic-v1/webtransport/certhash/uEiCHkZgcWZIKtJfe7giEim1CwxGW7UfQobMXttCXKwzEZA/certhash/uEiAFLT2bqTDr7UL-MSLoyt1nZCapT5DEubXvzaKaQoLGrg
Swarm announcing /ip6/::1/tcp/4001
Swarm announcing /ip6/::1/udp/4001/quic-v1
Swarm announcing /ip6/::1/udp/4001/quic-v1/webtransport/certhash/uEiCHkZgcWZIKtJfe7giEim1CwxGW7UfQobMXttCXKwzEZA/certhash/uEiAFLT2bqTDr7UL-MSLoyt1nZCapT5DEubXvzaKaQoLGrg
RPC API server listening on /ip4/127.0.0.1/tcp/5001
WebUI: http://127.0.0.1:5001/webui
Gateway server listening on /ip4/127.0.0.1/tcp/8080
Daemon is ready
```

#### 查询对等节点
```shell
>ipfs swarm peers
/ip4/103.20.169.133/udp/4001/quic-v1/p2p/12D3KooWMN6QZ1Rk7XJneDwYEcjPYd5wrGfRhYvhRkYUkkJiBTQK
/ip4/104.236.162.97/tcp/4001/p2p/QmZSw8YVbiRsZ5mbdRbZQP7RC3ZZSdnkdZvN4TH7zL1nnK
/ip4/104.238.167.94/udp/4001/quic-v1/p2p/12D3KooWSjfsTiie2rN3xNXmjFToL56N4aCse2uKnyVbe5DjUGp8
/ip4/107.173.201.158/udp/4001/quic-v1/p2p/12D3KooWBJvWrY2193Kvn5hgFd2JnxkYXYXCbzBaWhrvTVX9FKQ8
/ip4/107.174.156.145/udp/4001/quic-v1/p2p/12D3KooWB3WSxZRZ7qXCnGMbhT93FfoMsB6RhzynnLqR6jf3bmUt
/ip4/107.174.249.48/tcp/4001/p2p/QmPnEy7z2mMx5ms3MJJG5fDu79nG9gvAsLHtvQDo3aAdLM
/ip4/116.203.185.247/udp/4001/quic-v1/p2p/12D3KooWK8mC3mnhxYe7c14p8663nxHxD3AToSMqZmxeTuYWyiVB
/ip4/117.172.236.74/tcp/4589/p2p/12D3KooWFLekPWYbRi7tb2p6PVX87J7TYpc32nkCML3GogzQ6vt2
/ip4/121.157.241.41/tcp/41173/p2p/QmdAwGXkbdGspCh3vFFXrzrancsJVqyo2ADRbtRn98roaK
/ip4/13.57.178.134/tcp/4001/p2p/12D3KooWGzgza4PzUitKu2rRRKtM3R8iLpEeDjbx6r35WL3tsu3h
/ip4/135.148.122.168/udp/4001/quic-v1/p2p/12D3KooWF1VkHaB22pe8qDhVuXfcKEM84hqNmdfM7P77TJ2ARWpY
/ip4/135.181.5.188/udp/4001/quic-v1/p2p/12D3KooWLY24hyMgQVyxx6WjS4aXBk4PWpgqQtK8XJMPBeNuSZoy
/ip4/136.244.104.22/udp/4001/quic-v1/p2p/12D3KooWSpb4t2cgpNa5Q1qYEeMxvkb6D7qqApK54z9B9UhnbzcW
/ip4/137.220.50.249/udp/4001/quic-v1/p2p/12D3KooWJ4m95WBh2bS2VoJj6bfTNu465NbzqQi249RiG5id9YgJ
```

#### 上传文件
```shell
>ipfs add Ipfs-logo.png
 70.42 KiB / 70.42 KiB [==============================] 100.00%
 added QmRACojSdFuqnyyfQZ9Zgiz6zrVCUX1JRkYZyvRGu1MCzG Ipfs-logo.png
 70.42 KiB / 70.42 KiB [==============================] 100.00%
```

#### 下载文件(命令行)
```shell
>ipfs get QmRACojSdFuqnyyfQZ9Zgiz6zrVCUX1JRkYZyvRGu1MCzG -o my_get_image.png
Saving file(s) to my_get_image.png
 70.42 KiB / 70.42 KiB [==============================] 100.00% 0s
```

#### 下载文件(浏览器)
```
浏览器输入地址查看：
https://ipfs.io/ipfs/QmRACojSdFuqnyyfQZ9Zgiz6zrVCUX1JRkYZyvRGu1MCzG
```

### 参考文档

[IPFS 官方文档](https://docs.ipfs.tech/)

[IPFS 客户端下载](https://dist.ipfs.tech/)