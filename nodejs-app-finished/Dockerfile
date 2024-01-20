# 这是一个 Dockerfile，它定义了一个 Docker 镜像的构建过程。下面是每行命令的解释：
# FROM node:12: 这行告诉 Docker 使用 Node.js 12 版本的官方 Docker 镜像作为基础镜像。所有后续的命令都在这个镜像的基础上运行。

# FROM node:12: 这行告诉 Docker 使用 Node.js 12 版本的官方 Docker 镜像作为基础镜像。所有后续的命令都在这个镜像的基础上运行。

# WORKDIR /app: 这行设置了在 Docker 容器内部的工作目录。所有后续的命令（如 RUN, CMD, ENTRYPOINT, COPY 和 ADD）都会在这个目录下执行。

# COPY package.json /app: 这行将本地的 package.json 文件复制到 Docker 容器的 /app 目录下。
# COPY . /app 命令表示将当前目录（即 Dockerfile 所在的目录）中的所有文件和文件夹复制到容器的 /app 目录。
# 你可以使用 .dockerignore 文件来排除一些不需要复制到容器中的文件和文件夹。
# 例如，你可以在 .dockerignore 文件中添加 node_modules 文件夹，这样就不会将它复制到容器中。
# 这样做的好处是，当你在本地安装了新的 npm 包时，不需要重新构建 Docker 镜像，因为 node_modules 文件夹不会被复制到容器中。

# RUN npm install: 这行在 Docker 容器内部运行 npm install 命令，安装 package.json 文件中定义的所有依赖。
# 你可以在运行容器时覆盖这个默认命令，例如 docker run -p 3000:80 nodejs-app npm run dev。
# 你也可以在 Dockerfile 中使用 ENTRYPOINT 命令来定义容器的默认执行命令，但是这样的话，你就不能在运行容器时覆盖默认命令了。

# COPY . /app: 这行将当前目录下的所有文件和文件夹复制到 Docker 容器的 /app 目录下。

# EXPOSE 80: 这行告诉 Docker，容器打算在运行时监听 80 端口。

# CMD ["node", "server.js"]: 这行定义了容器默认的执行命令。在这个例子中，当容器启动时，它会运行 node server.js 命令。
# 你可以在运行容器时覆盖这个默认命令，例如 docker run -p 3000:80 nodejs-app npm run dev。
# 你也可以在 Dockerfile 中使用 ENTRYPOINT 命令来定义容器的默认执行命令，但是这样的话，你就不能在运行容器时覆盖默认命令了。
# 如果CMD 想要運行 script, such as npm run start, 應該怎麼描述
# CMD ["npm", "run", "start"]

FROM node:18

WORKDIR /app

COPY package.json /app

RUN npm install

COPY . /app

EXPOSE 80

CMD ["node", "server.js"]