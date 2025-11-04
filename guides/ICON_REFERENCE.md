# AWS Icon Reference Guide

This guide provides the correct AWS icon shape names for use in draw.io diagrams. When generating draw.io XML, AI agents must use these exact shape names to ensure icons display correctly.

## How AWS Icons Work in draw.io

AWS icons in draw.io use the `mxgraph.aws4` shape library. The shape name format is:
```
shape=mxgraph.aws4.[SERVICE_NAME]
```

Where `[SERVICE_NAME]` uses underscores instead of spaces and follows AWS naming conventions.

## Loading AWS Icons in draw.io

### Method 1: Built-in Library (Recommended)
1. Open draw.io at [https://app.diagrams.net](https://app.diagrams.net)
2. Click "More Shapes" at the bottom of the shapes panel
3. Scroll to "Networking" section
4. Check the box for "AWS" (or "AWS19" for latest version)
5. Click "Apply"

### Method 2: URL Library
1. In draw.io, go to File → Open Library from → URL
2. Enter: `https://raw.githubusercontent.com/m-radzikowski/diagrams-aws-icons/master/20240206/AWS%20Architecture%20Icons%2020240206.xml`
3. The AWS icons will be loaded into your workspace

### Method 3: Using URL Parameter
Open draw.io with: `https://app.diagrams.net/?splash=0&libs=aws4`

This automatically loads the AWS icon library.

## Complete AWS Icon Shape Name Mapping

### Compute Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **AWS Lambda** | `mxgraph.aws4.Lambda` | Serverless functions |
| **Amazon ECS** | `mxgraph.aws4.ECS` | Container service cluster |
| **ECS Task** | `mxgraph.aws4.ECS_Task` | Individual container task |
| **Amazon ECR** | `mxgraph.aws4.ECR` | Container registry |
| **EC2 Instance** | `mxgraph.aws4.EC2` | Virtual machine instance |
| **EC2 Mac** | `mxgraph.aws4.EC2_Mac` | Mac instances for iOS builds |

### Storage Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **Amazon S3** | `mxgraph.aws4.S3` | Object storage buckets |
| **Amazon EBS** | `mxgraph.aws4.EBS` | Block storage volumes |
| **Amazon EFS** | `mxgraph.aws4.EFS` | Elastic file system |
| **Amazon FSx** | `mxgraph.aws4.FSx` | Managed file systems |

### Database Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **Amazon RDS** | `mxgraph.aws4.RDS` | Relational database service |
| **RDS Instance** | `mxgraph.aws4.RDS_Instance` | Individual database instance |
| **Amazon DynamoDB** | `mxgraph.aws4.DynamoDB` | NoSQL database |
| **Amazon Aurora** | `mxgraph.aws4.Aurora` | MySQL/PostgreSQL compatible |
| **Amazon Redshift** | `mxgraph.aws4.Redshift` | Data warehouse |

### Networking Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **VPC** | `mxgraph.aws4.group` with `grIcon=mxgraph.aws4.group_vpc` | Virtual Private Cloud container |
| **Public Subnet** | `mxgraph.aws4.group` with `grIcon=mxgraph.aws4.group_public_subnet` | Public subnet container |
| **Private Subnet** | `mxgraph.aws4.group` with `grIcon=mxgraph.aws4.group_private_subnet` | Private subnet container |
| **Internet Gateway** | `mxgraph.aws4.Internet_Gateway` | Internet gateway |
| **NAT Gateway** | `mxgraph.aws4.NAT_Gateway` | Network address translation |
| **VPC Endpoint** | `mxgraph.aws4.VPC_Endpoint` | Private AWS service access |
| **API Gateway** | `mxgraph.aws4.API_Gateway` | REST/HTTP API management |
| **Application Load Balancer** | `mxgraph.aws4.ELB_Application_Load_Balancer` | Layer 7 load balancer |
| **Network Load Balancer** | `mxgraph.aws4.ELB_Network_Load_Balancer` | Layer 4 load balancer |

### AI/ML Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **Amazon Bedrock** | `mxgraph.aws4.Bedrock` | Foundation models |
| **Amazon SageMaker** | `mxgraph.aws4.SageMaker` | Machine learning platform |
| **Amazon Comprehend** | `mxgraph.aws4.Comprehend` | NLP service |
| **Amazon Rekognition** | `mxgraph.aws4.Rekognition` | Image/video analysis |

### Search and Analytics

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **Amazon OpenSearch Service** | `mxgraph.aws4.OpenSearch_Service` | Search and analytics |
| **Amazon Elasticsearch** | `mxgraph.aws4.Elasticsearch` | Search service (legacy) |
| **Amazon Kinesis** | `mxgraph.aws4.Kinesis` | Real-time streaming |

### Security and Identity

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **AWS IAM** | `mxgraph.aws4.IAM` | Identity and access management |
| **AWS Secrets Manager** | `mxgraph.aws4.Secrets_Manager` | Secrets management |
| **AWS KMS** | `mxgraph.aws4.KMS` | Key management service |
| **AWS WAF** | `mxgraph.aws4.WAF` | Web application firewall |

### Monitoring and Management

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **Amazon CloudWatch** | `mxgraph.aws4.CloudWatch` | Monitoring and logging |
| **AWS X-Ray** | `mxgraph.aws4.X_Ray` | Distributed tracing |
| **AWS Systems Manager** | `mxgraph.aws4.Systems_Manager` | Operational management |
| **AWS Config** | `mxgraph.aws4.Config` | Configuration management |

### Other Common Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **AWS Cloud** | `mxgraph.aws4.group` with `grIcon=mxgraph.aws4.group_aws_cloud` | AWS cloud boundary |
| **User** | `mxgraph.aws4.user` | End users |
| **AWS CodePipeline** | `mxgraph.aws4.CodePipeline` | CI/CD pipeline |
| **AWS CodeBuild** | `mxgraph.aws4.CodeBuild` | Build service |
| **AWS CodeDeploy** | `mxgraph.aws4.CodeDeploy` | Deployment service |
| **Amazon SQS** | `mxgraph.aws4.SQS` | Message queue |
| **Amazon SNS** | `mxgraph.aws4.SNS` | Notification service |
| **Amazon EventBridge** | `mxgraph.aws4.EventBridge` | Event bus |

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
        style="sketch=0;points=[];outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#759C3E;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.Lambda;" 
        parent="private-subnet-1" 
        vertex="1">
    <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

**Key elements**:
- `shape=mxgraph.aws4.Lambda` - Correct shape name
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

- [AWS Architecture Icons](https://aws.amazon.com/architecture/icons/)
- [draw.io AWS Icons Blog](https://www.drawio.com/blog/aws-diagrams)
- [GitHub: diagrams-aws-icons](https://github.com/m-radzikowski/diagrams-aws-icons)

## Notes for AI Agents

When generating draw.io XML:
1. **Always** use shape names from this reference guide
2. **Never** guess shape names - if unsure, check this guide
3. **Always** use standard icon size (78x78)
4. **Always** include `aspect=fixed` in style
5. **Always** verify AWS library is mentioned in user instructions
6. If a service isn't listed, search AWS documentation or use a generic container shape as fallback

