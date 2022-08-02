pipeline {
  agent any
  stages {
    stage('Fetch code from github') {
      steps {
        git(url: 'https://github.com/bhagyashri-cj/demojenkin.git', branch: 'main', poll: true)
      }
    }

    stage('install and start apache') {
      steps {
        sh '''sudo apt-get install apache2 -y
sudo service apache2 start'''
      }
    }

    stage('Deploy the code') {
      steps {
        sh 'sudo cp -R * /var/www/html/'
      }
    }

  }
}