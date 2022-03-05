pipeline {
    agent any

    stages {
        stage ("Checkout code") {
            steps {
                git url: "https://github.com/virtapp/simple-web.git",
                    // Set your credentials id value here.
                    // See https://jenkins.io/doc/book/using/using-credentials/#adding-new-global-credentials
                    credentialsId: "",
                    // You could define a new stage that specifically runs for, say, feature/* branches
                    // and run only "pulumi preview" for those.
                    branch: "master"
            }
        }

        stage ("Install dependencies") {
            steps {
                sh "cd /tmp/ && rm -rf simple-web"
                sh "helm upgrade simple-web simple-web -n yevgeni --wait"
            }
        }


            }
        }
    }
}
