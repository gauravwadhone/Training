pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        svn 'https://10.57.127.56/masrepo/ait/uts/uat/lc2'
      }
    }
    stage('test') {
      steps {
        sh '''dir ("lc2"){
        sh "${mvnHome}/bin/mvn clean install -Dportal.url=\'https://10.150.33.100/portal/server\' "
        sh "echo executor.host.name=\\"$NODE_NAME\\" >> target/allure-results/environment.properties"
       
    }'''
        }
      }
    }
  }