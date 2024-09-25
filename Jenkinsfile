pipeline{

	agent any
	stages{
		stage('Fetching code from github')
		{
			steps{
                     git 'https://github.com/sagarrajput2111/Maven-build-jenkins.git'			}
		}
		stage('generating artifacts')
		{
			steps{
		   sh 'mvn clean install'
			}
		}
		stage('deploying code to tomcat')
		{
			steps{
		   deploy adapters: [tomcat9(credentialsId: 'tomcatcreds', path: '', url: 'http://20.197.32.111:8081/')], contextPath: null, war: '**/*war'
			}
		}
	}
	
}
