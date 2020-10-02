node{

    stage('SCM Checkout')
    {
        git credentialsId: '0d5bf621-8589-4473-9a21-752b05086b20', url: 'https://github.com/vinprak/https-github.com-VardhanNS-phpmysql-app.git'
    }
    
    stage('Run Docker Compose File')
    {
        sh 'docker-compose build'
        sh 'docker-compose up -d'
    }
    stage('PUSH image to Docker Hub')
    {
        withCredentials([string(credentialsId: 'Vinkashi4vin', variable: 'DHPWD')]) 
        {
            sh "docker login -u vinprak -p ${DHPWD}"
        }
        sh 'docker push vinprak/phpmysql_app'
    }
}
