pipeline{
    agent any

    stages{
        stage('Run Test'){
            steps{
                bat "docker-compose up"
            }
        }
        stage('bring grid down'){
            steps{
                echo "docker-compose down"
            }
        }
    }
}