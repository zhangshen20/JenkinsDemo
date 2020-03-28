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

pipeline {
    agent {
        docker { image 'node:7-alpine' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
            }
        }
    }
}