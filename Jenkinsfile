pipeline {
     agent any
     stages {
        stage("Build") {
            steps {
                sh "chown -R jenkins:jenkins node_modules"
                sh "sudo npm install"
                sh "sudo npm run build"
            }
        }
        stage("Deploy") {
            steps {
                sh "sudo rm -rf /var/www/react-app"
                sh "sudo cp -r ${WORKSPACE}/build/ /var/www/react-app/"
            }
        }
    }
}