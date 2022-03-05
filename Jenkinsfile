pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                echo 'Hello world, this is multibranch pipeline for Dev branch'
		sh "cd /tmp/ && rm -rf simple-web"
		sh "git clone https://github.com/virtapp/simple-web.git"
            }
        }
        stage('test') {
            steps {
                echo 'testing'
		sh "df -h"
		
            }
        }
        stage('deploy') {
            steps {
                echo 'deploy'
		script{
		sh "helm upgrade simple-web simple-web -n yevgeni --wait"
            }
        }
    }
}
