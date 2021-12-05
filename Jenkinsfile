node
{

def mavenHome = tool name: "maven3.8.4"

properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), [$class: 'RebuildSettings', autoRebuild: false, rebuildDisabled: false], [$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([pollSCM('* * * * *')])])

stage('CheckoutCode'){
git branch: 'development', credentialsId: '588bf710-9a90-4c3a-8b1b-d274270d6e44', url: 'https://github.com/Vinod2DevOps/maven-web-application.git'   
}
stage('Build'){
sh "${mavenHome}/bin/mvn clean package"
}
/*
stage('ExecuteSonarQubeReport'){
sh "${mavenHome}/bin/mvn sonar:sonar"
}
stage('UploadArtifactsIntoNexus'){
sh "${mavenHome}/bin/mvn deploy"
}
stage('DeployAppintoTomcatServer'){

sshagent(['a594f310-f494-4b35-aac7-0ad97d4dcb0f']) {
   sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@52.66.7.63:/opt/apache-tomcat-9.0.54/webapps/"
}
}
stage('SendEmailNotification'){
emailext body: '''Build Over
Regards
G VINOD KUMAR
Kurnool
8498886546''', subject: 'Build Over', to: 'gollalatha1976@gmail.com'
}
*/
}
