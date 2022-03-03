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
                                        sh "helm upgrade --install simple-web virtapp/simple-web --values dev/values.yaml -n yevgeni --wait"
                                    }
                                }
                            }
                    }
                stage("Deploy to UAT") {
                        steps {
                            script{
					container(){
                                        sh "helm upgrade --install helm-app shailendra/sample-app --values uat/values.yaml -n uat --wait"
                                    }
                                }
                            }
                    }
            }
        }
