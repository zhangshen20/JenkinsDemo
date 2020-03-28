// pipeline {

//     agent { 
//         docker { image 'python:3.7' } 
//     }

//     stages {
//         stage('build') {
//             steps {
//                 sh 'python --version'
//                 sh 'echo "hello world"'
//             }
//         }
//     }
// }

// pipeline {
//     agent {
//         docker { image 'node:7-alpine' }
//     }
//     stages {
//         stage('Test') {
//             steps {
//                 sh 'node --version'
//             }
//         }
//     }
// }


// pipeline {
//     agent {
//         label '!windows'
//     }

//     environment {
//         DISABLE_AUTH = 'true'
//         DB_ENGINE    = 'sqlite'
//     }

//     stages {
//         stage('Build') {
//             steps {
//                 echo "Database engine is ${DB_ENGINE}"
//                 echo "DISABLE_AUTH is ${DISABLE_AUTH}"
//                 sh 'printenv'
//             }
//         }
//     }
// }

// pipeline {
//     agent any
//     stages {
//         stage('Test') {
//             steps {
//                 sh './gradlew check'
//             }
//         }
//     }
//     post {
//         always {
//             junit 'build/reports/**/*.xml'
//         }
//     }
// }

pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh './gradlew build'
            }
        }
        stage('Test') {
            steps {
                sh './gradlew check'
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'build/libs/**/*.jar', fingerprint: true
            junit 'build/reports/**/*.xml'
        }
    }
}