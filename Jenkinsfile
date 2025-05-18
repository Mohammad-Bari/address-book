pipeline {
	agent {label 'linux_agent'}
	tools{
		maven 'mymaven'
	}
	stages{
		stage('cloning git project'){
			steps{
				echo "project cloning....."
				git branch: 'master',
				    url: 'https://github.com/Mohammad-Bari/address-book.git'
			}
		}
		stage('test roject...'){
			steps{
				echo "testing ...."
				sh 'mvn test'
			}
		}
		stage('build project'){
		      steps{
			      echo "buiding the project..."
			      sh 'mvn package'
		      }
		}
		stage('deploy in tomcat'){
			steps{
				echo "aplication deploying...."
			deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcat_credentials', path: '', url: 'http://13.126.176.182:9090/')], contextPath: null, war: '**/*.war'
			}
			
		}
		stage('email notification'){
			steps{
				echo "notification..."
				emailext attachLog: true, body: 'Hi, check the error', subject: 'notification', to: 'nooraliulbari@gmail.com'
			}
		}
	}
	
}
