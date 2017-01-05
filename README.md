# psawsdevintroawslambda
##6. Integrating Lambda & Other AWS Services
###2 Installing Jinja and Configuring IAM and SES
```
pip install Jinja2
```
###3 Uploading Templates to S3 and Creating Cloudwatch Events with the AWS Command Line
```
aws s3api create-bucket --bucket name --region us-east-1
```
copy
```
aws s3 cp ../templates s3://name --recursive
```

put rule
```
aws events put-rule --name work --schedule-expression 'cron(0 12 ? * MON-FRI *)'
```
###4 Creating a Dynamic Lambda Handler
```py
def get_template_from_s3(key):
  s3 = boto3.client('s3');
  s3_file = s3.get_object(Bucket = TEMPLATE_S3_BUCKET,Key=key)
  try:
    template = Template(s3_file['Body'].read())
  except Exception as e:
    raise e
  return template
```
###5 Testing Your Lambda Function with the AWS Command Line

###6 
