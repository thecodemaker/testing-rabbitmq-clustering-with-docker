FROM centos:6

RUN yum -y update

# Install base deps
RUN yum install -y net-tools pwgen wget curl tar unzip mlocate logrotate

# Add and enable relevant application repositories:
# Note: We are also enabling third party remi package repositories.
RUN wget http://packages.erlang-solutions.com/erlang-solutions-1.0-1.noarch.rpm
RUN rpm -Uvh erlang-solutions-1.0-1.noarch.rpm

# Finally, download and install Erlang:
RUN yum install -y erlang

# Install RabbitMQ deps
RUN rpm --import https://www.rabbitmq.com/rabbitmq-signing-key-public.asc

RUN yum install -y  http://www.rabbitmq.com/releases/rabbitmq-server/v3.1.0/rabbitmq-server-3.1.0-1.noarch.rpm

# Allow triggerable events on the first time running
RUN touch /tmp/firsttimerunning

