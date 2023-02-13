pipeline {
    agent any

    stages {
        stage('Continuoues Download') {
            steps {
               git 'https://github.com/sunildevops77/maven.git'
            }
        }
        stage('Continuoues Build') {
            steps {
               sh 'mvn package'
            }
        }
        stage('Continuoues Deployment'){
     steps{
           sh 'scp /root/.jenkins/workspace/pipline/webapp/target/webapp.war    ec2-user@172.31.47.75:/var/lib/qaenv.war'
           }
       }
        stage('Continuoues Testing'){
     steps{
           sh 'echo "Testing passed"'
           }
       }
       stage('Continuoues Delivery'){
     steps{
           sh 'scp /root/.jenkins/workspace/pipline/webapp/target/webapp.war    ec2-user@172.31.33.172:/var/lib/qaenv.war'
           }
       }
    }
}
