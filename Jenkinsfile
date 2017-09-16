#!groovy 

node {
   stage 'Checkout'
        checkout scm

   stage 'Setup'
        sh 'sudo curl --silent --location https://rpm.nodesource.com/setup_6.x | sudo bash -'
		sh 'sudo yum -y install nodejs'
		sh 'sudo npm install -g grunt --save-dev'
        sh 'sudo npm install'

   stage 'Mocha test'
        sh 'sudo npm init --yes'
		sh 'sudo npm install mocha --save-dev'
        sh './node_modules/mocha/bin/mocha'

   stage 'Cleanup'
        echo 'prune and cleanup'
        sh 'npm prune'
        sh 'rm node_modules -rf'
}
