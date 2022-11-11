## Cloud access to datasets

The MIMIC-IV database is available on Amazon Web Services (AWS). To access the data on the cloud, simply add the relevant cloud identifier to your PhysioNet profile.

### Launch MIMIC-IV in AWS

MIMIC-IV (version 2.0) is available in an Amazon S3 bucket hosted on AWS. You can use an interactive query service like [Amazon Athena](https://aws.amazon.com/athena/?whats-new-cards.sort-by=item.additionalFields.postDateTime&whats-new-cards.sort-order=desc) to run standard SQL queries against the dataset, or programmatically in an [Amazon Sagemaker notebook instance](https://docs.aws.amazon.com/sagemaker/latest/dg/nbi.html) with the latest Jupyter Notebook App pre-installed.

To get started, deploy this [cloudformation template](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/new?stackName=MIMICIV&templateURL=https://template-mimiciv.s3.amazonaws.com/template.yaml). Deploying this template will create the following in your AWS account:

* An AWS Glue database called `mimiciv`
* AWS Glue tables (metadata) which define the schema for each table in the `mimiciv` database
* An Amazon Sagemaker notebook instance with an example python notebook demonstrating access to `mimiciv`
* An Amazon Athena workgroup configured to allow SQL queries against the `mimiciv` database
* An Amazon S3 bucket for use with the Amazon Athena workgroup to store query results

### Sagemaker Notebook Instance

You can access your notebook instance by clicking the URL in the `Outputs` tab:
![notebook-url](images/notebook-url.png)

### Amazon Athena Query Editor

The `Outputs` tab also has a link to the Amazon Athena query editor interface. Here you can author SQL queries and run them against the `mimiciv` database.

Once in the web interface, you'll need to switch to the `mimiciv` workgroup, located towards the top right of the screen:
![workgroup](images/workgroup.png)

This workgroup is configured to log results to an S3 bucket that has been created for you.

Prior to launching this, please login to the [MIMIC PhysioNet website](https://mimic.mit.edu/) and [input your AWS account number](https://physionet.org/settings/cloud/).

To start this deployment, click the Launch Stack button. Once the Stack has complete deploying, look at the **Outputs** tab of the AWS CloudFormation console for links to your Jupyter Notebooks instance.

<!-- On the first screen, the template link has already been specified, so just click next.  On the second screen, choose to keep or change the provided Stack name (letters and numbers) and click next, on the third screen, just click next.  On the forth screen, at the bottom, there is a box that says **I acknowledge that AWS CloudFormation might create IAM resources.**.  Check that box, and then click **Create**.   -->

[![cloudformation-launch-stack](images/cloudformation-launch-stack.png)](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/new?stackName=MIMICIV&templateURL=https://template-mimiciv.s3.amazonaws.com/template.yaml)
