pipeline {
    agent any
    stages {
        stage('git repo & clean') {
            steps {
               bat "rmdir  /s /q github.com/juazafra/pipeline"
                bat "git clone https://github.com/juazafra/pipeline"
                bat "mvn clean -f github.com/juazafra/pipeline"
            }
        }
        stage('install') {
            steps {
                bat "mvn install -f github.com/juazafra/pipeline"
            }
        }
        stage('test') {
            steps {
                bat "mvn test -f github.com/juazafra/pipeline"
            }
        }
        stage('package') {
            steps {
                bat "mvn package -f github.com/juazafra/pipeline"
            }
        }
    }
}
