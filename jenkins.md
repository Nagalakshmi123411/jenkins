### Jenkins

## Intro

To install Jenkins on Linux.

**Method 1:**
Installation on Debian-based Systems

1.Install Java: Ensure you have Java installed. Jenkins requires Java 11 or later:

     ' sudo apt update'
    'sudo apt install openjdk-11-jdk'

2.Add the Jenkins Repository: Import the GPG key and add the Jenkins repository:

      ' wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo gpg --dearmor -o /usr/share/keyrings/jenkins.gpg'

        'echo "deb [signed-by=/usr/share/keyrings/jenkins.gpg] http://pkg.jenkins.io/debian-stable binary/" | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null'

3.Update Package Index: Update the package index to include the new repository:
       
       'sudo apt update'

4.Install Jenkins: Now install Jenkins:

       'sudo apt install jenkins'

5.Start Jenkins: Start the Jenkins service:

       'sudo systemctl start jenkins'

6.Enable Jenkins on Boot: To ensure Jenkins starts on boot, run:

          'sudo systemctl enable jenkins'

7.Access Jenkins: Open your web browser and go to http://your_server_ip_or_domain:8080. You will need the initial admin password found in:

        'sudo cat /var/lib/jenkins/secrets/initialAdminPassword'
      
***Method 2.***
Installation on Red Hat-based Systems

1.Install Java: Similar to Debian-based systems, ensure Java is installed:

        'sudo yum install java-11-openjdk-devel'

2.Add the Jenkins Repository: Create a new repository file for Jenkins:
       
       ' sudo wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins-ci.org/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key '

3.Install Jenkins: Now install Jenkins using yum:

      'sudo yum install jenkins'

4.sudo systemctl start jenkins:

        'sudo systemctl start jenkins'

5.Enable Jenkins on Boot: To ensure Jenkins starts on boot, run:

         'sudo systemctl enable jenkins'

6.Configure Firewall: If you have a firewall running, allow traffic on port 8080:
       
        'sudo firewall-cmd --add-port=8080/tcp --permanent'
        'sudo firewall-cmd --reload'

7.Access Jenkins: As with Debian-based systems, open your browser and navigate to http://your_server_ip_or_domain:8080 and use the initial admin password located at:

          'sudo cat /var/lib/jenkins/secrets/initialAdminPassword'

### Conculsion ###
Following these steps will get Jenkins up and running on your Linux machine.
