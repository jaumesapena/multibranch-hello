node {
  checkout scm
  def workspace = pwd()

  if (env.BRANCH_NAME == 'master') {
    stage ('Some Stage 1 for master') {
      //sh 'do something'
    }
  }

  else if (env.BRANCH_NAME == '8.x') {
    stage ('Some stage branch step') {
      def mvnHome
	stage('Preparation') {
      git 'https://github.com/wildfly/quickstart.git'
      mvnHome = tool 'maven jenkins'
	}
	stage('Build') {
      if (isUnix()) {
        sh "'${mvnHome}/bin/mvn' -f jts -Dmaven.test.failure.ignore clean package"
      } else {
        bat(/"${mvnHome}\bin\mvn" -f jts -Dmaven.test.failure.ignore clean package/)
      }
    }
  }
  
  else if (env.BRANCH_NAME == '9.x') {
    stage ('Some stage branch step') {
      //sh 'do something'
    }
  }
  
  else if (env.BRANCH_NAME == '10.x') {
    stage ('Some stage branch step') {
     // sh 'do something'
    }
  }
  
  else if (env.BRANCH_NAME == '11.x') {
    stage ('Some stage branch step') {
      //sh 'do something'
    }
  }
  
  else if (env.BRANCH_NAME == '12.x') {
    stage ('Some stage branch step') {
      //sh 'do something'
    }
  }

  else {
    sh 'echo "Branch not applicable to Jenkins... do nothing"'
  }
}
