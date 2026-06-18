pipeline{
  agent any
  stages{
    stage ('Create'){
      steps{
        sh 'echo "devsecops"'
        sh 'mkdir -p /tmp/web && cd /tmp/web && git clone git@github.com:belutooth/devsecops.git'
        sh 'echo "build devsecops"'
        sh 'docker build -t bootstrap:1.0'
        sh 'echo "build di port 9090."'
        sh 'docker run -itd --name bootstrap-web -p 9090:80 bootstrap:1.0'
      }
    }
  }
}
