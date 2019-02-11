#!groovy
properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '3'))])

node {
   /* 
    stage('Checkout') { 
   git branch: 'development', credentialsId: '7eae45e3-b94b-46b4-b754-5bffe4afd2fb', url: ' https://github.com/mohansoftwares/maven-web-application.git'

   }
 */
 
 stage('Checkout'){

     checkout scm
  }
  
   stage('Testing')
   {
    if(isUnix()){
     sh 'mvn test'
      }
      else{
       bat 'mvn test'   
      }
   }
   /*
   stage('SonarQube Report Generation')
   {
    if(isUnix()){
     sh 'mvn sonar:sonar'
      }
      else{
       bat 'mvn sonar:sonar'   
      }
   }
    
    stage('NexusDeploy')
   {
    if(isUnix()){
     sh 'mvn deploy'
      }
      else{
       bat 'mvn deploy'   
      }
   }
   
   stage ('Deploy to Tomcat'){
       
       sh 'echo deploying application into tomcat'
       sh 'cp $WORKSPACE/target/*.war /Users/bhaskarreddyl/BhaskarReddyL/Softwares/Running/apache-tomcat-9.0.12/webapps/'
       sh 'echo deploymnet done'
   }
   */
   stage ('Email Notifcation'){
       
       mail bcc: '', body: '''Build done

Regards,
Mithun Technologies''', cc: 'bhaskar0504@gmail.com', from: '', replyTo: '', subject: 'Deployment done', to: 'devopstrainingblr@gmail.com,satyaswarup.inbox@gmail.com'
   } 
    
}
