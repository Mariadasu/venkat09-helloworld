#!groovy 

node {
   stage 'Checkout'
        checkout scm

   stage 'Setup'
        sh 'curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -'
		sh 'sudo apt-get install -y nodejs'
		sh 'npm install'

   stage 'Mocha test'
        sh './node_modules/mocha/bin/mocha'

   stage 'Cleanup'
        echo 'prune and cleanup'
        sh 'npm prune'
        sh 'rm node_modules -rf'
}
