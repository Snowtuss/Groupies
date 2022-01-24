pipeline {
    agent any

    stages {
		stage('Build Front') {
            steps {
                echo 'Building..'   
				bat 'cd front'
				bat 'npm package-lock'
				bat 'npm start'
            }
        }
        stage('Build Back') {
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
