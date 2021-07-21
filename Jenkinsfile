pipeline {
    agent any
    tools {
        maven 'Maven38'
    }
    stages {
        stage('Get the code') {
            steps {
                git 'https://github.com/chethanhjoshi/mavennew/'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn package'
            }
        }
        stage('Approval from release manager') {
            input {
                message "Approved By ReleaseManager"
            }
            steps {
                sh 'echo "hello"'
            }
        }
        stage('DevDeploy') {
            steps {
                sh 'cp target/JenkinsWar.war /var/lib/tomcat9/webapps'
            }
        }
    }
}
