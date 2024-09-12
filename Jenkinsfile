pipeline {
    agent any
    tools {
        maven "MAVEN3"
        jdk "OracleJDK8"
    }
    environment {
        SNAP-REPO = 'vprofile-snapshot'
        RELEASE-REPO = 'vprofile-release'
        NEXUS-GRP-REPO = 'vpro-maven-group'
        CENTRAL-REPO = 'vpro-maven-central'
        NEXUSIP = '192.168.10.12'
        NEXUSPORT = '8081'
        NEXUS-USER = 'admin'
        NEXUS-PASS = 'admin'
        NEXUS-LOGIN = 'nexuslogin'
    }

    stages{
        stage('BUILD'){
            steps{
                sh 'mvn -s settings.xml -DskipTests install'
            }
        }

    }
}










































