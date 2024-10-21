pipeline {

agent {label 'server1'}

stages {
     
     stage ('Build') {

        steps{
            echo "We are into Building Stage"
        }
     }

     stage ('test') {
        steps {
            echo " We are now into testing stage"
        }
     }

     stage ('deploy') {

        steps {
            echo "We are Finally reached to Deploy Stage, Bingoooo"
        }
     }

}

}