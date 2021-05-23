node {
    stage ('Clean WS'){
        sh 'echo "Cleaning Workspace"'
        cleanWs();
    }
    stage ("Declarative Checkout"){
        checkout scm;
    }
    stage ('Compile'){
        withMaven(jdk: "jdk11", maven: "maven3"){
            sh 'mvn compile'
        }
    }
    stage ('Test'){
        withMaven(jdk: "jdk11", maven: "maven3"){
            sh 'mvn test'
        }
    }
    stage ('Package'){
        withMaven(jdk: "jdk11", maven: "maven3"){
            sh 'mvn package'
        }
    }
}