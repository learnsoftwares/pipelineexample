pipeline {
    agent any

    stages {
        stage('code') {
            steps {
                git 'https://github.com/learnsoftwares/maven_demo.git'
            }
        }
         stage('build') {
            steps {
                bat 'mvn clean package'
            }
        }
         stage('deploy') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://localhost:9090/')], contextPath: 'declarativegame1', war: '**/*.war'
            }
        }
    }
}



