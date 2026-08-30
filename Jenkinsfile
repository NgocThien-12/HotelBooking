pipeline {
    agent any

    stages {

        stage('Restore') {
            steps {
                echo 'Dang restore dependencies...'
                bat 'dotnet restore HotelBooking.sln'
            }
        }

        stage('Build') {
            steps {
                echo 'Dang build project...'
                bat 'dotnet build HotelBooking.sln --configuration Release --no-restore'
            }
        }

        stage('Unit Test') {
            steps {
                echo 'Dang chay Unit Test...'
                bat 'dotnet test HotelBooking.sln --configuration Release --no-build --logger "console;verbosity=normal"'
            }
        }
    }

    post {
        success {
            echo 'BUILD SUCCESSFUL - Pipeline hoan thanh!'
        }

        failure {
            echo 'BUILD FAILED - Pipeline that bai!'
        }
    }
}