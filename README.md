# Gitlab CI/CD pipeline practice

1. Set the Docker python image that should be used for the build environment to run Python code 
2. Set a variable for USERNAME and PASSWORD in Settings - CI/CD - Variables. Variable can be used in any of the jobs in the pipeline.
3. Set 3 stages of the pipeline in the order that they should be executed. 
4. build-job runs in the build stage. The script section contains the commands that should be executed during the job. It compiles the code and creates a binary like file called binary-file-v1 in the build directory. 
5. The artifacts section tells GitLab to store this file as an artifact so that it can be used in later jobs.
6. Test stage depends on the build-job job, so it won't start until that job is complete. (same with lint-test-job)
7. deploy-job runs in the deploy stage. It depends on both the unit-test-job and lint-test-job jobs, so it won't start until those jobs are complete. 
This job potentially deploys the application to a production environment and outputs some information about the deployment, including the Python version being used and the credentials being used.