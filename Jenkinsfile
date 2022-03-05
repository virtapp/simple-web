node {

    stage('Git Clone') {
        /* This installs helm client */
	{
        sh "cd ${path}"
	sh "rm -rf simple-web"
	sh "git clone https://github.com/virtapp/simple-web.git"
	sh "ls -la"
        }

    }

    stage('Configure helm & add Artifactory repo') {
        /* Configure helm client to point to k8s cluster */
          {
        
           sh "helm -n yevgeni ls"
         }
    }

    stage('Deploy chart pulling from Artifactory') {
        /* Finally, we'll deploy the image to k8s using helm chart. */
        sh "helm upgrade simple-web simple-web -n yevgeni --wait"
    }
}
