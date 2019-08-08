pipeline {
    agent {
        docker {
            image "papitoio/capyrunner"
            args "--network=skynet" 
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
