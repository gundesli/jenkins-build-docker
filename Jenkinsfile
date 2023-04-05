
node {

  
   def IMAGE="srv-web"
	
    stage('Clone') {
          checkout scm
    }

    def img = stage('Build') {
          docker.build("$IMAGE",  '.')
    }

    stage('Run image') {
        docker.image('$IMAGE').withRun('-p 800:80 --name $IMAGE' ) { c ->

        sh 'docker ps | grep $IMAGE'
      }

    }
}
