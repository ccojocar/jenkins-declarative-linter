pipeline {
    options {
        buildDiscarder(logRotator(numToKeepStr:'8'))
        ansiColor('xterm')
        disableConcurrentBuilds()
    }
    agent {
        kubernetes {
            label "declarative-lint-${UUID.randomUUID().toString()}"
        }
    }
    stages {
        stage('env variables') {
            steps {
                sh "printenv | sort"
            }
        }
    }
}
