FROM centos:7.5.1804
MAINTAINER bluenotefit
# RUN build時に実行

### Git ###
RUN yum -y install wget
RUN yum install gcc -y
RUN yum install make -y
RUN yum install bzip2 -y
RUN yum -y install git

### rbenv ###
RUN yum install -y openssl-devel readline-devel zlib-devel
RUN git clone https://github.com/sstephenson/rbenv.git ~/.rbenv
RUN git clone git://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build
RUN cd ~/.rbenv && src/configure && make -C src
RUN ~/.rbenv/bin/rbenv install 2.4.1
RUN ~/.rbenv/bin/rbenv global 2.4.1
RUN echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
RUN echo 'eval "$(rbenv init -)"' >> ~/.bashrc
RUN source ~/.bashrc
## CMD RUN時に実行
#CMD ["echo", "~/.bash_profile"]
#CMD ["source", "~/.bash_profile"]
