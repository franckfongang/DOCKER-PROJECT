FROM amazonlinux:latest

# Install dependencies 
RUN yum update -y && \
    yum install -y httpd && \
    yum search wget && \
    yum install wget -y && \
    yum install unzip -y
    
    # change directory
    RUN cd /var/www/html

    # download Webfiles
    RUN wget https:// github.com/franckfongang/techmax/archive/refs/heads/main.zip

    # unzip folder 
    RUN unzip main.zip

    # copy files into html direstory
    RUN cp -r jupiter-main/* /var/www/html/

    #remove unwanted Folder 
    RUN rm -rf jupiter-main main.zip

    #exposes port 80 on the container 
    EXPOSE 80

    #set the default application that will start when the container start
    ENTRYPOINT [ " /usr/sbin/httpd" , "-D" , "FOREGROUND"]
    # now you can create your website