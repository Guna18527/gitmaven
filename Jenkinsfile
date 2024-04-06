pipeline {
    agent any
    
    tools {
        maven 'maven3'
    }

    stages {
        stage('git checkout') {
            steps {
                git 'https://github.com/Guna18527/gitmaven.git'
            }
        }
        stage('maven') {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage('Test') {
            steps {
                sh 'mv test'
            }
        }
    }

    post {
        always {
            echo 'post build action'
            build job: 'python'
            build job: 'maven project'
        }
    }
}
