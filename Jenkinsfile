pipeline{
    agent any
    stages{
        stage('Start Grid'){
            steps{
              sh "docker-compose -f grid.yaml up -d"

            }
        }
        stage('Bring Grid Down'){
            steps{

                sh "docker-compose -f test-suites.yaml up"

            }
        }
    }
    post{
        always{
          sh "docker-compose -f grid.yaml down"
          sh "docker-compose -f test-suites.yaml down"
        }
    }
}
