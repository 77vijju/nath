pipeline {
    agent any

    stages {
        stage('continous download') {
            steps {
                git 'https://github.com/77vijju/war-web-project.git'
            }
        }
        stage('mvn build') {
            steps {
                sh 'mvn install'
            }
        }
        stage('continues deployment') {
            steps {
                sh 'sshpass -p "vijju" scp target/wwp-1.0.0.war vijju@172.17.0.3:/opt/apache-tomcat-9.0.56/webapps'
            }
        }
    }
}
