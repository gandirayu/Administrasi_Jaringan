# Getting our App into PWD

1. Ketikkan perintah PWD di terminal 
    ```docker run -dp 80:80 docker/getting-started:pwd```
    ![start](./img/1.png)

2. Download file app.zip

3. Drag file app.zip ke dalam terminal, kemudian unzip file tersebut
```unzip app.zip```
    ![unzip](./img/2.png)

4. Pindah ke directory app dan buat file Dockerfile
    ```vim Dockerfile```
    ![vim](./img/3.png)

5. Isi file tersebut dengan script dibawah ini
    ```
    FROM node:18-alpine
    WORKDIR /app
    COPY . .
    RUN yarn install --production
    CMD ["node", "src/index.js"]
    ```
    ![vim](./img/4.png)

6. Build Docker image menggunakan perintah
```docker build -t docker-101 .```
    ![build](./img/5.png)

7. Run Docker image pada port 3000 dengan perintah
```docker run -dp 3000:3000 docker-101```
    ![run](./img/6.png)

8. Buka port 3000 dari instance PWD:
```http://ip172-18-0-84-cp5juq291nsg00a85jog-3000.direct.labs.play-with-docker.com/```
    ![run](./img/7.png)