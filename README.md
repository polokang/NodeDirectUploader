# NodeDirectUploader

## Direct-to-S3 uploads in a Node.js application running on Heroku

Simple example demonstrating how to accomplish a direct upload to Amazon's S3 in a Node.js web application.
This example uses the [express](http://expressjs.com/) web framework to facilitate request-handling. However, the process of signing the S3 PUT request would be identical in most Node apps.

## Loacal Dependencies and Installation

- Run `npm -i` and `npm start`

## Deploy to Heroku

1. Configurate the Vars at Heroku

- `AWS_ACCESS_KEY_ID = xxx`
- `AWS_SECRET_ACCESS_KEY = xxx`
- `S3_BUCKET = elasticbeanstalk-xxxx`

2. Configurate Amazon S3

- S3 buckets -> Permissions -> CORS configuration

```
<?xml version="1.0" encoding="UTF-8"?>
<CORSConfiguration xmlns="http://s3.amazonaws.com/doc/2006-03-01/">
<CORSRule>
  <AllowedOrigin>*</AllowedOrigin>
  <AllowedMethod>GET</AllowedMethod>
  <AllowedMethod>POST</AllowedMethod>
  <AllowedMethod>PUT</AllowedMethod>
  <AllowedHeader>*</AllowedHeader>
</CORSRule>
</CORSConfiguration>
```

3. modify the region in app.js
   `aws.config.region = "ap-southeast-2"`

##issue

1. change the git repository `git remote -v`

- `git remote rm origion`
- `git remote add origin https://github.com/polokang/XXX.git`
