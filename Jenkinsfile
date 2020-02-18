pipeline {
    agent any
    stages{
        stage('clone the repo and removing the existing one')
        {
          steps {
              sh "sudo rm -rf /home/t/dev/project"
              sh "cd /home/t/"
              sh "mkdir -p /home/t/dev/project"
              sh "cd /home/t/dev/project"
              sh "git clone https://github.com/PacktPublishing/Develop-and-Deploy-Modern-Web-Applications-with-Docker-Video-.git /home/t/dev/project"
               
               }
         }
         
         stage("copying files to /var/www/html")
         {
           steps 
           {
              sh "sudo cp /home/t/dev/project/www/html/index.html /var/www/html/"
           }
          }
          
           stage("Installing the webserver and starting its service")
          {
            steps
            {
              sh "sudo apt install apache2 -y"
              sh "sudo systemctl start apache2"
            }
          }
          
          
          stage("Restarting the apache2 service")
          {
            steps
            {
              sh "sudo systemctl restart apache2"
            }
          }
               
    }

}
