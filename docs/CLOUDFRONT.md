# CloudFront
CDN for web content

- Origin: location of the content i.e. S3/web host
- Cache Behaviour

## Cache key
- host encoding
- query string

## SSL termination to origin (need to setup cert)

## Why Do You Need to Clear Amazon CloudFront Cache?
While caching improves performance and reduces latency, it can also cause issues when you make changes to your website or application. CloudFront caches content based on the TTL (Time to Live) value set in the cache behavior settings. When you make changes to your website or application, such as updating the content or changing the configuration, CloudFront may not immediately reflect those changes due to cached content. In this case, you need to clear the cache of your CloudFront distribution to ensure that the latest content is served to your users.

## Manually Clearing CloudFront Cache

To manually clear the cache of your Amazon CloudFront distribution, follow these steps:

- Log in to the AWS Management Console and navigate to the CloudFront dashboard.
- Select the distribution for which you want to clear the cache.
- Click on the “Invalidations” tab and then click on “Create Invalidation.”
- In the “Object Paths” field, enter the path of the file or directory that you want to invalidate. You can use wildcards (*) to invalidate multiple files or directories.
- Click on “Create Invalidation” to submit the invalidation request.
  - Note that it may take some time for the invalidation request to complete, depending on the size of your distribution and the number of files to be invalidated.

## Programmatically Clearing CloudFront Cache

If you need to clear the cache of your Amazon CloudFront distribution programmatically, you can use the AWS SDKs or the CloudFront API. Here’s an example of how to clear the cache of your CloudFront distribution using the AWS CLI:
```
aws cloudfront create-invalidation --distribution-id DISTRIBUTION_ID --paths "/path1/*" "/path2/*"
```
Replace DISTRIBUTION_ID with the ID of your CloudFront distribution and /path1/* and /path2/* with the paths of the files or directories that you want to invalidate. You can use multiple paths separated by spaces.



