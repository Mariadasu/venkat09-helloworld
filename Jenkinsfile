#!groovy 

node {
   stage 'Checkout'
        checkout scm

   stage 'Setup'
        sh 'sudo wget -qO https://deb.nodesource.com/setup_6.x'
		sh 'sudo apt-get install -y nodejs'
		sh 'sudo npm install'

   stage 'Mocha test'
        sh './node_modules/mocha/bin/mocha'

   stage 'Cleanup'
        echo 'prune and cleanup'
        sh 'npm prune'
        sh 'rm node_modules -rf'
}
