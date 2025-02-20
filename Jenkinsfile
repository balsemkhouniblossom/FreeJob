pipeline {

 agent any

 tools {jdk 'JAVA_HOME'
        maven 'M2_HOME'}

 stages {

 stage('GIT') {

           steps {

               git branch: 'projet',

               url: 'https://github.com/balsemkhouniblossom/FreeJob.git'

          }

     }

 stage ('Compile Stage') {

 steps {

 sh 'mvn clean compile'

 }

 }
 stage('MVN SONARQUBE'){
  steps {
   sh 'mvn sonar:sonar -Dsonar.login=admin -Dsonar.password=balsemKHOUNI@123 -Dmaven.test.skip=true';
  }
 }

 }

}

