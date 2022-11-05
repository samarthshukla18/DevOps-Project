node {
	stage('SCM Checkout') {		
		echo 'checkout stage started'
		git branch: 'main', url: 'https://github.com/samarthshukla18/DevOps-Project.git'
		echo 'checkout stage completed'			
	}
	stage('Compile Stage') {		
		echo 'compile stage started'
		echo 'compile stage completed'			
	}
	stage('Test Stage') {		
		echo 'test stage started'
		echo 'test stage completed'			
	}
	stage('SonarQube Stage') {		
		withSonarQubeEnv('sonarqube-server'){
				sh "mvn sonar:sonar"
			}
	}
	stage('Deploy Stage') {		
		echo 'deploy stage started'
		echo 'deploy stage completed'			
	}
}
