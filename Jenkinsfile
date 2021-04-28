
pipeline {
    agent any

    stages {
        stage('Verify Branch') {
            steps {
              echo "$GIT_BRANCH"
            }
        }
        
        stage('DOCKER BUILD') {
            steps {
              echo (script: 'docker images -a')
              echo (script: """
               cd azure-vote/
               docker images -a
               docker build -t jenkins-pipeline .
               docker images -a
               cd ..
               """)  
            }
        }
    }
}
