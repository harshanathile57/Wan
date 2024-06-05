pipeline{
         agent any
  	triggers {
  pollSCM '* * * * *'
    	}
	parameters {
  choice choices: ['DEV', 'QA', 'UAT'], name: 'ENV'
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
sh '''if [ $ENV == "DEV" ];then
cp target/Wan.war  /home/harsh/Documents/apache-tomcat-9.0.88/webapps\'
elif[ $ENV == "QA" ]; then
cp target/Wan.war  /home/harsh/Documents/apache-tomcat-9.0.88/webapps\'
elif [ $ENV == "UAT" ];then
cp target/Wan.war  /home/harsh/Documents/apache-tomcat-9.0.88/webapps\'
fi'''
                                   }
                           }             
                          }
                                }      
