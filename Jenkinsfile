node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("ktos5427/jenkins-flask-example")
         
     }
     stage('Push image') {
         docker.withRegistry('https://registry.hub.docker.com', 'ktos5427') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
}

stage('Build image') {
  app = docker.build("ktos5427/jenkins-flask-example")
}

stage('Push image') {
  docker.withRegistry('https://registry.hub.docker.com', 'ktos5427') 
  {
     app.push("${env.BUILD_NUMBER}")
     app.push("latest")
  }
}

