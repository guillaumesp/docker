FROM debian:bullseye
#php
RUN apt update && apt upgrade && apt install -yq lsb-release apt-transport-https ca-certificates software-properties-common wget unzip
RUN wget -O /etc/apt/trusted.gpg.d/php.gpg https://packages.sury.org/php/apt.gpg
RUN echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" | tee /etc/apt/sources.list.d/php.list
RUN apt update && apt install -yq php7.3 php7.3-cli php7.3-common php7.3-fpm php7.3-curl php7.3-mbstring php7.3-mysql php7.3-xml php7.3-json php7.3-pdo php7.3-mysql php7.3-zip php7.3-gd php7.3-bcmath php7.3-xdebug
#nginx
RUN apt install -yq nginx 
#nodejs
RUN curl -fsSL https://deb.nodesource.com/setup_11.x | bash -
RUN apt install -yq nodejs npm
#composer
RUN wget -O composer-setup.php https://getcomposer.org/installer
RUN php composer-setup.php --install-dir=/usr/local/bin --filename=composer
#keep container running
CMD [ "sh", "-c", "while sleep 1000; do :; done"]