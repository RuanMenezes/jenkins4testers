pipeline {
    agent {
        docker {
            image "ruby:alpine:3.9"
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
                sh "bundler exec cucumber -p ci"
            }
        }
    }
}