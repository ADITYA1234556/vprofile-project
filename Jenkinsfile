pipeline {
    agent any
    tools {
        maven "MAVEN3"
        jdk "OracleJDK8"
    }
    environment {
        SNAP_REPO = 'vprofile-snapshot'
        RELEASE_REPO = 'vprofile-release'
        NEXUS_GRP_REPO = 'vpro-maven-group'
        CENTRAL_REPO = 'vpro-maven-central'
        NEXUSIP = '192.168.10.12'
        NEXUSPORT = '8081'
        NEXUS_USER = 'admin'
        NEXUS_PASS = 'admin'
        NEXUS_LOGIN = 'nexuslogin'
    }

    stages{
        stage('BUILD'){
            steps{
                sh 'mvn -s settings.xml -DskipTests install'
            }
            post {
                success{
                    echo "Now Archiving"
                    archiveArtifacts artifacts: '**/*.war'
                }
            }
        }

        stage('TEST'){
            steps{
                sh 'mvn test'
            }
        }

        stage('CHECKSTYLE ANALYSIS'){
            steps {
                sh 'mvn checkstyle:checkstyle'
            }
        }


    }
}










































