pipeline{
  agent any
  tools{
    maven 'Maven-3'
  }
  parameters{
    choice(name:'MyVersion', choices:['1.1','1.2','1.3'], description:'Choose the version')
    booleanParam(name:'ConditionExecute', defaultValue:'true', description:'Executes stages based on condition')
  }
  stages{
    stage("Build"){
      steps{
        echo 'Hello'
      }
    }
    stage("Test"){
      when{
          expression{
            params.ConditionExecute
          }
      }
      steps{
        echo "testing the   version ${params.MyVersion}"
      }
    }
    stage("Deploy"){
      steps{
        echo 'Deploying'
      }
    }
  }
}

    
