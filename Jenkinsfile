pipeline {
    agent any

    stages {
        stage('Fetch') {
            steps {
            deleteDir()
            echo "test fetch"
                   git branch: 'main', credentialsId: 'c225e912-8f08-4a7c-93c1-22c60f76361d', url: 'https://github.com/mantasmacionis/jenkinsproject'
            }
        }

        stage('Build') {
            steps {
                echo "Building the Java project"
                    bat 'javac -d src/Student.java src/StudentTest.java -cp lib/junit-platform-console-standalone-1.9.3.jar'

            }
        }

        stage('Test') {
            steps {
            echo "test check "
                    bat 'java -jar lib/junit-platform-console-standalone-1.9.3.jar --class-path bin --select-class StudentTest'
            }
        }
    }
}