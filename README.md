# Mac MVC Setup
This Repository describes how to install Tomcat, Maven, Spring, JAVA in MAC to get started with MVC Project.

# Java Installation In MAC
1. I followed this link to install Tomcat server https://www.youtube.com/watch?time_continue=35&v=h_qQOVDTxo8
2. The above video is not uploaded by me.
3. In the video one can see that the tomcat server is up and running properly where as that was not the case with me.

# Tomcat Start up Error and Mitigation
1. upon execution of the command ./startup.sh you will see on the terminal that tomcat server started Running. However when you visit localhost:8080 on the browser you will not see tomcat server running.
2. Vist the apache-tomcat-9.0.14/logs path and check the catalina.out file content. You will see that file will describe JAVA path mentioned is not found. This is typically because the path where your java is installed and the file path being looked at are different.
3. Refer to the Stack overflow link https://stackoverflow.com/questions/15826202/where-is-java-installed-on-mac-os-x/15826203
  In case of MAC the path setting are bit differnt.
4. In my case I have to do changes in the ~/.bash_profile file
5. Below is the content from my ~/.bash_profile 
  #java export
  export PATH=/Library/Java/JavaVirtualMachines/1.6.0.jdk/Contents/Home/bin
  export M2_HOME=/Applications/apache-maven-3.6.0
  export PATH=$PATH:$M2_HOME/bin
  export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk-11.0.1.jdk/Contents/Home
  
6. Save this file and make sure to excecute "source ~/.bash_profile" 
7. Close the terminal in which you have executed the ~/.startup.sh command. This is must step. The terminal in which you were executing this command will still be referring to the old java path. Close this terminal and start a new terminal for the changes to get picked up.

