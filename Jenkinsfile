pipeline {
    agent any
    stages {
        stage('Going To Scan the Repo') {
            steps {
              git 'https://github.com/shaxidevops/sonar-scanning-examples.git'
                script {
                    withDockerContainer(image: 'sonarsource/sonar-scanner-cli:latest') {
                        sh """
                        ./gradlew sonar \
                            -Dsonar.projectKey=Example \
                            -Dsonar.projectName-Example \
                            -Dsonar.sources=. \
                            -Dsonar.host.url=http://192.168.50.188:9000 \
                            -Dsonar.login=admin \
                            -Dsonar.password=admin1234 \
                            -Dsonar.token=sqp_8a73af9132bc79136167fcbf2a24c680e352b179 \
                        """
                    }
                }
            }
        }
    }
}
