def repo="https://github.com/virtapp/simple-web.git"
pipeline {
    agent any 
    stages {
        stage("add Repo") {
                        steps {
                               sh "helm repo add simple-web ${repo}"
                            }
                    }
				stage("Deployment") {
                        steps {
                            script{
					container(helm){
                                        sh "helm upgrade --install simple-web virtapp/simple-web -n yevgeni --wait"
                                    }
                                }
                            }
                    }
                
            }
        }


