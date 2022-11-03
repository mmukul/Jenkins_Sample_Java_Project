pipeline {
    agent any
    tools { 
      maven 'MAVEN_HOME' 
      /*jdk 'JAVA_HOME'*/ 
    }

    stages {
        stage('Get Latest Code') {
            steps {
                echo 'Get Latest Code'
                git 'https://github.com/mmukul/Jenkins_Sample_Java_Project.git'
            }
        }
		stage('Clean the Workspace') {
            steps {
                echo 'Clean the Workspace'
                sh "mvn clean"
            }
        }
		stage('Compile') {
            steps {
                echo 'Compile'
                sh "mvn clean compile"
            }
        }
		stage('Test') {
            steps {
                echo 'Test'
                sh "mvn clean compile test"
				
            }
        }
		stage('Package the Solution') {
            steps {
                echo 'Package the Solution'
                sh "mvn clean compile package"
            }
        }
		stage('Deploy to PROD') {
            steps {
                input 'Do you want to continue deployment to PROD?'
		echo 'Deploy to PROD'
				
            }
        }
		
    }
}
