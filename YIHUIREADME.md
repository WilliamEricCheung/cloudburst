## 系统更新
```
sudo apt update
sudo apt upgrade
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt update
```
## 实验环境Python配置
### 安装依赖工具
```sudo apt-get install -y gcc make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev```

### 下载源码文件压缩包
```wget https://www.python.org/ftp/python/3.6.6/Python-3.6.6.tgz```

### 解压源码文件压缩包
```tar -zxf Python-3.6.6.tgz```

### 配置
```cd Python-3.6.6```
```sudo ./configure --enable-optimizations```

### 编译
```sudo make```

### 安装
```sudo make install```

### 查看Python版本
```python3.6 --version```

### 切换Python环境
```
sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.10 2
sudo update-alternatives --install /usr/local/bin/python python /usr/local/bin/python3.6 1
```

#### 不同版本间切换
```sudo update-alternatives --config python```
#### 验证切换成功
```python --version```

### 创建虚拟环境venv
#### 验证虚拟环境
```
python -m venv --help
```
#### 创建并激活
```
python -m venv cloudburst-venv
source cloudburst-venv/bin/activate
```

#### 退出虚拟环境
```
deactivate
```

### 卸载pip
```
python -m pip uninstall pip
```

### 安装pip
```
curl https://bootstrap.pypa.io/pip/3.6/get-pip.py -o get-pip.py
python get-pip.py
# pip对应版本为10.0.1
```

### pip环境配置
```
echo 'export PATH=/usr/local/bin/python3.6/bin:$PATH' >>~/.bashrc
source ~/.bashrc
```

## 实验环境基础配置
### Python依赖库
```pip3 install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple/```

### Protobuf等依赖安装
```./common/scripts/install-dependencies.sh```