# CircleCI
This repository is where we store templates and examples relevant to CircleCI. 


##### Templates
- Base Maven Template - This is an example of a CircleCI Yaml file with a base workflow for projects using Maven 
- Base Gradle Template - This is an example of a CircleCI Yaml file with a base workflow for projects using Gradle
- Both feature the same base steps outlined as follows:
  * **inc_build** - incremental build for PR branches
  * **full_build** - full build for master branch
  * **test** - run tests, put build artifacts into directory for CircleCI to use for Test Summary page (can be included as a step in either build jobs above)
  * **owasp** - runs OWASP vulnerability scan on the project's dependencies
  * **sonar** - runs a Sonar scan and posts results to Sonar or GitHub, depending on configuration
  * **release_tag** - creates and pushes a tag for this code change
  * **deploy** - deploy the artifact to a Nexus repository

  This also shows how to use workflows and filters. Workflows allow distinct steps to be run on different schedules or branches; a PR branch may have different steps or different parameters than that of master branch.



##### Examples
- Gradle Container Config - This demonstrates a lot of useful concepts
  * **test** job is an example of how to retrieve and store test artifacts for CircleCI to use in it's Test Summary section
  * **quality-scan** job is an example of passing parameters, using environment variables, and provides the mechanism which sends Sonar data to GitHub pull request page to be used as a merge rule
  * **create-image** job is an example of creating an image with Docker commands, but saving it to the local workspace to be able to load it in other jobs in the same workflow, removing the need to create the image at each subsequent step
  * **image-scan** job is an example of how to use a 3rd party orb within the context of a job, namely Anchore
  * **deploy** job is an example of how to load saved images from previous steps, and deploy to a docker repository

- Inline Orb Config - This demonstrates how to define an orb and include definitions for executors, commands, and jobs. There is an example of orb usage in the workflow portion of the yaml, which is the same formatting regardless of the orbs location (imported from CircleCI orb registry or as an inline orb). Creating an inline orb is the first step in creating and publishing and orb to the CircleCI central orb repository. 









##### Documentation
[Official CircleCI documentation](https://circleci.com/docs/)

[Confluence that contains information about configuration, reporting, and plugin integrations](https://connexta.atlassian.net/wiki/spaces/CICD/pages/741146644/CircleCI+Setup+Configuration
)