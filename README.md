# 基于官方 code-server 镜像
FROM codercom/code-server:latest

# 设置工作目录
WORKDIR /home/coder/project

# 复制初始化的工作区文件
COPY ./workspace /home/coder/project

# 暴露默认端口
EXPOSE 8080

# 启动 code-server
CMD ["code-server", "--bind-addr", "0.0.0.0:8080", "--auth", "none", "/home/coder/project"]
