
node {

    // Checkout Stage
    stage('Checkout') {
        echo 'Checking out source code from GitHub'

        git branch: 'main',
            url: 'https://github.com/sitakameshwari/metroticket.git'
    }

    // Build Stage
    stage('Build') {
        echo 'Building Metro Ticket Reservation System'

        sh 'mvn clean package -DskipTests'
    }

    // Test Stage
    stage('Test') {
        echo 'Executing Unit Test Cases'

        sh 'mvn test'
    }

    // Archive Stage
    stage('Archive') {
        echo 'Archiving generated JAR/WAR files'

        archiveArtifacts artifacts: 'target/*.jar,target/*.war',
                         allowEmptyArchive: false
    }

    echo 'Metro Ticket Pipeline Executed Successfully'
}
