def repo="https://github.com/virtapp/simple-web.git"
def path="/tmp/"

pipeline {
    agent any 
    stages {
        stage("Clone Repository") {
                        steps {
                               sh "cd ${path}"
			       sh "rm -rf simple-web"
			       sh "git clone ${repo}"
			       sh "ls -la"
			       
                            }
                    }
				stage("Deploy") {
                        steps {
                            script{
					container(){
				        sh "cd /tmp/"
					sh "df -h"
                                        sh "helm upgrade --install simple-web simple-web -n yevgeni --wait"
                                    }
                                }
                            }
                    }
                
            }
        }


