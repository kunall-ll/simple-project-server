pipeline {
    agent any

    stages {
        stage('Testing') {
            steps {
                    sh 'mvn test -Dtest=ControllerAndServiceSuite'
	            sh 'mvn test -Dtest=IntegrationSuite'
                }
            }
        stage('Build') {
            steps {
		 sh 'mvn package -DskipTests'
		 sh 'docker build -t="kunall/simple-project:latest" .'
                }
            }
        stage('Deploy') {
            steps {sh 'docker push kunall/simple-project:latest'
}     }   
stage('Testing Environment') {
            steps {
                echo "hello"
            }
        }
        stage('Staging') {
            when{
			expression{ 
		env.BRANCH_NAME == 'developer'}}
	steps{ echo "staging"
        }

        stage('Production') {
            
                when {
		    expression{
			env.BRANCH_NAME == 'master'}}
	    steps{ echo "production"
            }
        }
    
	
            }
        
    

}

