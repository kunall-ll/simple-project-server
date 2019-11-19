pipeline {
    agent any

    stages {
        stage('Testing Environment') {
            steps {
                    sh 'mvn test -Dtest=ControllerAndServiceSuite'
                }
            }
        stage('Build') {
            steps {
		 sh 'mvn package -DskipTests'
                }
            }
        stage('Deploy') {
            steps {
		echo "Deploy"
            }
        }
    }
}

