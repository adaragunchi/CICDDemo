node {
    def mvnHome
    stage('Checkout') {
        git credentialsId: '4377ffa5-fed3-4606-aebb-f891fdbe0802',
                url: 'https://github.com/adaragunchi/CICDDemo.git'
    }
    stage('Build') {
        withMaven(maven: 'M2_HOME') {
            mvn -B -DskipTests clean install
        }
    }
    stage('CF Push'){
           cf login -a api.run.pivotal.io --skip-ssl-validation -u adaragunchi@gmail.com -p Puma@328
           cf push
     }
}