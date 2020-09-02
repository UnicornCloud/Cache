FROM ubuntu

RUN apt update && apt install -y ansible

RUN mkdir -p /uni/roles

COPY roles /uni/roles/
COPY cache.yml /uni/
COPY hosts /etc/ansible/hosts

WORKDIR /uni
RUN ansible-playbook docker.yml

#Test
#RUN ansible -m ping apt_cacher

EXPOSE 3142/tcp
