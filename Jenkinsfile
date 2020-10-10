pipeline {
    agent any
    stages {
        stage('Verify Branch') {
            steps {
               echo "$GIT_BRANCH"
            }
        }
        stage('Docker Build') {
            steps {
               sh 'docker images -a'
               sh(script:'''
                  cd azure-vote/
                  docker images -a
                  docker build -t jenkins-pipeline .
                  cd ..
               ''')
            }
        }
    }
}
