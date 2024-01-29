FROM node

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 80

# env 的用法, 可以在 docker run 的時候, 透過 -e 來設定, 也可以在 docker-compose.yml 裡面設定
# 這邊的設定, 是為了讓 docker-compose.yml 裡面的環境變數可以被使用, 這樣就不用在 docker-compose.yml 裡面設定
ENV MONGODB_USERNAME=root
ENV MONGODB_PASSWORD=secret

CMD ["npm", "start"]