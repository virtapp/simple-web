def repo="https://github.com/virtapp/simple-web.git"
pipeline {
    agent any 
    stages {
        stage("Clone Repository") {
                        steps {
                               sh "cd /tmp/ && sudo rm -rf ${repo} && git clone ${repo}"
			       sh "df -h"
			       
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


