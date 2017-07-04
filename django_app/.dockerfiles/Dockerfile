FROM            eb_ubuntu
MAINTAINER      bbungsang@gmail.com

RUN             apt-get -y install
# 현재 경로의 모든 파일을 컨테이너의 /srv/deploy_eb_docker 폴더에 복사
COPY            . /srv/deploy_eb_docker

# cd /srv/deploy_eb_docker 와 같은 효과
WORKDIR         /srv/deploy_eb_docker

# requirements 설치
RUN             /root/.pyenv/versions/deploy_eb_docker/bin/pip install -r .requirements/debug.txt

COPY            .config/supervisor/uwsgi.conf /etc/supervisor/conf.d/
CMD             supervisord -n

EXPOSE          80 8000