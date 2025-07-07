pipeline{
    agent any

    stages{
        stage('Start GRID'){
            steps{
                bat "docker-compose -f grid.yaml up -d"
            }
        }
        stage('Run Test'){
            steps{
                bat "docker-compose -f test-suites up"
            }
        }
    }

    post{
        always{
            bat "docker-compose -f grid.yaml down"
            bat "docker-compose -f test-suites down"
        }
    }
}