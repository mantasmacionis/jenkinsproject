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
                bat 'javac -d C:\\Users\\35387\\.jenkins\\workspace\\jenkinsca\\Jenkinsproject\\out\\production\\jenkinsproject C:\\Users\\35387\\.jenkins\\workspace\\jenkinsca\\Jenkinsproject\\src\\Student.java C:\\Users\\35387\\.jenkins\\workspace\\jenkinsca\\Jenkinsproject\\src\\StudentTest.java -cp C:\\Users\\35387\\.jenkins\\workspace\\jenkinsca\\Jenkinsproject\\lib\\junit-platform-console-standalone-1.9.3.jar'
            }
        }

        stage('Test') {
            steps {
             echo "Running tests"
             bat 'java -cp C:\\Users\\35387\\.jenkins\\workspace\\jenkinsca\\Jenkinsproject\\out\\production\\jenkinsproject;C:\\Users\\35387\\.jenkins\\workspace\\jenkinsca\\Jenkinsproject\\lib\\junit-platform-console-standalone-1.9.3.jar org.junit.platform.console.ConsoleLauncher --class-path out/production/jenkinsproject --select-class StudentTest'
            }
        }
    }
}