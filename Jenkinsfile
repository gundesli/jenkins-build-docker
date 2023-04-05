
node {

  
   def IMAGE="srv-web"
	
    stage('Clone') {
          checkout scm
    }

    def img = stage('Build') {
          docker.build("$IMAGE",  '.')
    }

    stage('Run image') {
        docker.image('srv-web').withRun('-p 800:80 --name srv-web' ) { c ->

        sh 'docker ps | grep srv-web'
      }

    }
}
