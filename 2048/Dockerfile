FROM nginx:latest 

LABEL author="Joaquin Gonzalez IAW"

#En el run podemos poner la continuidad de los comadnos con ; o &&
#rm -rf /var/lib/apt/lists/* --> Borrará todos los archivos cuando hacemos el update

RUN apt update \
    && apt install git -y \
    && rm -rf /var/lib/apt/lists/*

#Podemos tener dos capas diferentes para poder reutilizar cada "CAPA" de una manera diferente.
RUN git clone https://github.com/josejuansanchez/2048.git /app \
    && mv /app/* /usr/share/nginx/html \
    && rm -rf /app 

#Para ejecutar la docker run -d -p 80:80 2048