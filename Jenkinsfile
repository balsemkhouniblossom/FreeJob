pipeline {
  agent any
  tools {
    jdk 'JAVA_HOME'
    maven 'M2_HOME'
  }
  environment {
    // Récupérer le token depuis Jenkins (le credential ID "sonarqube-token" doit être configuré dans Jenkins)
    SONAR_TOKEN = credentials('sonarqube-token')
  }
  stages {
    stage('GIT') {
      steps {
        git branch: 'projet', url: 'https://github.com/balsemkhouniblossom/FreeJob.git'
      }
    }
    stage('Compile Stage') {
      steps {
        sh 'mvn clean compile'
      }
    }
    stage('MVN SONARQUBE') {
      steps {
        sh 'mvn sonar:sonar -Dsonar.host.url=http://192.167.33.10:9000 -Dsonar.login=sqa_2ce8c7b0b26806111384d5c23d29d396a3471b1c -Dmaven.test.skip=true'
      }
    }
  }
}
