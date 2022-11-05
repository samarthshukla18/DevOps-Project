node {
	stage('SCM Checkout') {		
		echo 'checkout stage started'
		git 'https://github.com/samarthshukla18/DevOps-Project.git'
		echo 'checkout stage completed'			
	}
	stage('Compile Stage') {		
		echo 'compile stage started'
		def mvnHome = tool name: 'maven-3-8-6', type: 'maven'
		bat "${mvnHome}/bin/mvn clean compile"
		echo 'compile stage completed'			
	}
	stage('Test Stage') {		
		echo 'test stage started'
		def mvnHome = tool name: 'maven-3-8-6', type: 'maven'
		bat "${mvnHome}/bin/mvn test"
		echo 'test stage completed'			
	}
	stage('SonarQube Stage') {		
		echo 'sonarqube stage started'
		withSonarQubeEnv(installationName: 'sonarqube-server') {
			sh './mvnw clean org.sonarsource.scanner.maven:sonar-maven-plugin:3.9.0.2155:sonar'
		}
	}
	stage('Deploy Stage') {		
		echo 'deploy stage started'
		def mvnHome = tool name: 'maven-3-8-6', type: 'maven'
		bat "${mvnHome}/bin/mvn install"
		echo 'deploy stage completed'			
	}
}
