job('Git_Pull'){

  description ("This job is for pull the code from jenkins")

   scm {
    github("devopsly12/task6-deploy", "main") 

  }
   triggers {
      scm("* * * * *")
  }
  steps {
  shell('sh cp -rf * ./ ')
  }

  job("2 Check And Deploy") {
  description("This job is for deploying web server")
  
  triggers {
    upstream("Git_Pull")
  }


  steps {
    shell( echo 'deploy the code')

  }
}
buildPipelineView("K8s Deploy WebApp") {
	  title("automating CI/CD pipeline")
	  description("This is build pipeline view for task 6")
	  selectedJob("Git_Pull")
	  alwaysAllowManualTrigger(true)
	  refreshFrequency(33)
	  displayedBuilds(1)
	  showPipelineParameters(true)
}


}