pipeline {
  agent any
  tools {
        maven 'maven-3.3.3' 
        jdk 'jdk-1.8.221'
    }
  stages {
    stage('Run') {
      steps {
        script {
          sh 'mvn clean package test -U'
        }
      }
    }
  }
  post {
    success {
      junit '**/target/surefire-reports/TEST-*.xml'
    }
  }
}
