# SSL Issues Resolved

It turns out that the issue was indeed with my certificate that I was using. To
resolve this, I basically did the following:

1. Setup a Route53 zone for a domain I owned (zettels.io)
2. Changed my DNS Nameservers on Namecheap for zettels.io to those which were
   provided by my new Route53 NS record
3. I added two new records to my hosted zone to route traffic from www.zettels.io
   and zettels.io the EC2 IPv4 endpoint for the server running my zettels-service 
   jar
4. I logged into the same EC2 instance and used Certbot CLI to get my certification
   in order.
5. I used openSSL CLI to use the `*.pem` keys that were generated by Certbot to
   create a `keystore.p12` file which was stored in `/etc/letsencrypt/live/zettels.io/keystore.p12`
   on the EC2 instance
6. I changed the `server.ssl.key-store: ...` in the `application.properties` in the
   source files of my application and remade the jar; I redeployed this jar to 
   the EC2 and fired it back up

## References
https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-to-ec2-instance.html  (Step 1,3) \
https://turreta.com/2019/02/27/aws-point-your-namecheap-domain-to-ec2-instance-via-route53/  (Step 2,3) \
https://dzone.com/articles/spring-boot-secured-by-lets-encrypt  (Step 5) \
https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/SSL-on-amazon-linux-2.html#letsencrypt  (Step 4)

## Tags
#java #spring