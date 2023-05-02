FROM amazonlinux:2

RUN amazon-linux-extras install -y

RUN yum update -y && yum install \
        systemd \
        tar \
        unzip \
        sudo \
        -y

RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" \
    && unzip awscliv2.zip \
    && sudo ./aws/install

RUN useradd "ec2-user" && echo "ec2-user ALL=NOPASSWD: ALL" >> /etc/sudoers

RUN amazon-linux-extras install -y python3.8
RUN pip3.8 install awscli-local

CMD ["/sbin/init"]
