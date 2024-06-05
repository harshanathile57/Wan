pipeline{
         agent any
  	triggers {
  pollSCM '* * * * *'
    	}
         stages{
              stage("Checkout scm") {
         steps{ 
                 checkout scm
              }
                  }
         stage("BUILD"){
                steps{
     sh '/home/harsh/Documents/apache-maven-3.9.6/bin/mvn install' 
                            } 
                            } 
         stage("Deployment"){
                steps{
         sh 'cp target/Wan.war /home/harsh/Documents/apache-tomcat-9.0.88/webapps'    
                                   }
                           }             
                          }
                                }      
