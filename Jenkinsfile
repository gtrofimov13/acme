pipeline {
    agent any
    stages {
        stage('Pre-Build') {
            steps {
                sh 'echo "Starting the script"'
                cleanWs()
                git branch: 'master', url: 'https://github.com/gtrofimov13/Projects.git'
            }
        }
        stage('Build') {
            steps {
              sh 'echo "Nothing to Build"'
            }
        }
        stage('Test'){
            steps {
              sh 'echo "Nothing to Test"'
            }
        }
        stage('Deploy') {
            steps {
              sh '''
                  echo "Start Docker container"
                  docker build -t homepage-ngnix
                  docker run \
                  --name homepage-ngnix \
                  -p 8888:80
                  -d gt-ngnix
                  '''
            }
        }
    }
}
