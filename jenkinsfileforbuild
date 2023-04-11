pipeline {
    agent none
    stages {
        stage('vcs') {
            agent { label 'GIT' }
            steps { 
                sh 'git --version'
            }
        }
        stage('build') {
            agent { label 'MAVEN || MAVEN_JDK8' }
            steps {
                sh 'mvn --version'
        }
        stage('deploy') {
            agent { label 'k8s && developer' }
            steps {
                sh 'kubectl --version'
            }
        }
    }

}
