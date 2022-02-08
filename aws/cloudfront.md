AWS CloudFront makes for an excellent host for static assets.
Basically you put your static assets in an S3 bucket and CloudFront will serve those assets at minimal cost.
You can also get a free ACM certificate for your domain and point it at your CloudFront distribution.

## Invalidation

By default, CloudFront will cache a given object (path) basically forever.
We therefore have to use a versioning strategy to invalidate objects when they change.
See [this support page](https://aws.amazon.com/premiumsupport/knowledge-center/cloudfront-serving-outdated-content-s3/) for details.

For objects that change frequently, I use the naming convention `name-datetime.extension`.
For example instead of `index.html` I will have `index-2022-02-08T17-21.html`.
