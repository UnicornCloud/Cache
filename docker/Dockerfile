FROM ubuntu

RUN apt update && apt install -y ansible

RUN mkdir -p /uni/roles

COPY roles /uni/roles/
COPY in.yml /uni/
COPY hosts/cache /etc/ansible/hosts

WORKDIR /uni
RUN ansible-playbook build.yml

#Test
#RUN ansible -m ping apt_cacher

EXPOSE 3142/tcp
CMD chmod 777 /var/cache/apt-cacher-ng && /etc/init.d/apt-cacher-ng start && tail -f /var/log/apt-cacher-ng/*
