pipeline {
environment {
registry = "abaliyoussef/tp4"
registryCredential = 'myhub'
dockerImage = ''
}
agent any
stages {
stage('Cloning Git') {
steps {
git 'https://github.com/Abali-Youssef/TP4-Devops'
}
}
stage('Building image') {
steps{
script {
dockerImage = docker.build registry + ":$BUILD_NUMBER"
}
}
}
stage('Test image') {
steps{
script {
echo "Tests passed" }
}
}
stage('Publish Image') {
steps{
script {
docker.withRegistry( '', registryCredential ) {
dockerImage.push()
}}}}}}