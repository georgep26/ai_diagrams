# AWS Icon Reference Guide

This guide provides the correct AWS icon shape names for use in draw.io diagrams. When generating draw.io XML, AI agents must use these exact shape names to ensure icons display correctly.

## How AWS Icons Work in draw.io

AWS icons in draw.io use the `mxgraph.aws4` shape library. The shape name format is:
```
shape=mxgraph.aws4.[service_name]
```

Where `[service_name]` uses **lowercase** letters and underscores instead of spaces. **Important**: All icon shape names are lowercase (e.g., `lambda`, not `Lambda`).

## Loading AWS Icons in draw.io

### Method 1: Built-in Library
1. Open draw.io at [https://app.diagrams.net](https://app.diagrams.net)
2. Click "More Shapes" at the bottom of the shapes panel
3. Scroll to "Networking" section
4. Check the box for "AWS" (or "AWS19" for latest version)
5. Click "Apply"

### Method 2: URL Library (Recommended)
**Using m-radzikowski/diagrams-aws-icons Repository**:

The [m-radzikowski/diagrams-aws-icons](https://github.com/m-radzikowski/diagrams-aws-icons) repository provides up-to-date AWS Architecture Icons for draw.io with proper connection points and optimized sizing.

1. In draw.io, go to File → Open Library from → URL
2. Enter the latest version URL:
   - Latest (2024-02-06): `https://raw.githubusercontent.com/m-radzikowski/diagrams-aws-icons/master/20240206/AWS%20Architecture%20Icons%2020240206.xml`
   - Or check the [repository](https://github.com/m-radzikowski/diagrams-aws-icons) for newer versions
3. The AWS icons will be loaded into your workspace

**Getting the Latest Version**:
- Visit: https://github.com/m-radzikowski/diagrams-aws-icons
- Check the repository for the latest version directory (format: YYYYMMDD)
- Use the URL format: `https://raw.githubusercontent.com/m-radzikowski/diagrams-aws-icons/master/[VERSION]/AWS%20Architecture%20Icons%20[VERSION].xml`
- Replace `[VERSION]` with the date code (e.g., `20240206`)

**Note**: This icon library uses lowercase shape names (e.g., `lambda`, `ecs`, `rds`) and is the source of truth for icon names in this repository.

### Method 3: Using URL Parameter
Open draw.io with: `https://app.diagrams.net/?splash=0&libs=aws4`

This automatically loads the AWS icon library.

## Complete AWS Icon Shape Name Mapping

### Compute Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **AWS Lambda** | `mxgraph.aws4.lambda` | Serverless functions |
| **Amazon ECS** | `mxgraph.aws4.ecs` | Container service cluster |
| **ECS Task** | `mxgraph.aws4.ecs_task` | Individual container task |
| **Amazon ECR** | `mxgraph.aws4.ecr` | Container registry |
| **EC2 Instance** | `mxgraph.aws4.ec2` | Virtual machine instance |
| **EC2 Mac** | `mxgraph.aws4.ec2_mac` | Mac instances for iOS builds |

### Storage Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **Amazon S3** | `mxgraph.aws4.s3` | Object storage buckets |
| **Amazon EBS** | `mxgraph.aws4.ebs` | Block storage volumes |
| **Amazon EFS** | `mxgraph.aws4.efs` | Elastic file system |
| **Amazon FSx** | `mxgraph.aws4.fsx` | Managed file systems |

### Database Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **Amazon RDS** | `mxgraph.aws4.rds` | Relational database service |
| **RDS Instance** | `mxgraph.aws4.rds_instance` | Individual database instance |
| **Amazon DynamoDB** | `mxgraph.aws4.dynamodb` | NoSQL database |
| **Amazon Aurora** | `mxgraph.aws4.aurora` | MySQL/PostgreSQL compatible |
| **Amazon Redshift** | `mxgraph.aws4.redshift` | Data warehouse |

### Networking Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **VPC** | `mxgraph.aws4.group` with `grIcon=mxgraph.aws4.group_vpc` | Virtual Private Cloud container |
| **Public Subnet** | `mxgraph.aws4.group` with `grIcon=mxgraph.aws4.group_public_subnet` | Public subnet container |
| **Private Subnet** | `mxgraph.aws4.group` with `grIcon=mxgraph.aws4.group_private_subnet` | Private subnet container |
| **Internet Gateway** | `mxgraph.aws4.internet_gateway` | Internet gateway |
| **NAT Gateway** | `mxgraph.aws4.nat_gateway` | Network address translation |
| **VPC Endpoint** | `mxgraph.aws4.vpc_endpoint` | Private AWS service access |
| **API Gateway** | `mxgraph.aws4.api_gateway` | REST/HTTP API management |
| **Application Load Balancer** | `mxgraph.aws4.elb_application_load_balancer` | Layer 7 load balancer |
| **Network Load Balancer** | `mxgraph.aws4.elb_network_load_balancer` | Layer 4 load balancer |

### AI/ML Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **Amazon Bedrock** | `mxgraph.aws4.bedrock` | Foundation models |
| **Amazon SageMaker** | `mxgraph.aws4.sagemaker` | Machine learning platform |
| **Amazon Comprehend** | `mxgraph.aws4.comprehend` | NLP service |
| **Amazon Rekognition** | `mxgraph.aws4.rekognition` | Image/video analysis |

### Search and Analytics

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **Amazon OpenSearch Service** | `mxgraph.aws4.opensearch_service` | Search and analytics |
| **Amazon Elasticsearch** | `mxgraph.aws4.elasticsearch` | Search service (legacy) |
| **Amazon Kinesis** | `mxgraph.aws4.kinesis` | Real-time streaming |

### Security and Identity

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **AWS IAM** | `mxgraph.aws4.iam` | Identity and access management |
| **AWS Secrets Manager** | `mxgraph.aws4.secrets_manager` | Secrets management |
| **AWS KMS** | `mxgraph.aws4.kms` | Key management service |
| **AWS WAF** | `mxgraph.aws4.waf` | Web application firewall |

### Monitoring and Management

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **Amazon CloudWatch** | `mxgraph.aws4.cloudwatch` | Monitoring and logging |
| **AWS X-Ray** | `mxgraph.aws4.x_ray` | Distributed tracing |
| **AWS Systems Manager** | `mxgraph.aws4.systems_manager` | Operational management |
| **AWS Config** | `mxgraph.aws4.config` | Configuration management |

### Other Common Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **AWS Cloud** | `mxgraph.aws4.group` with `grIcon=mxgraph.aws4.group_aws_cloud` | AWS cloud boundary |
| **User** | `mxgraph.aws4.user` | End users |
| **AWS CodePipeline** | `mxgraph.aws4.codepipeline` | CI/CD pipeline |
| **AWS CodeBuild** | `mxgraph.aws4.codebuild` | Build service |
| **AWS CodeDeploy** | `mxgraph.aws4.codedeploy` | Deployment service |
| **Amazon SQS** | `mxgraph.aws4.sqs` | Message queue |
| **Amazon SNS** | `mxgraph.aws4.sns` | Notification service |
| **Amazon EventBridge** | `mxgraph.aws4.eventbridge` | Event bus |

## Icon Sizing Standards

Standard AWS icon size in draw.io:
- **Width**: 78 pixels
- **Height**: 78 pixels
- **Aspect**: `aspect=fixed` (maintains icon proportions)

Example geometry:
```xml
<mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
```

## Icon Color Codes

AWS icons use standard color codes by service category:

| Category | Color Code | Example Services |
|----------|-----------|------------------|
| **Compute** | `#759C3E` (Green) | Lambda, ECS, EC2 |
| **Storage** | `#759C3E` (Green) | S3, EBS, EFS |
| **Database** | `#2E27AD` (Blue) | RDS, DynamoDB, Redshift |
| **Networking** | `#8C4FFF` (Purple) | VPC, API Gateway, Load Balancer |
| **Security** | `#8C4FFF` (Purple) | IAM, Secrets Manager, KMS |
| **AI/ML** | `#4D27AA` (Dark Purple) | Bedrock, SageMaker |
| **Management** | `#8C4FFF` (Purple) | CloudWatch, Systems Manager |

In the style attribute, use:
```xml
fillColor=#759C3E
```

## Common Icon Loading Issues

### Issue: Icons Not Displaying
**Symptoms**: Icons show as empty rectangles or generic shapes

**Solutions**:
1. Verify AWS library is loaded: Check "More Shapes" → AWS should be checked
2. Verify shape name is correct: Must match exactly (case-sensitive)
3. Check if using `libs=aws4` parameter when opening draw.io
4. Try reloading the library: File → Open Library from → URL (see Method 2 above)

### Issue: Wrong Icon Appears
**Symptoms**: Different icon than expected

**Solutions**:
1. Verify shape name spelling (use underscores, not spaces)
2. Check if service name has changed (e.g., Elasticsearch → OpenSearch)
3. Verify you're using the latest AWS icon library version

### Issue: Icon Size Wrong
**Symptoms**: Icon too large or too small

**Solutions**:
1. Use standard size: width="78" height="78"
2. Ensure `aspect=fixed` in style attribute
3. Don't modify icon dimensions - use standard size

## Verification Checklist

When generating draw.io XML with AWS icons, verify:

- [ ] AWS icon library is loaded in draw.io
- [ ] Shape name uses correct format: `mxgraph.aws4.[SERVICE_NAME]`
- [ ] Shape name uses underscores, not spaces
- [ ] Icon size is 78x78 pixels
- [ ] Style includes `aspect=fixed`
- [ ] Color code matches service category
- [ ] Container shapes use `shape=mxgraph.aws4.group` with appropriate `grIcon`

## Example: Correct Icon Usage

```xml
<!-- AWS Lambda Function -->
<mxCell id="lambda-function" 
        value="My Lambda Function" 
        style="sketch=0;points=[];outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#759C3E;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.lambda;" 
        parent="private-subnet-1" 
        vertex="1">
    <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

**Key elements**:
- `shape=mxgraph.aws4.lambda` - Correct shape name (lowercase)
- `fillColor=#759C3E` - Compute service color
- `aspect=fixed` - Maintains icon proportions
- `width="78" height="78"` - Standard icon size

## Template Usage

When using templates from this repository:
1. Reference this guide for correct icon shape names
2. Copy icon examples from base templates
3. Modify only the `value` (label) and `id` attributes
4. Keep all style attributes identical to template

## Additional Resources

- [AWS Architecture Icons](https://aws.amazon.com/architecture/icons/) - Official AWS icon source
- [draw.io AWS Icons Blog](https://www.drawio.com/blog/aws-diagrams) - Draw.io AWS integration guide
- [GitHub: m-radzikowski/diagrams-aws-icons](https://github.com/m-radzikowski/diagrams-aws-icons) - **Recommended**: Up-to-date draw.io library with lowercase icon names

## Getting the Latest AWS Icon Set

### Recommended Source: m-radzikowski/diagrams-aws-icons

The [m-radzikowski/diagrams-aws-icons](https://github.com/m-radzikowski/diagrams-aws-icons) repository is the recommended source for AWS icons in draw.io because:

1. **More Up-to-Date**: Icons are updated more frequently than the built-in draw.io library
2. **Connection Points**: Shapes have proper connection points enabled
3. **Optimized Sizing**: Icons are 50x50px (or can be configured for 78x78px)
4. **Lowercase Names**: All icon shape names use lowercase (e.g., `lambda`, `ecs`, `rds`)
5. **Single Library**: All icons in one library file

### How to Get the Latest Version

1. **Visit the Repository**: https://github.com/m-radzikowski/diagrams-aws-icons
2. **Check Latest Version**: Look for the latest version directory (format: `YYYYMMDD`, e.g., `20240206`)
3. **Load in draw.io**:
   - Method A (URL): File → Open Library from → URL
   - Enter: `https://raw.githubusercontent.com/m-radzikowski/diagrams-aws-icons/master/[VERSION]/AWS%20Architecture%20Icons%20[VERSION].xml`
   - Replace `[VERSION]` with the date code (e.g., `20240206`)
   
   - Method B (Direct Link): Click the link in the repository README to auto-load
4. **Verify Icon Names**: After loading, check icon names - they should all be lowercase

### Icon Name Format

All icons from this repository use **lowercase** names:
- ✅ `mxgraph.aws4.lambda` (correct)
- ❌ `mxgraph.aws4.Lambda` (incorrect - uppercase)
- ✅ `mxgraph.aws4.api_gateway` (correct)
- ❌ `mxgraph.aws4.API_Gateway` (incorrect - uppercase)

**Important**: This repository's icon reference guide uses lowercase names to match the m-radzikowski library format.

## Notes for AI Agents

When generating draw.io XML:
1. **Always** use shape names from this reference guide (all lowercase)
2. **Never** guess shape names - if unsure, check this guide or the [m-radzikowski repository](https://github.com/m-radzikowski/diagrams-aws-icons)
3. **Always** use lowercase for icon shape names (e.g., `lambda`, not `Lambda`)
4. **Always** use standard icon size (78x78)
5. **Always** include `aspect=fixed` in style
6. **Always** verify AWS library is loaded (preferably from m-radzikowski repository)
7. If a service isn't listed, check the latest icon library or use a generic container shape as fallback

