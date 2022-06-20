node {
def mavenHome = tool name: "maven_pipeline"
properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([cron('* * * * *'), pollSCM('* * * * *')])])
stage ('CheckoutCode')
{
git branch: 'development', url: 'https://github.com/Kiran8099988/maven-web-application.git'
}
stage ('Build_with_Maven')
{
sh "${mavenHome}/bin/mvn clean package"
}
/*
stage ('Generate_Sonar_report')
{
sh "${mavenHome}/bin/mvn sonar:sonar"
}
stage ('Deploy_to_Tomcat_Server')
{
sshagent(['4ba657ad-6977-4837-81b4-b8c7a4b1d993']) {
sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@13.232.84.128:/opt/apache-tomcat-9.0.63/webapps"
}
}
*/
}
