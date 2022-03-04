def repo="https://github.com/virtapp/simple-web.git"
pipeline{
		agent{
			label 'helm'
		}
		stages{
				
                stage("add Repo") {
                        steps {
                               sh "helm repo add simple-web ${repo}"
                            }
                    }
				stage("Deploy to Dev") {
                        steps {
                            script{
					container(){
                                        sh "helm upgrade --install simple-web virtapp/simple-web -n yevgeni --wait"
                                    }
                                }
                            }
                    }
                
            }
        }
