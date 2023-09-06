# CloudFront
CDN for web content

- Origin: location of the content i.e. S3/web host
- Cache Behaviour

## Cache key
- host encoding
- query string

## How to use SSL with CloudFront?
You can configure CloudFront to require that viewers use HTTPS so that connections are encrypted when CloudFront communicates with viewers. You also can configure CloudFront to use HTTPS with your origin so that connections are encrypted when CloudFront communicates with your origin.

If you configure CloudFront to require HTTPS both to communicate with viewers and to communicate with your origin, here’s what happens when CloudFront receives a request:

- A viewer submits an HTTPS request to CloudFront. There’s some SSL/TLS negotiation here between the viewer and CloudFront. In the end, the viewer submits the request in an encrypted format.
- If the CloudFront edge location contains a cached response, CloudFront encrypts the response and returns it to the viewer, and the viewer decrypts it.
- If the CloudFront edge location doesn’t contain a cached response, CloudFront performs SSL/TLS negotiation with your origin and, when the negotiation is complete, forwards the request to your origin in an encrypted format.
- Your origin decrypts the request, processes it (generates a response), encrypts the response, and returns the response to CloudFront.
- CloudFront decrypts the response, re-encrypts it, and forwards it to the viewer. CloudFront also caches the response in the edge location so that it’s available the next time it’s requested.
- The viewer decrypts the response.

The process works basically the same way whether your origin is an Amazon S3 bucket, MediaStore, or a custom origin such as an HTTP/S server.

## How to setup TLS with CloudFront and Origin?
To require HTTPS between CloudFront and your origin, follow the procedures in this topic to do the following:

1. In your distribution, change the Origin Protocol Policy setting for the origin.
2. Install an SSL/TLS certificate on your origin server (this isn’t required when you use an Amazon S3 origin or certain other AWS origins).

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



