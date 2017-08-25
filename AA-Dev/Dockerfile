FROM malkab/nodejs:v8_4_0
MAINTAINER Juan Pedro Perez "jp.perez.alcantara@gmail.com"

# Installation
# There is an issue with the install of gyp that makes the 
# installation enter into a loop with no exit
# This is a hack to avoid it. Try to just perform the npm install
# with a newest version
RUN useradd -ms /bin/bash node
USER node
ENV PATH=/home/node/.npm-global/bin:$PATH
ENV NPM_CONFIG_PREFIX=/home/node/.npm-global
RUN mkdir /home/node/.npm-global && \
    npm install -g \
        @angular/cli \
        typescript \
        tslint \
        live-server

# Run
ENTRYPOINT ["/bin/bash"]