pipeline {
    agent { 
        docker { 
            image 'python:3.8.0' 
            args '-u root:root -p 8000:8000'
        } 
    }
    stages {
        stage('Git') {
            steps {
               git branch: 'main', url: 'https://github.com/NeoKms/jenkins_autotest'
            }
        }
        //stage('build') {
        //    steps {
        //        sh '/usr/local/bin/python3 -m venv --clear /home'
        //        sh 'source /home/bin/activate'
        //        sh "mkdir -p hello"
        //        sh 'pip3 install -r requirements.txt'
        //    }
        //}
        stage('test') {
            steps {
                sh 'python --version'
                sh 'python -c "import this"'
                sh '/usr/local/bin/python3 -m venv --clear /home'
                //sh 'source /home/bin/activate'
                //sh '. env/bin/activate '
                sh 'pip install --upgrade pip'
                sh 'pip install pytest'
                sh 'pip install -r requirements.txt'
                sh 'cd app'
                sh 'pytest'
            }
        }
    }
}
