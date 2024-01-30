FROM node

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .
# expose 80 對應 app.listen(80), 這樣才能讓外部連進來, 但是這邊只是定義, 還沒有真的開啟
# 這邊的 80 是指 container 內部的 port, 也就是說, container 內部的 80 port 會對應到外部的 80 port
EXPOSE 80 

ENV MONGODB_USERNAME=root
ENV MONGODB_PASSWORD=secret

CMD ["npm", "start"]