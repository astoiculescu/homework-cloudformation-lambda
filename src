import boto3
#upload a file in the bucket
s3_client = boto3.client('s3')
response = s3_client.upload_file('file_to_upload.txt', 'homework-lambda-s3', 'uploads/file_to_upload.txt')
print('Upload Successful')

# list all objects in a bucket
s3 = boto3.resource('s3')
my_bucket = s3.Bucket('homework-lambda-s3')
for file in my_bucket.objects.all():
    print('Bucket files:')
    print(file.key)
