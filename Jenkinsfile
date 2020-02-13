pipeline {
  agent any
  tools {
        maven 'maven-3.3.3' 
        jdk 'jdk-1.8.221'
    }
  stages {
    stage('Build') {
      steps {
        script {
          sh 'mvn clean package -U -Dmaven.test.failure.ignore'
        }
      }
    }
  }
  post {
    success {
      junit testResults:'**/target/surefire-reports/TEST-*.xml', allowEmptyResults: true
    }
  }
}
