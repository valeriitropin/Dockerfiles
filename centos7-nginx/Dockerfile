FROM centos:centos7

RUN yum -y update
RUN yum -y upgrade
RUN yum -y install wget
RUN cd /etc/yum.repos.d && wget https://repo.codeit.guru/codeit.el`rpm -q --qf "%{VERSION}" $(rpm -q --whatprovides redhat-release)`.repo
RUN yum -y install epel-release
RUN yum -y install nginx
RUN yum clean all
RUN rm -v /etc/nginx/nginx.conf
ADD configs/nginx.conf /etc/nginx

VOLUME /etc/nginx/conf.d
VOLUME /var/www

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]