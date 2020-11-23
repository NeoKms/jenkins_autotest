pipeline {
    agent { 
        docker { 
            image 'python:3.8' 
            args "-u root:root -p 8000:8000'
        } 
    }
    stages {
        stage('build') {
            steps {
                sh '/usr/local/bin/python3 -m venv --clear /home'
                sh 'source /home/bin/activate'
                sh "mkdir -p hello"
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
