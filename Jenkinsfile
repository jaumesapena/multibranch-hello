node {
  checkout scm
  def workspace = pwd()

  if (env.BRANCH_NAME == 'master') {
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

  else if (env.BRANCH_NAME == '8.x') {
    stage ('Imprimir MASTER') {
      echo '8.x'
    }
  }
  
  else if (env.BRANCH_NAME == '9.x') {
    stage ('Imprimir MASTER') {
      echo '9.x'
    }
  }
  
  else if (env.BRANCH_NAME == '10.x') {
    stage ('Imprimir MASTER') {
      echo '10.x'
    }
  }
  
  else if (env.BRANCH_NAME == '11.x') {
    stage ('Imprimir MASTER') {
      echo '11.x'
    }
  }
  
  else if (env.BRANCH_NAME == '12.x') {
    stage ('Imprimir MASTER') {
     echo '11.x'
    }
  }

  else {
    sh 'echo "Branch not applicable to Jenkins... do nothing"'
  }
}
