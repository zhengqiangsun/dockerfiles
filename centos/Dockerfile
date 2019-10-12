FROM centos:7
MAINTAINER 298043747@qq.com
# 首先安装wget，不然后面没法下载
RUN yum install -y wget
RUN mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup
RUN wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-6.repo
RUN sed -i -e '/mirrors.cloud.aliyuncs.com/d' -e '/mirrors.aliyuncs.com/d' /etc/yum.repos.d/CentOS-Base.repo
RUN yum clean all -y && \
		yum makecache -y  && \
		yum update -y
RUN yum install -y epel-release
RUN wget -O /etc/yum.repos.d/epel-7.repo  http://mirrors.aliyun.com/repo/epel-7.repo
RUN yum clean all -y && \
		yum makecache -y && \
		yum update -y

ENTRYPOINT ["yum","list","|","grep","epel-release"]

