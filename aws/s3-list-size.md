# Finding the size of an S3 bucket

Today I learned how to list the size of an S3 bucket. First, this information is currently (Nov 2018) not displayed in the AWS console.

Instead, you have to run this command from the console.

```
aws s3 ls s3://mybucket --recursive --human-readable --summarize
```

Note that `--recursive` will print the contents of the bucket as well, and might be expensive if you have many small objects. However the command will not work without `--recursive` and will return an incorrect size without it.

[Source](https://docs.aws.amazon.com/cli/latest/reference/s3/ls.html)
