node {
    stage('Initialize'){
        def dockerHome = tool 'localDocker'
        def mavenHome = tool 'localMaven'
        env.PATH = "${dockerHome}/bin:${mavenHome}/bin:${env.PATH}"
        echo "Environment Path: ${env.PATH}"
    }
    stage('Checkout') {
        checkout scm
    }
    stage('Build') {
        echo 'Building....'
        sh 'mvn --version'
    }
    stage('Test') {
        echo 'Building....'
        sh 'mvn check || true'
        junit '**/target/*.xml'

    }
    stage('Deploy') {
        echo 'Deploying....'
        echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
        if (currentBuild.result == null || currentBuild.result == 'SUCCESS') {
            sh 'make publish'
        }
    }
}