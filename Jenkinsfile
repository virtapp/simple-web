def repo="https://github.com/virtapp/simple-web.git"
pipeline {
    agent any 
    stages {
        stage("Clone Repository") {
                        steps {
                               sh "cd /tmp/ && rm -rf ${repo}"
			       sh "git clone ${repo}"
			       sh "ls -ls"
			       
                            }
                    }
				stage("Deploy") {
                        steps {
                            script{
					container('helm'){
                                        sh "helm upgrade --install simple-web simple-web -n yevgeni --wait"
                                    }
                                }
                            }
                    }
                
            }
        }


