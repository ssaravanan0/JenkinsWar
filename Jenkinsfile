node{
 
   def tomcatWeb = 'C:\\apache-tomcat-9.0.2\\webapps'
   def tomcatBin = 'C:\\apache-tomcat-9.0.2\\bin'
   def tomcatStatus = ''
   
   agent { docker {image 'maven:3.8.3'}}
   stage('SCM Checkout'){
     git 'https://github.com/ssaravanan0/JenkinsWar'
   }
   stage('Compile-Package-create-war-file'){
      // Get maven home path
      def mvnHome =  tool name: 'apache-maven-3.8.3', type: 'maven'   
      bat "${mvnHome}/bin/mvn package"
      }
/*   stage ('Stop Tomcat Server') {
               bat ''' @ECHO OFF
               wmic process list brief | find /i "tomcat" > NUL
               IF ERRORLEVEL 1 (
                    echo  Stopped
               ) ELSE (
               echo running
                  "${tomcatBin}\\shutdown.bat"
                  sleep(time:10,unit:"SECONDS") 
               )
'''
   }*/
   /*
   stage('Deploy to Tomcat'){
     bat "copy target\\JenkinsWar.war \"${tomcatWeb}\\JenkinsWar.war\""
   }
      stage ('Start Tomcat Server') {
         sleep(time:5,unit:"SECONDS") 
         bat "${tomcatBin}\\startup.bat"
         sleep(time:100,unit:"SECONDS")
   }*/
}
