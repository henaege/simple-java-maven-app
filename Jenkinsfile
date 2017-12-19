pipeline {
<<<<<<< HEAD
    agent any
=======
    agent {
        docker {
			image 'maven:3-alpine'
			args '-v /root/.m2:/root/.m2'
		}
	}
>>>>>>> d608e42acc84d370b5b9b9aa1c27373589e9816c
	stages {
		stage('Build') {
			steps {
				sh 'mvn -B -DskipTests clean package'
			}
		}
		stage('Test') {
			steps {
				sh 'mvn test'
			}
			post {
				always {
					junit 'target/surefire-reports/*.xml'
				}
			}
		}
		stage('Deliver') {
			steps {
				sh './jenkins/scripts/deliver.sh'
			}
		}
	}
}