pipeline {
  agent any
tools {
  jdk 'java8'
  maven 'maven'
}
 stages {
  stage('build') {
    steps {
      bat 'mvn clean package -DskipTests=true'
    }
  }

  stage('deploy') {
    steps {
                      bat 'copy C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\Springboot_pipeline\\target\\*.war "C:\\Program Files\\Apache Software Foundation\\Tomcat 10.0\\webapps\\"'
    }
  }
} 
}
