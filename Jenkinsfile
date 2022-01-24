pipeline {
    agent any

    stages {
		stage('Build Front') {
            steps {
				dir('front') {
					echo 'Building..'   
					bat 'rm -rf node_modules && npm install'
					bat 'npm start'
				}

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
