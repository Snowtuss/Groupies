pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'   
                 withGradle(){
                    bat '.\\gradlew build'
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                withGradle(){
                    bat '.\\gradlew test'
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
