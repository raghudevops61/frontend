//@Library('roboshop') _
//
//// Variables
//env.COMPONENT = "frontend"
//env.BUILD_LABEL = "WORKSTATION"
//
//// Library Groovy file
//immutable_nginx()

pipeline {
  agent any

  triggers { pollSCM('H/2 * * * *') }

  stages {
    stage('Stage for Main Branch') {
      steps {
        echo 'Steps for Main Branch'
      }
    }
    stage('Stage for Tag') {
      when {
        expression { sh([returnStdout: true, script: 'echo ${GIT_BRANCH} | grep tags || true' ]) }
      }
      steps {
        echo 'Steps for Tag'
      }
    }
  }
}
///
