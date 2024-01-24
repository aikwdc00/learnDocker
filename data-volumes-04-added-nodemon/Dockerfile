FROM node:14

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 80

# 什麼是VOLUME指令？
# VOLUME指令是用來建立一個可以從容器外部存取的目錄，這個目錄可以是一個目錄或是一個資料卷。
# 這個指令可以讓我們在容器啟動時，將一個本地端的目錄掛載到容器內部，或是將一個資f料卷掛載到容器內部。
# 這個指令的語法如下：
# VOLUME ["/data"] 或 VOLUME /data 或 VOLUME /data /var/lib/mysql 
# 
# VOLUME [ "/app/node_modules" ]

CMD [ "npm", "start" ]