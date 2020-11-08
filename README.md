# maven-project

Simple Maven Project

Setup data for Jenkins SSH files or execute commands over SSH
Source Code Management:
  Repository : https://github.com/trind09/ValaxyTech-hello-world.git
  Branches to build : */master
Build:
  Root POM:pom.xml
  Goals and options : clean install package
Post Steps
  Send files or execute commands over SSH
    Name: ansible_server
    Source files : **/webapp/target/webapp.war
    Remove prefix : webapp/target
    Remote directory : //opt
  Send files or execute commands over SSH
    Name: ansible_server
    Source files : Dockerfile
    Remote directory : //opt
    Exec Command:
      docker build -t valaxy_demo .
      docker tag valaxy_demo valaxy/valaxy_demo
      docker push valaxy/valaxy_demo
      docker rmi valaxy_demo valaxy/valaxy_demo
