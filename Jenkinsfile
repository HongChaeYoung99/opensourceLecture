node {
def app
stage('Clone repository') {
        git 'https://github.com/HongChaeYoung99/opensourceLecture.git'
    }
stage('Build image') {
app = docker.build("h3088/test")
}
stage('Test image') {
app.inside {
sh 'make test'
} }
stage('Push image') { docker.withRegistry('https://registry.hub.docker.com', 'h3088') {
           app.push("${env.BUILD_NUMBER}")
app.push("latest") }
} }
