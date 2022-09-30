node {
  def app
  def myImg
  checkout scm
  stage('Build image') {
    app = docker.build("prasad2405/mydockerimage")
  }
  stage('Push image') {
    docker.withRegistry('https://registry.hub.docker.com','cc96d1f7-19b5-4058-ba54-1fe0219912a0') {
      app.push("${env.BUILD_NUMBER}")
      app.push("latest")
    }
  }
  stage('Pull image') {
    docker.withRegistry('https://registry.hub.docker.com','cc96d1f7-19b5-4058-ba54-1fe0219912a0') {
      myImg = docker.image("prasad2405/mydockerimage:${env.BUILD_NUMBER}")
      myImg.inside {
        sh "cat /etc/lsb-release"
      }
    }
  }
}
