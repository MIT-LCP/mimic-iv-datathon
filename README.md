## Cloud access to datasets

The MIMIC-IV database is available on Amazon Web Services (AWS). To access the data on the cloud, simply add the relevant cloud identifier to your PhysioNet profile.

### Launch MIMIC-IV in AWS

MIMIC-IV (version 2.0) is available on AWS. Use the below Launch Stack button to deploy access to the MIMIC-IV dataset into your AWS account.  This will give you real-time access to the MIMIC-IV data in your AWS account without having to download a copy of the MIMIC-IV dataset.  It will also deploy a Jupyter Notebook with access to the content of this GitHub repository in your AWS account.    Prior to launching this, please login to the [MIMIC PhysioNet website](https://mimic.mit.edu/) and [input your AWS account number](https://physionet.org/settings/cloud/).

To start this deployment, click the Launch Stack button.  

<!-- On the first screen, the template link has already been specified, so just click next.  On the second screen, choose to keep or change the provided Stack name (letters and numbers) and click next, on the third screen, just click next.  On the forth screen, at the bottom, there is a box that says **I acknowledge that AWS CloudFormation might create IAM resources.**.  Check that box, and then click **Create**.  Once the Stack has complete deploying, look at the **Outputs** tab of the AWS CloudFormation console for links to your Juypter Notebooks instance. -->

[![cloudformation-launch-stack](cloudformation-launch-stack.png)](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/new?stackName=MIMICIV&templateURL=https://template-mimiciv.s3.amazonaws.com/template.yaml)