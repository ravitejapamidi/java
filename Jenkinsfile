pipeline{
    agent any

    /*tools {
         maven 'maven'
         jdk 'java'
    }*/

    stages{
        stage('checkout'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'github access', url: 'https://github.com/ravitejapamidi/java.git']]])
            }
        }
        stage('build'){
            steps{
               sh 'mvn package'
         stage('Deploy to Tomcat') {
            steps {
                // Copy the generated WAR file to Tomcat webapps directory
                sh 'cp target/jb-hello-world-maven-0.2.0.jar /opt/tomcat/webapps/'
            }
        }
    }
}
