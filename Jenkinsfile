pipeline {
    agent {
        docker {
            image "ruby:alpine"
        }
    }
    stages {
        stage("Build") {
            steps {
                sh "chmod +x scripts/alpine.sh"
                sh "./scripts/alpine.sh"
                sh "bundle install"
            }
        }
        stage("Tests") {
            steps {
                sh "echo 'simulando um teste automatizado'"
            }
        }
    }
}