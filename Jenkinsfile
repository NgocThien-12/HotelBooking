
pipeline {
    agent any

    stages {

        stage('Restore') {
            steps {
                echo 'Dang restore dependencies...'
                bat 'dotnet restore HotelBooking.csproj'
            }
        }

        stage('Build') {
            steps {
                echo 'Dang build project...'
                bat 'dotnet build HotelBooking.csproj --configuration Release --no-restore'
            }
        }

        stage('Unit Test') {
            steps {
                echo 'Dang chay Unit Test...'
                bat 'dotnet test HotelBooking.csproj --configuration Release --no-build --logger "console;verbosity=normal"'
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
```
