pipeline {
    agent { docker { image 'python:3.8' } }
    stages {
        stage('build') {
            steps {
                sh '/usr/local/bin/python3 -m venv --clear /home'
            }
            steps {
                sh 'source /home/bin/activate'
            }
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }
        stage('test') {
            steps {
                sh 'python -m unittest discover -v'
            }
        }
    }
}
