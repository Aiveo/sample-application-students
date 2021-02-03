FROM python:3.7.6-stretch

RUN pip install pip --upgrade
RUN pip install ansible

RUN apt-get update -y && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
    sshpass

RUN mkdir /tmp/ansible

ENV IDRSA_PATH=/tmp/ansible/id_rsa

WORKDIR /tmp/ansible
CMD ls && pwd && ansible-playbook -i inventories/setup.yml playbook.yml