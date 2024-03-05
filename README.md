# Mlflowtest
Test mlflow dagshub



dagshub
dagshub

MLFLOW_TRACKING_URI=https://dagshub.com/larakim/Mlflowtest.mlflow 
MLFLOW_TRACKING_USERNAME=larakim 
MLFLOW_TRACKING_PASSWORD=6f0caff147881a6dd8d7169da2dc21273f023c6c 
python script.py

Run this to export as env variables:


```bash
set MLFLOW_TRACKING_URI=https://dagshub.com/larakim/Mlflowtest.mlflow

set MLFLOW_TRACKING_USERNAME=larakim 

set MLFLOW_TRACKING_PASSWORD=6f0caff147881a6dd8d7169da2dc21273f023c6c 
```

## AWS

### Mlflow on AWS setup:
1. Login to AWS console
2. Create IAM user with AdminAccess
3. Export the credentials in your AWS CLI by running "aws configure"
4. Create a s3 bucket
5. Create EC2 machine (Ubuntu) & add security groups 5000 port

Run the following command on EC2 machine
```bash
sudo apt update
sudo apt install python3-pip
sudo pip3 install pipenv
sudo pip3 install virtualenv
mkdir mlflow
cd mlflow
pipenv install mlflow
pipenv install awscli
pipenv install boto3
pipenv shell

#Then set aws credentials
aws configure
#Finally
mlflow server -h 0.0.0.0 --default-artifact-root s3://mlflow-test-23
# open public IPv4 DNS to the port 5000

# set uri in your local terminal and in your code
set MLFLOW_TRACKING_URI=http://ec2-54-147-36-34.compute-1.amazonaws.com:5000/
```


