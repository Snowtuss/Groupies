pipeline {
    agent any

    stages {

        stage('Build Back') {
            steps {
                echo 'Building..'   
                 withGradle(){
                    bat '.\\gradlew build'
                }
            }
        }
		stage('Build Front') {
            steps {
				dir('front') {
					echo 'Building..'   
					bat 'npm install'
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

		
    }
}
