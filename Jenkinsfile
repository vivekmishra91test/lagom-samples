
node {
    stage('SBT compile*****') {
      sh "cd ./shopping-cart/shopping-cart-scala"
        sh "pwd"
  sh "/usr/lib/jvm/java-11-openjdk-amd64/bin/java -jar /home/mishra/sbt-dist/bin/sbt-launch.jar clean compile"
  sh "pwd"
  }
  stage('SCM') {
    checkout scm
      sh "pwd"
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'SonarScanner';
      sh "pwd"
    withSonarQubeEnv() {
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}
