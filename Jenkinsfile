node {

    stage('Initialize'){
        def dockerHome = tool 'localDocker'
        def mavenHome = tool 'localMaven'
        env.PATH = "${dockerHome}/bin:${mavenHome}/bin:${env.PATH}"
        echo "Environment Path: {env.PATH}"
    }

    stage('Checkout') {
        checkout scm
    }

    stage('Build') {
        echo 'Building....'
    }
    stage('Test') {
        echo 'Building....'
    }
    stage('Deploy') {
        echo 'Deploying....'
    }
}