# aws-scaleable-wordpress-multisite

## Description
### System Design:
- Scale-able Wordpress MultiSite Setup
- AWS

```
  AWS autoscaling can handle this via ElasticBeanstalk.
  The site can scale based on metrics such as CPU or load balancer latency.
```

#### Must Include:
- CDN
- WAF
- Object Cache (e.g. Redis)
- ElasticSearch (Apache Licence Version)
- PHP FPM
- Nginx Apache Hybrid Stack
- High Availability I.E. multiple zones as in example below.
```
  It would be easiest to leverage the AWS services here. CloudFront for the CDN, AWS WAF can be used with application 
  loadbalancers and CloudFront too. Elasticache, and Elasticsearch are both available services. AutoScaling can be
  very simply configured to provide multi availability zone support.
  
  PHP FPM and Nginx apache would be part of the container, (docker uses more CPU so will be more expensive). 
```

#### Must Support Multi Site for:
- Subdirectory
- Redirect based on GeoLocation to site (e.g. domain.com/us domain.com/eu)
```
    Multisite can be implemented with Application loadbalancers that read the Host-Header in the HTTP request headers. 
    This allows for redirecting traffic to a different application/container.
```

#### Must Support:
- WooCommerce
- ElasticPress or Alternative for Search
```
    Themeforest has lots of out-of-the-box templates, including WooCommerce: https://themeforest.net/category/wordpress
```

#### Must Scale:
- Down for cost when site is not busy
- Up for when busy
```
    This technology is called AutoScaling and keys off metrics such as CPU, or load-balancer latency.
```

#### Must:
- Easy Deploy using CloudFormation, not hours of config
- Logging Everything
- Opensource Only
```
    All my work is CloudFormation, please see my Githib page for more examples of my work. Logging comes included with 
    AWS CloudWatch. WooCommerce is available on Github https://github.com/woocommerce/woocommerce
```

### Deliverable's:
- Granular Costings for Cloud Resources, along with real life examples i.e. one person in the admin area fulfilling orders or updating content and 20 people on the site browsing the store requires these resources, when there are 50 people on the site it scales up and the additional resources are .... and the cost is ....
- CloudFormation/Template that works as per the specification
- Detailed and Well Documented Design to allow for any future modifications and testing.

```
  I created a simple calculation for you using the AWS monthly calculator: 
  
  https://calculator.s3.amazonaws.com/index.html#r=IAD&key=files/calc-ebdb7c927ebbda94fc045a6f82125feb6ebfb9dd&v=ver20190731tO
  
  Please note that EC2 bill is estimated:
    - Elasticsearch requires an instance profile based on the data being searched.
    - Web server autoscaling trends and instance profile can only be esitmated until real world metrics are gathered.
    
  All my work is CloudFormation. I do terraform on request.
  
  I've saved this as a CloudCraft app, and can be shared if you provide your email, this will allow you to modifiy it.
  They also have a plugin that will spin-up the design in AWS. 
```


Similar to Below does not have to be kubernetes, but seems the most likely alternative.

https://developer.ibm.com/patterns/scalable-wordpress-on-kubernetes/

Feel free to make recommendation/corrections, that are fast, secure and scale.

```
  - You haven't requested a database. RDS multi-az running postgres would be best.
  - Elasticbeanstalk is fast and has much of what you want off the bat.
```

## Solution
