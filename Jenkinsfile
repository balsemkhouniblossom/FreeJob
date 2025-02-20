pipeline {
  agent any
  tools {
    jdk 'JAVA_HOME'
    maven 'M2_HOME'
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
   stage('SonarQube Analysis') {
            steps {
                sh 'mvn sonar:sonar -Dsonar.token=sqa_2ce8c7b0b26806111384d5c23d29d396a3471b1c -Dmaven.test.skip=true';
            }

    }
  }
}
