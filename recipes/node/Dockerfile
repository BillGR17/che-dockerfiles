# Copyright (c) 2012-2016 Codenvy, S.A.
# All rights reserved. This program and the accompanying materials
# are made available under the terms of the Eclipse Public License v1.0
# which accompanies this distribution, and is available at
# http://www.eclipse.org/legal/epl-v10.html
# Contributors:
# Codenvy, S.A. - initial API and implementation

FROM eclipse/stack-base:debian
    
RUN sudo apt-get update && \
    sudo apt-get install software-properties-common&& \
    sudo apt-key adv --recv-keys --keyserver keyserver.ubuntu.com 0xcbcb082a1bb943db&& \
    sudo add-apt-repository 'deb [arch=amd64,i386,ppc64el] http://mirror.klaus-uwe.me/mariadb/repo/10.2/debian jessie main'&& \
    sudo apt-get update && \
    sudo apt-get -y install build-essential libkrb5-dev gcc make debian-keyring python2.7 mariadb-server&& \
    sudo apt-get -y autoremove && \
    sudo apt-get -y clean && \
    sudo rm -rf /var/lib/apt/lists/* 

RUN wget -qO- https://deb.nodesource.com/setup_11.x| sudo -E bash -
RUN sudo apt update && sudo apt -y install nodejs && sudo npm i -g npm

EXPOSE 1337 3000 4200 5000 9000 8003

RUN sudo npm install --unsafe-perm -g webpack webpack-cli express-generator nodemon 
