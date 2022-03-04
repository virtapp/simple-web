def repo="https://github.com/virtapp/simple-web.git"
pipeline {
    agent any 
    stages {
        stage("add Repo") {
                        steps {
                               sh "cd /tmp/ && git clone ${repo}"
			       
                            }
                    }
				stage("Deployment") {
                        steps {
                            script{
					container(){
                                        sh "helm upgrade --install simple-web simple-web -n yevgeni --wait"
                                    }
                                }
                            }
                    }
                
            }
        }


