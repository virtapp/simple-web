def repo="https://github.com/virtapp/simple-web.git"
def path="/tmp/"
pipeline {
    agent any 
    stages {
        stage("Clone Repository") {
                        steps {
                               sh "cd ${path}"
			       sh "sudo rm -rf ${repo}"
			       sh "sudo git clone ${repo}"
			       sh "ls -ls"
			       
                            }
                    }
				stage("Deploy") {
                        steps {
                            script{
					container(){
				        sh "cd /tmp/"
                                        sh "helm upgrade --install simple-web simple-web -n yevgeni --wait"
                                    }
                                }
                            }
                    }
                
            }
        }


