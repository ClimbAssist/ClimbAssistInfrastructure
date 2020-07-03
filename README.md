ClimbAssistInfrastructure
============

Welcome to ClimbAssistInfrastructure!

See it live at [climbassist.com](https://climbassist.com)!

This repository contains the code defining the deployment toolchain infrastructure for Climb Assist. Climb Assist
runs on AWS and the toolchain resources are provisioned using CloudFormation. The toolchain is responsible for
the basic deployment process, which includes:
* Compiling and munging source code
* Running unit tests
* Deploying beta and production versions of ClimbAssist through CloudFormation
* Running integration tests against beta

If you have any questions or concerns, reach out to the development team at 
[dev@climbassist.com](mailto:dev@climbassist.com).

To clone this repository, run the following command:

    $ git clone https://github.com/ClimbAssist/ClimbAssistInfrastructure.git
    
The toolchain stack contains all of our development resources like our CodePipeline pipeline, CodeBuild stages, related
roles, etc. The name of this stack is "awscodestar-climbassist" and the template used to create it is located in
toolchain.yml. Unlike our infrastructure stack, this stack is not updated when we make a code change. Instead, you
have to manually deploy this stack when you need to make changes. Remember, the toolchain stack is responsible for 
creating all of the infrastructure on which Climb Assist runs. Modifying it recklessly could bring down the website
altogether. Make sure you know what you're doing before you make changes. Reach out to the development team if you're
unsure.

In order to deploy the toolchain, you will need access to the Climb Assist AWS account. Most likely, you will have to
reach out to the development team and have them run your changes and confirm that they work.

However, if you do have access to the AWS account and you would like deploy changes to the toolchain, the
instructions are as follows:

Deploying the Toolchain Stack
-----------------------------

1. Install the SAM CLI following [these
instructions](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html).
Note: You don't need to install Docker, even though it says you do.

2. Deploy the toolchain stack

        $ ./deploy-toolchain
