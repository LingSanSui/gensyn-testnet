<h2 align=center>Gensyn Testnet Node Guide</h2>

## 💻 System Requirements

| Requirement                        | Details                                                                                      |
|-------------------------------------|---------------------------------------------------------------------------------------------|
| **CPU Architecture**                | `arm64` or `amd64`                                                                          |
| **Recommended RAM**                 | 25 GB                                                                                       |
| **CUDA Devices (Recommended)**      | `RTX 3090`, `RTX 4090`, `A100`, `H100`                                                      |
| **Python Version**                  | Python >= 3.10 (For Mac, you may need to upgrade) 


## 🌐 Rent GPU
- Visit : [Vast.ai Website](https://cloud.vast.ai/?ref_id=226538)
- Sign Up using email address
- Go to your email and verify your Vast.ai account
- Click on `Add Credit` button in the corner to deposit fund
- You can deposit using crypto currency (from metamask) or using Credit card
- Now  select [Ubuntu 22.04 jammy](https://cloud.vast.ai/?ref_id=226538&creator_id=226538&name=Ubuntu%2022.04%20jammy) in the below
- Now click on `Select GPU` and search `RTX 4090` and choose it
- Now choose a GPU and click on `RENT` button
- Your GPU server will be deployed soon
- Now click on `Connect` option and then choose `Connect to web terminal`

## 📥 Installation

1. **Install（安装） `sudo`**
```bash
apt update && apt install -y sudo
```
2. **Install other dependencies（安装其他依赖项）**
```bash
sudo apt update && sudo apt install -y python3 python3-venv python3-pip curl wget screen git lsof && curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add - && echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list && sudo apt update && sudo apt install -y yarn
```
3. **Install Node.js and npm if not installed already（如果未安装Node.js和npm，请执行安装）**  
```bash
curl -sSL https://raw.githubusercontent.com/zunxbt/installation/main/node.sh | bash
```
4. **Clone this repositoryI（克隆项目）**
```bash
cd $HOME && [ -d rl-swarm ] && rm -rf rl-swarm; git clone https://github.com/LingSanSui/rl-swarm.git
```
5. **go to rl-swarm（进入项目目录）**
```bash
cd rl-swarm
```
6. **Create a `screen` session（创建一个`screen` 会话）**
```bash
screen -S gensyn
```
7. **venv（创建venv虚拟环境并激活）**
```bash
python3 -m venv .venv && . .venv/bin/activate
```
8. **Run the swarm（启动项目）**
```bash
./run_rl_swarm.sh
```


**测试全部命令一次性执行**
```bash
apt update && apt install -y sudo && sudo apt update && sudo apt install -y python3 python3-venv python3-pip curl wget screen git lsof && curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add - && echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list && sudo apt update && sudo apt install -y yarn && curl -sSL https://raw.githubusercontent.com/zunxbt/installation/main/node.sh | bash && cd $HOME && [ -d rl-swarm ] && rm -rf rl-swarm; git clone https://github.com/LingSanSui/rl-swarm.git && cd rl-swarm && screen -S gensyn && python3 -m venv .venv && . .venv/bin/activate && ./run_rl_swarm.sh
```

**重启服务器后的一次性执行命令**
```bash
cd rl-swarm && screen -S gensyn && python3 -m venv .venv && . .venv/bin/activate && ./run_rl_swarm.sh
```

**只重启项目的执行命令**
```bash
./run_rl_swarm.sh
```

- It will ask some questions, you should send response properly
- ```Would you like to connect to the Testnet? [Y/n]``` : Write `Y`（默认回车是Y）
- ```Would you like to push models you train in the RL swarm to the Hugging Face Hub? [y/N]``` : Write `N`（默认回车是N）
- When you will see interface like this, you can detach from this screen session（当你看到这样的界面时，你可以脱离这个屏幕会话）
- 建议备份自己的名字和node id。登录成功后记得备份项目目录下的swarm.pem文件，更换服务器时放入项目路径下可以继续使用原来的名字和node id，继承进度。

![Screenshot 2025-04-01 061641](https://github.com/user-attachments/assets/b5ed9645-16a2-4911-8a73-97e21fdde274)

7. **Detach from `screen session`**
- Use `Ctrl + A` and then press `D` to detach from this screen session.（使用“Ctrl+A”，然后按“D”脱离此屏幕会话。）
