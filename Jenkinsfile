pipeline {
    agent any

    tools {nodejs "node"}

    environment {
        CHROME_BIN = '/bin/google-chrome'
    }

    stages {
        stage('Dependencies') {
            steps {
                sh 'npm i'
            }
        }
        stage('Build') {
            steps {
                sh 'node -v'
                sh 'npm run build'
            }
        }
        // stage('Unit Tests') {
        //     steps {
        //         sh 'npm run test'
        //     }
        // }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }

    post {
        always {
            junit 'results/cypress-report.xml'
        }
    }
}

// pipeline {
//     agent any

//     tools {nodejs "node"}

//     environment {
//         CHROME_BIN = '/bin/google-chrome'
//     }

//     stages {
//         stage('Dependencies') {
//             steps {
//                 sh 'npm i'
//             }
//         }
//         stage('e2e Tests') {
//             steps {
//                 sh 'npm run cypress:run'
//             }
//         }
//     }

//     post {
//         always {
//             junit 'results/cypress-report.xml'
//         }
//     }
// }
