pipelines{
  agents any
  stages{
    stage("Build"){
      echo "Building..."
    }
    post{
      success{
        mail to: "sakifhasan.work@gmail.com"
        subject: " Jenkins Build Status "
        body: " Build was successful "
      }
    }
  }
}
}
      
