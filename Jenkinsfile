node {
    stage ('Clean WS'){
        sh 'echo "Cleaning Woekspace"'
        cleanWs();
    }
    stage ("Declarative Checkout"){
        checkout scm;
    }
    stage ("Compile"){
        withMaven(jdk: "jdk11", maven: "maven3"){
            sh 'mvn compile'
            sh 'echo "successful"'
        }
    }
    stage ("Test"){
        withMaven(jdk: "jdk11", maven: "maven3"){
            sh 'mvn package'
        }
    }
}