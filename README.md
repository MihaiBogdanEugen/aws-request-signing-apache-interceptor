# AWS Request Signing Interceptor

An AWS request signing interceptor for arbitrary HttpRequests.

This enables you to sign requests to any service that leverages SigV4 this means you have a client that can access any AWS Service or APIGW backed service.

This library is based on [AWS Interceptor](https://github.com/awslabs/aws-request-signing-apache-interceptor) but using AWS SDK version 2.X.X.

## License

This library is licensed under the Apache 2.0 License.

## Usage
```java
Aws4Signer signer = Aws4Signer.create();

HttpRequestInterceptor interceptor = new AwsRequestSigningApacheInterceptor(serviceName, signer, credentialsProvider, AWS_REGION);

HttpClients.custom()
        .addInterceptorLast(interceptor)
        .build();
```

## Examples

See [examples](src/test/java/io/github/acm19/aws/interceptor/test) for a few valid requests.
