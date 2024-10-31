node {
  def app
    stage('Clone') {
        checkout scm
    }
    stage('Build image') {
        app = docker.build("murielle/nginx")
    }
    stage('Run image') {
    docker.image('murielle/nginx').withRun('-p 8081:80') { c->
    sh 'docker ps'
    sh 'curl localhost'
    }
    }
}
