pipeline {
  agent any
tools {
  jdk 'java8'
  maven 'maven'
}
 stages {
         agent {
    label 'tomcatserver'
  }
  stage('build') {
    steps {
      bat 'mvn clean package -DskipTests=true'
    }
  }

  stage('deploy') {
      agent {
    label 'tomcatserver'
  }
    
    steps {
                      sh 'cp target/*.war /home/ec2-user/apache-tomcat-9.0.63/webapps/'
    }
  }
} 
}
