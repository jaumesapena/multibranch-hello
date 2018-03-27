node {
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
   stage('Copy') { //COPIAR EL WAR VIA SSH
      sshPublisher(publishers: [sshPublisherDesc(configName: 'wildfly-docker', transfers: [sshTransfer(excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: 'deploy', remoteDirectorySDF: false, removePrefix: 'jts/target', sourceFiles: 'jts/target/jts.war')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
   }
   stage('Deploy') {
     if (isUnix()) {
        //DEPLOY VIA SSH UNIX
        sh 'ssh jboss@172.17.0.3 \'wildfly/bin/jboss-cli.sh --connect --command="deploy --path="deploy/jts.war""\''
      } else {
        //DEPLOY VIA SSH WINDOWS
        bat 'C:\\Users\\jsapena\\Desktop\\git-bash -c ssh docker@192.168.99.100 \'wildfly/bin/jboss-cli.sh --connect --command="deploy --path="deploy/helloworld.war""\''
    }
   }
}
