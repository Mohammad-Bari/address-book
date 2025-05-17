pipeline {
	agent any
	tools{
		maven 'mymaven'
	}
	stages{
		stage('cloning git project'){
			steps{
				echo "project cloning....."
				git branch: 'master'
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
	}
	
}
