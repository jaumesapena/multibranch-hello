node {
  checkout scm
  def workspace = pwd()
  def mvnHome
	
	stage('Preparation') {
      		git 'https://github.com/wildfly/quickstart.git'
      		mvnHome = tool 'maven jenkins'
	}
	stage('Build') {
      		if (isUnix()) {
        		sh "'${mvnHome}/bin/mvn' -f helloworld -Dmaven.test.failure.ignore clean package"
      		} else {
        		bat(/"${mvnHome}\bin\mvn" -f helloworld -Dmaven.test.failure.ignore clean package/)
      		}
	}
  }
