node {
    def app

    stage('Clone repository') {
        /* Let's make sure we have the repository cloned to our workspace */

        checkout scm
    }
	
	stage('Clean up') {
		sh 'docker rm $(docker stop $(docker ps -a -q --filter ancestor=friendlyhello --format="{{.ID}}"))'
	
	}

    stage('Build image') {
        /* This builds the actual image; synonymous to
         * docker build on the command line */

        app = docker.build("friendlyhello")
    }

    stage('Run image') {
        /* Ideally, we would run a test framework against our image.
         * For this example, we're using a Volkswagen-type approach ;-) */

        sh 'docker run -d -p 4000:80 friendlyhello'
		sh 'curl http://localhost:4000/'
    }
}