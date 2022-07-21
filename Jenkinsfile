pipeline {
  agent any
tools {
  jdk 'java8'
  maven 'maven'
}
 stages {

  stage('build') {
    steps {
      sh 'mvn clean package -DskipTests=true'
    }
  }

  stage('deploy') {
     timeout(time: 600, unit: 'SECONDS') {
     input message: 'Waiting for Deployment approval', ok: 'Approve', submitter: 'admin', submitterParameter: 'approved_users'
  }
    steps {
       sh 'cp target/*.war /opt/apache-tomcat-9.0.63/webapps/'
    }
  }
} 
}
