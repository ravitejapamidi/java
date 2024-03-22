pipeline{
    agent any
    

    stages{
        stage('checkout'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'github access', url: 'https://github.com/ravitejapamidi/java.git']]])
            }
        }
        stage('build'){
            steps{
                sh 'mvn --version'
                sh 'mvn install'
                sh 'mvn test'
                sh 'mvn compile'
                sh 'mvn package'
            }
        }
            
       /* stage('Deploy to Tomcat') {
            steps {
                // Copy the generated WAR file to Tomcat webapps directory
                sh 'cp /var/lib/jenkins/workspace/ABC/target/jb-hello-world-maven-0.2.0.jar'
            } 
        } */
    }
}
