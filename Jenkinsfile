pipeline {
    agent { docker { image 'python:3.8' } }
    stages {
        stage('build') {
            steps {
                sh 'pip3 install --user -r requirements.txt'
            }
        }
        stage('test') {
            steps {
                sh 'python -m unittest discover -v'
            }
        }
    }
}
