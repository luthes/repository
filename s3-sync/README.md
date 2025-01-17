# Community Hass.io Add-ons: AWS S3 Sync

## About

This add-on allows you to automate backups to AWS S3, keeping them outside of 
your home network in case of a catastrophic failure.

This addon should not cause any harm to your system, there are no writes or
modifications made to your system. It will only sync what's local to the 
specified S3 Bucket.


## Features

This add-on will sync local backup files to the specified S3 bucket, and the
other way as well, from S3 to Local. Backups will not be deleted from the local
directory, and any backups that exist in S3 will be moved locally.

Because this is a sync, you could potentially move more backups from S3 to the
local drive than you have storage for. The AWS CLI will stop it from filling up
the drive, but be sure to remove old backups from S3 just to be on the safe
side.

## Config

Example Config
```
{
  "log_level": "info",
  "aws_access_key": "AKIAIOSFODNN7EXAMPLE",
  "aws_secret_key": "wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY",
  "aws_s3_bucket": "my-s3-bucket"
}
```

### Option: log_level
Info - Will only show error messages from the AWS CLI
Debug - Shows full output of S3 Command. This is really noisey.

### Option: aws_access_key
Only matches AWS Access Key pattern

### Option: aws_access_key
Only matches AWS Secret Access Key pattern

### Option: aws_s3_bucket
Bucket name, without `s3://` prefix.

