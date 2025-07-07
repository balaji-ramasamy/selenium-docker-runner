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
                bat "docker-compose -f test-suites.yaml up"
            }
        }
    }

    post{
        always{
            bat "docker-compose -f grid.yaml down"
            bat "docker-compose -f test-suites.yaml down"
            archiveArtifacts artifacts: 'output/flight-reservation/emailable-report.html', followSymLinks: false,
            archiveArtifacts artifacts: 'output/vendor-portal/emailable-report.html', followSymLinks: false,
        }
    }
}