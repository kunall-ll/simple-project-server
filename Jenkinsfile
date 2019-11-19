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
		 sh 'mvn package -DshipTests'
                }
            }
        stage('Deploy') {
            steps {
		echo "Deploy"
            }
        }
    }
}

