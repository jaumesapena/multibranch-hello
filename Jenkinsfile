node {
  checkout scm
  def workspace = pwd()

  if (env.BRANCH_NAME == 'master') {
    stage ('Some Stage 1 for master') {
      sh 'echo Hola'
    }
    stage ('Another Stage for Master') {
      sh 'do something else here'
    }
  }
}