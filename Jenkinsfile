pipeline {
   tools{
    maven '3.8.5'
  }
  agent any
  stages {

    stage("test"){
    steps{
    sh 'mvn test'

     }
    }


    stage("package") {
      steps{
       sh 'mvn clean install'

      }
    }

    stage("docker run") {
      steps{
//       sh 'java -jar /var/jenkins_home/workspace/oily-mahad-eureka/target/eureka-server.jar'
     sh 'docker-compose ps'
     sh 'docker-compose rm'
     sh 'docker-compose build'
     sh 'docker-compose up -d'

      }
    }
}
}
