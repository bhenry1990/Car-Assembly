pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // sh 'rm -rf build'
                bat 'rd /s /q "build"'
                // sh 'mkdir build'
                bat 'mkdir build'
                // sh 'touch build/car.txt'
                bat 'echo.> build/car.txt'
                // sh 'echo "chassis" > build/car.txt'
                bat 'echo chassis >> build/car.txt'
                bat 'echo engine >> build/car.txt'
                bat 'echo body >> build/car.txt'
            }
        }
        stage('Test') {
            steps {
                // sh 'test -f build/car.txt'
                bat 'if exist "build/car.txt" (echo File exist) else (echo File not exist)' 
                // sh 'grep "chassis" build/car.txt'
                bat 'find /i "chassis" build/car.txt'
                bat 'find /i "engine" build/car.txt'
                bat 'find /i "body" build/car.txt'
            }
        }
        stage('Publish') {
            steps {
                archiveArtifacts artifacts: 'build/'
            }
        }
    }
}
