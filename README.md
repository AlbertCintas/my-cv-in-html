# My CV in HTML

This repository contains an unupdated version of my CV, exported to HTML from Google Docs. It is used to test and showcase CI/CD pipelines and other stuff.

The repository also contains two Github Actions:
* An action that creates a draft release when there is a push on the main branch.
* Another one that pings some webhooks in a live Ansible Tower instance to run provision/deploy playbooks stored in: https://github.com/AlbertCintas/ansible-webserver.

The release pipeline should be adapted to the team/project workflow, since there is not a perfect pipeline for all projects but in the latest stage, would be something like this:
* Developers work in their branches, and merge to a common develop branch.
* Once develop branch has been tested enough, it can be merged into main branch, where a draft release will be automatically created and deployed to a Staging environment.
* Once QA gives the OK, the draft release can be published, which will trigger a prod deployment using Tower. The last step can be automated, but a manual last step gives control on the deployment, which is desirable in some instances.

This pipeline also works for many kind of deployments, adding to the actions steps to build docker images or generate artifacts, as well as uploading everything to public or private registries.
 
