def repo="https://github.com/virtapp/simple-web.git"
pipeline {
    agent any 
    stages {
        stage("Clone Repository") {
                        steps {
                               sh "cd /tmp/ && rm -rf ${repo} && git clone ${repo}"
			       
                            }
                    }
				stage("Deploy") {
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


