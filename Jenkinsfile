#!groovy 

node {
   stage 'Checkout'
        checkout scm

   stage 'Setup'
        sh 'sudo -S yum install gcc-c++ make'
		sh 'curl --silent --location https://rpm.nodesource.com/setup_6.x | sudo bash -'
		sh 'sudo yum install -y nodejs'
		sh 'sudo npm install'

   stage 'Mocha test'
        sh './node_modules/mocha/bin/mocha'

   stage 'Cleanup'
        echo 'prune and cleanup'
        sh 'npm prune'
        sh 'rm node_modules -rf'
}
