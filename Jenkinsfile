node{
    stage('Checkout'){
        git 'https://github.com/DipenSolanki/pipe1.git'
    }
    stage('Compile'){
        withMaven(jdk: 'JAVA_HOME', maven: 'M2_HOME') {
         sh "mvn compile"
         }
    }
    stage('Unit Testing'){
        withMaven(jdk: 'JAVA_HOME', maven: 'M2_HOME') {
         sh "mvn test"
        }
    }
    stage('Publish Result'){
        junit 'target/surefire-reports/*.xml'
    }
    stage('Package Artifact'){
        withMaven(jdk: 'JAVA_HOME', maven: 'M2_HOME') {
         sh "mvn package"
        }
    }
}
