FROM python:slim


RUN apt-get -y update &&\
    apt-get install -y python3-pip &&\
    apt-get autoremove -y &&\
    pip3 install pyyaml google-api-python-client

RUN apt-get install -y curl apt-transport-https ca-certificates gnupg &&\
    echo "deb [signed-by=/usr/share/keyrings/cloud.google.gpg] http://packages.cloud.google.com/apt cloud-sdk main" | tee -a /etc/apt/sources.list.d/google-cloud-sdk.list &&\
    curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key --keyring /usr/share/keyrings/cloud.google.gpg  add - &&\
    apt-get update -y &&\
    apt-get install google-cloud-sdk -y
      
