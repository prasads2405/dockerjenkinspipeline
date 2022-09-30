node {
  def app
  stage('Build image') {
    app = docker.build("prasad2405/mydockerimage")
  }
  stage('Push image') {
    docker.withRegistry('https://registry.hub.docker.com','cc96d1f7-19b5-4058-ba54-1fe0219912a0') {
      app.push("${env.BUILD_NUBER}")
      app.push("latest")
    }
  }
}
