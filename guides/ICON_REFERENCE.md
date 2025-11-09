# AWS Icon Reference Guide

This guide provides the correct AWS icon shape names for use in draw.io diagrams. When generating draw.io XML, AI agents must use these exact shape names to ensure icons display correctly.

## How AWS Icons Work in draw.io

AWS icons in draw.io use the `mxgraph.aws4` shape library. The **correct** format for AWS service icons is:
```
shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.[service_name]
```

Where `[service_name]` uses **lowercase** letters and underscores instead of spaces. **Important**: 
- All icon shape names are lowercase (e.g., `lambda`, not `Lambda`)
- Use `shape=mxgraph.aws4.resourceIcon` with `resIcon` attribute for AWS services
- Do NOT use `shape=mxgraph.aws4.[service_name]` directly (this is the old format)

**Exception**: User icons use `shape=mxgraph.aws4.user` directly (not `resourceIcon`).

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

**Important**: The shape names listed in the tables below should be used as `resIcon` values. For example, if the table shows `mxgraph.aws4.lambda`, use it as:
```xml
shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.lambda
```

### Compute Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **AWS Lambda** | `mxgraph.aws4.lambda` | Serverless functions |
| **Lambda Function** | `mxgraph.aws4.lambda_function` | Individual Lambda function |
| **Amazon ECS** | `mxgraph.aws4.ecs` | Container service cluster |
| **ECS Service** | `mxgraph.aws4.ecs_service` | ECS service definition |
| **ECS Service Connect** | `mxgraph.aws4.ecs_service_connect` | Service mesh connectivity |
| **ECS Task** | `mxgraph.aws4.ecs_task` | Individual container task |
| **ECS Anywhere** | `mxgraph.aws4.ecs_anywhere` | ECS on-premises |
| **ECS Copilot CLI** | `mxgraph.aws4.ecs_copilot_cli` | ECS CLI tool |
| **Amazon ECR** | `mxgraph.aws4.ecr` | Container registry |
| **Amazon EKS** | `mxgraph.aws4.eks` | Kubernetes service |
| **EKS Anywhere** | `mxgraph.aws4.eks_anywhere` | EKS on-premises |
| **EKS Cloud** | `mxgraph.aws4.eks_cloud` | EKS cloud deployment |
| **EKS Distro** | `mxgraph.aws4.eks_distro` | EKS Kubernetes distribution |
| **EKS on Outposts** | `mxgraph.aws4.eks_on_outposts` | EKS on AWS Outposts |
| **EC2 Instance** | `mxgraph.aws4.ec2` | Virtual machine instance |
| **EC2 Instance Contents** | `mxgraph.aws4.ec2_instance_contents` | EC2 instance internals |
| **EC2 Mac Instance** | `mxgraph.aws4.ec2_mac` | Mac instances for iOS builds |
| **EC2 M1 Mac Instance** | `mxgraph.aws4.ec2_m1_mac_instance` | Apple Silicon Mac instances |
| **EC2 Image Builder** | `mxgraph.aws4.ec2_image_builder` | Automated image creation |
| **EC2 C6a Instance** | `mxgraph.aws4.ec2_c6a_instance` | Compute-optimized instances |
| **EC2 C6gn Instance** | `mxgraph.aws4.ec2_c6gn_instance` | Network-optimized compute instances |
| **EC2 C6i Instance** | `mxgraph.aws4.ec2_c6i_instance` | Compute-optimized instances |
| **EC2 C6in Instance** | `mxgraph.aws4.ec2_c6in_instance` | Network-optimized compute instances |
| **EC2 C7g Instance** | `mxgraph.aws4.ec2_c7g_instance` | Graviton3 compute instances |
| **EC2 C7gn Instance** | `mxgraph.aws4.ec2_c7gn_instance` | Network-optimized Graviton3 instances |
| **EC2 DL1 Instance** | `mxgraph.aws4.ec2_dl1_instance` | Deep learning instances |
| **EC2 G5 Instance** | `mxgraph.aws4.ec2_g5_instance` | GPU instances |
| **EC2 G5g Instance** | `mxgraph.aws4.ec2_g5g_instance` | Graviton GPU instances |
| **EC2 HPC6a Instance** | `mxgraph.aws4.ec2_hpc6a_instance` | High performance compute instances |
| **EC2 HPC6id Instance** | `mxgraph.aws4.ec2_hpc6id_instance` | High performance compute with local storage |
| **EC2 I4i Instance** | `mxgraph.aws4.ec2_i4i_instance` | Storage-optimized instances |
| **EC2 IM4gn Instance** | `mxgraph.aws4.ec2_im4gn_instance` | Storage-optimized Graviton instances |
| **EC2 Inf2 Instance** | `mxgraph.aws4.ec2_inf2_instance` | Inferentia inference instances |
| **EC2 IS4gen Instance** | `mxgraph.aws4.ec2_is4gen_instance` | Storage-optimized instances |
| **EC2 M6a Instance** | `mxgraph.aws4.ec2_m6a_instance` | General purpose instances |
| **EC2 M6i Instance** | `mxgraph.aws4.ec2_m6i_instance` | General purpose instances |
| **EC2 M6idn Instance** | `mxgraph.aws4.ec2_m6idn_instance` | Network-optimized general purpose instances |
| **EC2 M6in Instance** | `mxgraph.aws4.ec2_m6in_instance` | Network-optimized general purpose instances |
| **EC2 P4de Instance** | `mxgraph.aws4.ec2_p4de_instance` | GPU instances for ML |
| **EC2 R6a Instance** | `mxgraph.aws4.ec2_r6a_instance` | Memory-optimized instances |
| **EC2 R6i Instance** | `mxgraph.aws4.ec2_r6i_instance` | Memory-optimized instances |
| **EC2 R6idn Instance** | `mxgraph.aws4.ec2_r6idn_instance` | Network-optimized memory instances |
| **EC2 R6in Instance** | `mxgraph.aws4.ec2_r6in_instance` | Network-optimized memory instances |
| **EC2 R7iz Instance** | `mxgraph.aws4.ec2_r7iz_instance` | Memory-optimized instances |
| **EC2 TRN1 Instance** | `mxgraph.aws4.ec2_trn1_instance` | Trainium training instances |
| **EC2 VT1 Instance** | `mxgraph.aws4.ec2_vt1_instance` | Video transcoding instances |
| **EC2 X2gd Instance** | `mxgraph.aws4.ec2_x2gd_instance` | Memory-optimized Graviton instances |
| **EC2 X2idn Instance** | `mxgraph.aws4.ec2_x2idn_instance` | Network-optimized memory instances |
| **EC2 X2iedn Instance** | `mxgraph.aws4.ec2_x2iedn_instance` | Network-optimized memory instances |
| **EC2 X2iezn Instance** | `mxgraph.aws4.ec2_x2iezn_instance` | Network-optimized memory instances |
| **EC2 AWS Microservice Extractor for .NET** | `mxgraph.aws4.ec2_aws_microservice_extractor_for_net` | .NET microservice extraction tool |
| **A1 Instance** | `mxgraph.aws4.a1_instance` | Arm-based instances |
| **C4 Instance** | `mxgraph.aws4.c4_instance` | Compute-optimized instances |
| **C5 Instance** | `mxgraph.aws4.c5_instance` | Compute-optimized instances |
| **C5a Instance** | `mxgraph.aws4.c5a` | AMD compute-optimized instances |
| **C5ad Instance** | `mxgraph.aws4.c5ad` | AMD compute-optimized with NVMe |
| **C5d Instance** | `mxgraph.aws4.c5d` | Compute-optimized with NVMe |
| **C5n Instance** | `mxgraph.aws4.c5n_instance` | Network-optimized compute instances |
| **C6g Instance** | `mxgraph.aws4.c6g_instance` | Graviton2 compute instances |
| **C6gd Instance** | `mxgraph.aws4.c6gd` | Graviton2 compute with NVMe |
| **D2 Instance** | `mxgraph.aws4.d2_instance` | Dense storage instances |
| **D3 Instance** | `mxgraph.aws4.d3_instance` | Dense storage instances |
| **D3en Instance** | `mxgraph.aws4.d3en_instance` | Enhanced dense storage instances |
| **F1 Instance** | `mxgraph.aws4.f1_instance` | FPGA instances |
| **G3 Instance** | `mxgraph.aws4.g3_instance` | GPU instances |
| **G4ad Instance** | `mxgraph.aws4.g4ad_instance` | AMD GPU instances |
| **G4dn Instance** | `mxgraph.aws4.g4dn` | GPU instances with NVMe |
| **H1 Instance** | `mxgraph.aws4.h1_instance` | High disk throughput instances |
| **I2 Instance** | `mxgraph.aws4.i2` | Storage-optimized instances |
| **I3 Instance** | `mxgraph.aws4.i3_instance` | Storage-optimized instances |
| **I3en Instance** | `mxgraph.aws4.i3en` | Enhanced storage-optimized instances |
| **Inf1 Instance** | `mxgraph.aws4.inf1` | Inferentia inference instances |
| **M4 Instance** | `mxgraph.aws4.m4_instance` | General purpose instances |
| **M5 Instance** | `mxgraph.aws4.m5_instance` | General purpose instances |
| **M5a Instance** | `mxgraph.aws4.m5a_instance` | AMD general purpose instances |
| **M5d Instance** | `mxgraph.aws4.m5d_instance` | General purpose with NVMe |
| **M5dn Instance** | `mxgraph.aws4.m5dn_instance` | Network-optimized general purpose |
| **M5n Instance** | `mxgraph.aws4.m5n_instance` | Network-optimized general purpose |
| **M5zn Instance** | `mxgraph.aws4.m5zn_instance` | High frequency general purpose |
| **M6g Instance** | `mxgraph.aws4.m6g_instance` | Graviton2 general purpose |
| **M6gd Instance** | `mxgraph.aws4.m6gd_instance` | Graviton2 general purpose with NVMe |
| **Mac Instance** | `mxgraph.aws4.mac_instance` | Mac instances |
| **P2 Instance** | `mxgraph.aws4.p2_instance` | GPU instances |
| **P3 Instance** | `mxgraph.aws4.p3_instance` | GPU instances |
| **P3dn Instance** | `mxgraph.aws4.p3dn_instance` | Network-optimized GPU instances |
| **P4 Instance** | `mxgraph.aws4.p4_instance` | GPU instances |
| **P4d Instance** | `mxgraph.aws4.p4d_instance` | GPU instances |
| **R4 Instance** | `mxgraph.aws4.r4_instance` | Memory-optimized instances |
| **R5 Instance** | `mxgraph.aws4.r5_instance` | Memory-optimized instances |
| **R5a Instance** | `mxgraph.aws4.r5a_instance` | AMD memory-optimized instances |
| **R5ad Instance** | `mxgraph.aws4.r5ad_instance` | AMD memory-optimized with NVMe |
| **R5b Instance** | `mxgraph.aws4.r5b_instance` | Memory-optimized instances |
| **R5d Instance** | `mxgraph.aws4.r5d_instance` | Memory-optimized with NVMe |
| **R5gd Instance** | `mxgraph.aws4.r5gd_instance` | Graviton2 memory-optimized with NVMe |
| **R5n Instance** | `mxgraph.aws4.r5n_instance` | Network-optimized memory instances |
| **R6g Instance** | `mxgraph.aws4.r6g_instance` | Graviton2 memory-optimized |
| **RDN Instance** | `mxgraph.aws4.rdn_instance` | Memory-optimized instances |
| **T2 Instance** | `mxgraph.aws4.t2_instance` | Burstable instances |
| **T3 Instance** | `mxgraph.aws4.t3_instance` | Burstable instances |
| **T3a Instance** | `mxgraph.aws4.t3a_instance` | AMD burstable instances |
| **T4g Instance** | `mxgraph.aws4.t4g_instance` | Graviton2 burstable instances |
| **Trainium Instance** | `mxgraph.aws4.trainium_instance` | Trainium training instances |
| **X1 Instance** | `mxgraph.aws4.x1_instance` | Memory-optimized instances |
| **X1e Instance** | `mxgraph.aws4.x1e_instance` | Enhanced memory-optimized instances |
| **Z1d Instance** | `mxgraph.aws4.z1d_instance` | High frequency instances |
| **Amazon Elastic Beanstalk** | `mxgraph.aws4.elastic_beanstalk` | Application deployment platform |
| **AWS Batch** | `mxgraph.aws4.batch` | Batch computing service |
| **AWS Fargate** | `mxgraph.aws4.fargate` | Serverless containers |
| **AWS Lightsail** | `mxgraph.aws4.lightsail` | Simplified virtual private servers |
| **Lightsail for Research** | `mxgraph.aws4.lightsail_for_research` | Research computing instances |
| **AWS App Runner** | `mxgraph.aws4.app_runner` | Containerized application service |
| **AWS Outposts** | `mxgraph.aws4.outposts` | On-premises AWS infrastructure |
| **Outposts Family** | `mxgraph.aws4.outposts_family` | Outposts product family |
| **Outposts 1U and 2U Servers** | `mxgraph.aws4.outposts_1u_and_2u_servers` | Compact Outposts servers |
| **AWS Local Zones** | `mxgraph.aws4.local_zones` | Low-latency edge locations |
| **AWS Wavelength** | `mxgraph.aws4.wavelength` | 5G edge computing |
| **AWS Auto Scaling** | `mxgraph.aws4.auto_scaling` | Automatic scaling service |
| **Auto Scaling 2** | `mxgraph.aws4.auto_scaling2` | Auto Scaling variant |
| **Auto Scaling 3** | `mxgraph.aws4.auto_scaling3` | Auto Scaling variant |
| **Application Auto Scaling** | `mxgraph.aws4.application_auto_scaling` | Application-level auto scaling |
| **Spot Instance** | `mxgraph.aws4.spot_instance` | Spot EC2 instances |
| **Elastic IP Address** | `mxgraph.aws4.elastic_ip_address` | Static IP addresses |
| **Elastic Network Interface** | `mxgraph.aws4.elastic_network_interface` | Virtual network interface |
| **Elastic Fabric Adapter** | `mxgraph.aws4.elastic_fabric_adapter` | High performance networking |
| **Elastic Network Adapter** | `mxgraph.aws4.elastic_network_adapter` | Enhanced networking |
| **Elastic Inference** | `mxgraph.aws4.elastic_inference` | GPU acceleration |
| **Elastic Inference 2** | `mxgraph.aws4.elastic_inference_2` | GPU acceleration variant |
| **Elastic Block Store** | `mxgraph.aws4.elastic_block_store` | Block storage volumes |
| **EBS Volume GP3** | `mxgraph.aws4.elastic_block_store_volume_gp3` | General purpose SSD volumes |
| **EBS Data Lifecycle Manager** | `mxgraph.aws4.elastic_block_store_amazon_data_lifecycle_manager` | Automated snapshot management |
| **Elastic Load Balancing** | `mxgraph.aws4.elastic_load_balancing` | Load balancing service |
| **Elastic Compute Cloud** | `mxgraph.aws4.compute` | EC2 compute service |
| **Compute Optimizer** | `mxgraph.aws4.compute_optimizer` | Cost and performance optimization |
| **Optimized Instance** | `mxgraph.aws4.optimized_instance` | Optimized EC2 instances |
| **High Memory Instance** | `mxgraph.aws4.high_memory_instance` | High memory instances |
| **Dense Compute Node** | `mxgraph.aws4.dense_compute_node` | Dense compute nodes |
| **Dense Storage Node** | `mxgraph.aws4.dense_storage_node` | Dense storage nodes |
| **Habana Gaudi** | `mxgraph.aws4.habana_gaudi` | AI training accelerators |
| **Inferentia** | `mxgraph.aws4.inferentia` | Machine learning inference chips |
| **Bottlerocket** | `mxgraph.aws4.bottlerocket` | Container-optimized OS |
| **Deep Learning AMIs** | `mxgraph.aws4.deep_learning_amis` | Pre-configured ML AMIs |
| **Deep Learning Containers** | `mxgraph.aws4.deep_learning_containers` | Pre-configured ML containers |
| **Apache MXNet on AWS** | `mxgraph.aws4.apache_mxnet_on_aws` | MXNet framework |
| **TensorFlow on AWS** | `mxgraph.aws4.tensorflow_on_aws` | TensorFlow framework |
| **TorchServe** | `mxgraph.aws4.torchserve` | PyTorch model serving |
| **Neuron ML SDK** | `mxgraph.aws4.neuron_ml_sdk` | Machine learning SDK |
| **AWS ParallelCluster** | `mxgraph.aws4.parallel_cluster` | HPC cluster management |
| **AWS Parallel Computing Service** | `mxgraph.aws4.parallel_computing_service` | Parallel computing |
| **AWS Thinkbox Deadline** | `mxgraph.aws4.thinkbox_deadline` | Render farm management |
| **AWS Thinkbox Draft** | `mxgraph.aws4.thinkbox_draft` | Render management tool |
| **AWS Thinkbox Frost** | `mxgraph.aws4.thinkbox_frost` | File transfer service |
| **AWS Thinkbox Krakatoa** | `mxgraph.aws4.thinkbox_krakatoa` | Particle rendering |
| **AWS Thinkbox Sequoia** | `mxgraph.aws4.thinkbox_sequoia` | Render management |
| **AWS Thinkbox Stoke** | `mxgraph.aws4.thinkbox_stoke` | Particle simulation |
| **AWS Thinkbox XMesh** | `mxgraph.aws4.thinkbox_xmesh` | Mesh processing |
| **AWS Deadline Cloud** | `mxgraph.aws4.deadline_cloud` | Cloud render farm |
| **AWS SimSpace Weaver** | `mxgraph.aws4.simspace_weaver` | Large-scale simulations |
| **AWS Nitro Enclaves** | `mxgraph.aws4.nitro_enclaves` | Isolated compute environments |
| **AWS Cloud9** | `mxgraph.aws4.cloud9` | Cloud IDE |
| **AWS CloudShell** | `mxgraph.aws4.cloudshell` | Browser-based shell |
| **AWS Command Line Interface** | `mxgraph.aws4.command_line_interface` | CLI tool |
| **AWS Management Console** | `mxgraph.aws4.management_console` | Web-based console |
| **Management Console 2** | `mxgraph.aws4.management_console2` | Console variant |
| **AWS Tools and SDKs** | `mxgraph.aws4.tools_and_sdks` | Development tools |
| **External SDK** | `mxgraph.aws4.external_sdk` | External SDK integration |
| **External Toolkit** | `mxgraph.aws4.external_toolkit` | External toolkit integration |
| **AWS Cloud Development Kit** | `mxgraph.aws4.cloud_development_kit` | Infrastructure as code |
| **AWS Cloud Control API** | `mxgraph.aws4.cloud_control_api` | Resource management API |
| **AWS Distro for OpenTelemetry** | `mxgraph.aws4.distro_for_opentelemetry` | Observability distribution |
| **AWS Corretto** | `mxgraph.aws4.corretto` | OpenJDK distribution |
| **AWS Freertos** | `mxgraph.aws4.freertos` | Real-time operating system |
| **AWS Nova** | `mxgraph.aws4.nova` | Quantum computing |
| **Nova 2** | `mxgraph.aws4.nova2` | Quantum computing variant |
| **AWS Braket** | `mxgraph.aws4.braket` | Quantum computing service |
| **Braket Chandelier** | `mxgraph.aws4.braket_chandelier` | Quantum device |
| **Braket Chip** | `mxgraph.aws4.braket_chip` | Quantum processor |
| **Braket Embedded Simulator** | `mxgraph.aws4.braket_embedded_simulator` | Quantum simulator |
| **Braket Managed Simulator** | `mxgraph.aws4.braket_managed_simulator` | Managed quantum simulator |
| **Braket Noise Simulator** | `mxgraph.aws4.braket_noise_simulator` | Noise simulation |
| **Braket QPU** | `mxgraph.aws4.braket_qpu` | Quantum processing unit |
| **Braket Simulator** | `mxgraph.aws4.braket_simulator` | Quantum simulator |
| **Braket Simulator 1** | `mxgraph.aws4.braket_simulator_1` | Simulator variant 1 |
| **Braket Simulator 2** | `mxgraph.aws4.braket_simulator_2` | Simulator variant 2 |
| **Braket Simulator 3** | `mxgraph.aws4.braket_simulator_3` | Simulator variant 3 |
| **Braket Simulator 4** | `mxgraph.aws4.braket_simulator_4` | Simulator variant 4 |
| **Braket State Vector** | `mxgraph.aws4.braket_state_vector` | Quantum state representation |
| **Braket Tensor Network** | `mxgraph.aws4.braket_tensor_network` | Tensor network simulator |
| **Quantum Technologies** | `mxgraph.aws4.quantum_technologies` | Quantum computing technologies |
| **Quantum Ledger Database** | `mxgraph.aws4.quantum_ledger_database` | Immutable ledger database |

### Storage Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **Amazon S3** | `mxgraph.aws4.s3` | Object storage buckets |
| **S3 Bucket** | `mxgraph.aws4.bucket` | S3 storage bucket |
| **S3 Bucket with Objects** | `mxgraph.aws4.bucket_with_objects` | S3 bucket containing objects |
| **S3 Batch Operations** | `mxgraph.aws4.s3_batch_operations` | Bulk operations on S3 objects |
| **S3 Express One Zone** | `mxgraph.aws4.s3_express_one_zone` | High-performance single-zone storage |
| **S3 File Gateway** | `mxgraph.aws4.s3_file_gateway` | File interface to S3 |
| **S3 Multi-Region Access Points** | `mxgraph.aws4.s3_multi_region_access_points` | Multi-region S3 access |
| **S3 Object Lambda** | `mxgraph.aws4.s3_object_lambda` | Transform objects on retrieval |
| **S3 Object Lambda Access Points** | `mxgraph.aws4.s3_object_lambda_access_points` | Object Lambda access points |
| **S3 Object Lock** | `mxgraph.aws4.s3_object_lock` | Write-once-read-many storage |
| **S3 on Outposts** | `mxgraph.aws4.s3_on_outposts` | S3 on-premises |
| **S3 on Outposts Storage** | `mxgraph.aws4.s3_on_outposts_storage` | Outposts storage |
| **S3 Replication Time Control** | `mxgraph.aws4.s3_replication_time_control` | Cross-region replication |
| **S3 Select** | `mxgraph.aws4.s3_select` | SQL queries on S3 objects |
| **S3 Storage Lens** | `mxgraph.aws4.s3_storage_lens` | Storage analytics |
| **S3 Tables** | `mxgraph.aws4.s3_tables` | Tabular data storage |
| **S3 Vectors** | `mxgraph.aws4.s3_vectors` | Vector data storage |
| **Simple Storage Service Directory Bucket** | `mxgraph.aws4.simple_storage_service_directory_bucket` | Directory-style bucket |
| **Simple Storage Service S3 Glacier Instant Retrieval** | `mxgraph.aws4.simple_storage_service_s3_glacier_instant_retrieval` | Instant access archive storage |
| **Amazon EBS** | `mxgraph.aws4.ebs` | Block storage volumes |
| **EBS Volume** | `mxgraph.aws4.volume` | EBS storage volume |
| **EBS Snapshot** | `mxgraph.aws4.snapshot` | EBS volume snapshot |
| **EBS Cached Volume** | `mxgraph.aws4.cached_volume` | Cached storage volume |
| **EBS Non-Cached Volume** | `mxgraph.aws4.non_cached_volume` | Non-cached storage volume |
| **Multiple Volumes Resource** | `mxgraph.aws4.multiple_volumes_resource` | Multiple EBS volumes |
| **Amazon EFS** | `mxgraph.aws4.efs` | Elastic file system |
| **EFS Standard** | `mxgraph.aws4.efs_standard` | Standard EFS storage class |
| **EFS Infrequent Access** | `mxgraph.aws4.efs_infrequentaccess` | Infrequent access storage class |
| **Elastic File System** | `mxgraph.aws4.elastic_file_system` | Managed file system |
| **Elastic File System Elastic Throughput** | `mxgraph.aws4.elastic_file_system_elastic_throughput` | Bursting throughput mode |
| **Elastic File System Infrequent Access** | `mxgraph.aws4.elastic_file_system_infrequent_access` | Cost-optimized storage tier |
| **Elastic File System Intelligent Tiering** | `mxgraph.aws4.elastic_file_system_intelligent_tiering` | Automatic tiering |
| **Elastic File System One Zone** | `mxgraph.aws4.elastic_file_system_one_zone` | Single availability zone |
| **Elastic File System One Zone Infrequent Access** | `mxgraph.aws4.elastic_file_system_one_zone_infrequent_access` | One zone IA tier |
| **Elastic File System One Zone Standard** | `mxgraph.aws4.elastic_file_system_one_zone_standard` | One zone standard tier |
| **Elastic File System Standard** | `mxgraph.aws4.elastic_file_system_standard` | Standard storage tier |
| **Elastic File System Standard Infrequent Access** | `mxgraph.aws4.elastic_file_system_standard_infrequent_access` | Standard IA tier |
| **Amazon FSx** | `mxgraph.aws4.fsx` | Managed file systems |
| **FSx File Gateway** | `mxgraph.aws4.fsx_file_gateway` | File gateway for FSx |
| **FSx for Lustre** | `mxgraph.aws4.fsx_for_lustre` | High-performance file system |
| **FSx for NetApp ONTAP** | `mxgraph.aws4.fsx_for_netapp_ontap` | NetApp file system |
| **FSx for OpenZFS** | `mxgraph.aws4.fsx_for_openzfs` | OpenZFS file system |
| **FSx for Windows File Server** | `mxgraph.aws4.fsx_for_windows_file_server` | Windows file server |
| **File Cache** | `mxgraph.aws4.file_cache` | High-performance file cache |
| **File Cache Hybrid NFS Linked Datasets** | `mxgraph.aws4.file_cache_hybrid_nfs_linked_datasets` | Hybrid NFS cache |
| **File Cache On-Premises NFS Linked Datasets** | `mxgraph.aws4.file_cache_on_premises_nfs_linked_datasets` | On-premises NFS cache |
| **File Cache S3 Linked Datasets** | `mxgraph.aws4.file_cache_s3_linked_datasets` | S3-linked cache |
| **File System** | `mxgraph.aws4.file_system` | Generic file system |
| **Amazon Glacier** | `mxgraph.aws4.glacier` | Archive storage |
| **Glacier Deep Archive** | `mxgraph.aws4.glacier_deep_archive` | Long-term archive storage |
| **Cold Storage** | `mxgraph.aws4.cold_storage` | Cold storage tier |
| **Archive** | `mxgraph.aws4.archive` | Archive storage |
| **Infrequent Access Storage Class** | `mxgraph.aws4.infrequent_access_storage_class` | IA storage tier |
| **Standard IA** | `mxgraph.aws4.standard_ia` | Standard infrequent access |
| **One Zone IA** | `mxgraph.aws4.one_zone_ia` | Single zone infrequent access |
| **Intelligent Tiering** | `mxgraph.aws4.intelligent_tiering` | Automatic storage tiering |
| **Amazon Storage Gateway** | `mxgraph.aws4.storage_gateway` | Hybrid cloud storage |
| **File Gateway** | `mxgraph.aws4.file_gateway` | File interface gateway |
| **Tape Gateway** | `mxgraph.aws4.tape_gateway` | Virtual tape library |
| **Volume Gateway** | `mxgraph.aws4.volume_gateway` | Block storage gateway |
| **Virtual Tape Library** | `mxgraph.aws4.virtual_tape_library` | Virtual tape storage |
| **Tape Storage** | `mxgraph.aws4.tape_storage` | Tape backup storage |
| **Storage** | `mxgraph.aws4.storage` | Generic storage |
| **Disk** | `mxgraph.aws4.disk` | Storage disk |
| **Amazon Snowball** | `mxgraph.aws4.snowball` | Data transfer appliance |
| **Snowball Edge** | `mxgraph.aws4.snowball_edge` | Edge computing appliance |
| **Snowcone** | `mxgraph.aws4.snowcone` | Portable data transfer |
| **Snowmobile** | `mxgraph.aws4.snowmobile` | Exabyte-scale data transfer |
| **Data Transfer Terminal** | `mxgraph.aws4.data_transfer_terminal` | Data transfer endpoint |
| **Import/Export** | `mxgraph.aws4.import_export` | Data import/export service |
| **AWS Backup** | `mxgraph.aws4.backup` | Centralized backup service |
| **Backup Vault** | `mxgraph.aws4.backup_vault` | Backup storage vault |
| **Backup Plan** | `mxgraph.aws4.backup_plan` | Backup policy definition |
| **Backup Restore** | `mxgraph.aws4.backup_restore` | Backup restoration |
| **Backup Virtual Machine** | `mxgraph.aws4.backup_virtual_machine` | VM backup |
| **Backup Virtual Machine Monitor** | `mxgraph.aws4.backup_virtual_machine_monitor` | VM backup monitoring |
| **Backup Gateway** | `mxgraph.aws4.backup_gateway` | Backup gateway service |
| **Backup Audit Manager** | `mxgraph.aws4.backup_audit_manager` | Backup compliance |
| **Backup Compliance Reporting** | `mxgraph.aws4.backup_compliance_reporting` | Compliance reports |
| **Backup Recovery Point Objective** | `mxgraph.aws4.backup_recovery_point_objective` | RPO configuration |
| **Backup Recovery Time Objective** | `mxgraph.aws4.backup_recovery_time_objective` | RTO configuration |
| **Backup Compute** | `mxgraph.aws4.backup_compute` | Compute backup |
| **Backup Database** | `mxgraph.aws4.backup_database` | Database backup |
| **Backup Storage** | `mxgraph.aws4.backup_storage` | Storage backup |
| **AWS Backup for AWS CloudFormation** | `mxgraph.aws4.aws_backup_for_aws_cloudformation` | CloudFormation backup |
| **AWS Backup Legal Hold** | `mxgraph.aws4.aws_backup_legal_hold` | Legal retention |
| **AWS Backup Support for Amazon FSx for NetApp ONTAP** | `mxgraph.aws4.aws_backup_support_for_amazon_fsx_for_netapp_ontap` | FSx ONTAP backup |
| **AWS Backup Vault Lock** | `mxgraph.aws4.aws_backup_vault_lock` | Immutable backup vault |
| **AWS Backup Virtual Machine Monitor** | `mxgraph.aws4.aws_backup_virtual_machine_monitor` | VM monitoring |
| **Backup AWS Backup Support for Amazon S3** | `mxgraph.aws4.backup_aws_backup_support_for_amazon_s3` | S3 backup support |
| **Backup AWS Backup Support for VMware Workloads** | `mxgraph.aws4.backup_aws_backup_support_for_vmware_workloads` | VMware backup |
| **Backint Agent** | `mxgraph.aws4.backint_agent` | SAP backup agent |

### Database Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **Amazon RDS** | `mxgraph.aws4.rds` | Relational database service |
| **RDS Instance** | `mxgraph.aws4.rds_instance` | Individual database instance |
| **RDS Instance Alt** | `mxgraph.aws4.rds_instance_alt` | RDS instance variant |
| **RDS Blue/Green Deployments** | `mxgraph.aws4.rds_blue_green_deployments` | Zero-downtime deployments |
| **RDS Multi-AZ** | `mxgraph.aws4.rds_multi_az` | Multi-availability zone deployment |
| **RDS Multi-AZ DB Cluster** | `mxgraph.aws4.rds_multi_az_db_cluster` | Multi-AZ cluster |
| **RDS Optimized Writes** | `mxgraph.aws4.rds_optimized_writes` | Write-optimized instances |
| **RDS PIOP** | `mxgraph.aws4.rds_piop` | Provisioned IOPS |
| **RDS PIOPS** | `mxgraph.aws4.rds_piops` | Provisioned IOPS variant |
| **RDS Proxy** | `mxgraph.aws4.rds_proxy` | Database connection pooling |
| **RDS Proxy Alt** | `mxgraph.aws4.rds_proxy_alt` | RDS Proxy variant |
| **RDS Trusted Language Extensions for PostgreSQL** | `mxgraph.aws4.rds_trusted_language_extensions_for_postgresql` | PostgreSQL extensions |
| **RDS on VMware** | `mxgraph.aws4.rds_on_vmware` | RDS on VMware Cloud |
| **RDS MySQL Instance** | `mxgraph.aws4.rds_mysql_instance` | MySQL database instance |
| **RDS MySQL Instance Alt** | `mxgraph.aws4.rds_mysql_instance_alt` | MySQL instance variant |
| **MySQL DB Instance** | `mxgraph.aws4.mysql_db_instance` | MySQL database |
| **MySQL DB Instance Alternate** | `mxgraph.aws4.mysql_db_instance_alternate` | MySQL variant |
| **RDS PostgreSQL Instance** | `mxgraph.aws4.rds_postgresql_instance` | PostgreSQL database instance |
| **RDS PostgreSQL Instance Alt** | `mxgraph.aws4.rds_postgresql_instance_alt` | PostgreSQL instance variant |
| **PostgreSQL Instance** | `mxgraph.aws4.postgresql_instance` | PostgreSQL database |
| **RDS MariaDB Instance** | `mxgraph.aws4.rds_mariadb_instance` | MariaDB database instance |
| **RDS MariaDB Instance Alt** | `mxgraph.aws4.rds_mariadb_instance_alt` | MariaDB instance variant |
| **RDS Oracle Instance** | `mxgraph.aws4.rds_oracle_instance` | Oracle database instance |
| **RDS Oracle Instance Alt** | `mxgraph.aws4.rds_oracle_instance_alt` | Oracle instance variant |
| **Oracle DB Instance** | `mxgraph.aws4.oracle_db_instance` | Oracle database |
| **Oracle DB Instance Alternate** | `mxgraph.aws4.oracle_db_instance_alternate` | Oracle variant |
| **Oracle Database at AWS** | `mxgraph.aws4.oracle_database_at_aws` | Oracle on AWS |
| **RDS SQL Server Instance** | `mxgraph.aws4.rds_sql_server_instance` | SQL Server database instance |
| **RDS SQL Server Instance Alt** | `mxgraph.aws4.rds_sql_server_instance_alt` | SQL Server instance variant |
| **MS SQL Instance** | `mxgraph.aws4.ms_sql_instance` | Microsoft SQL Server |
| **MS SQL Instance Alternate** | `mxgraph.aws4.ms_sql_instance_alternate` | SQL Server variant |
| **SQL Primary** | `mxgraph.aws4.sql_primary` | Primary database |
| **SQL Replica** | `mxgraph.aws4.sql_replica` | Database replica |
| **DB Instance** | `mxgraph.aws4.db_instance` | Generic database instance |
| **DB Instance Read Replica** | `mxgraph.aws4.db_instance_read_replica` | Read replica |
| **DB Instance Standby** | `mxgraph.aws4.db_instance_standby` | Standby database |
| **DB on Instance** | `mxgraph.aws4.db_on_instance` | Database on EC2 |
| **DB on Instance 2** | `mxgraph.aws4.db_on_instance2` | Database on EC2 variant |
| **Database** | `mxgraph.aws4.database` | Generic database |
| **Generic Database** | `mxgraph.aws4.generic_database` | Generic database icon |
| **Amazon Aurora** | `mxgraph.aws4.aurora` | MySQL/PostgreSQL compatible database |
| **Aurora Instance** | `mxgraph.aws4.aurora_instance` | Aurora database instance |
| **Aurora Instance Alt** | `mxgraph.aws4.aurora_instance_alt` | Aurora instance variant |
| **Amazon DynamoDB** | `mxgraph.aws4.dynamodb` | NoSQL database |
| **DynamoDB DAX** | `mxgraph.aws4.dynamodb_dax` | DynamoDB accelerator |
| **DynamoDB Standard Access Table Class** | `mxgraph.aws4.dynamodb_standard_access_table_class` | Standard table class |
| **DynamoDB Standard Infrequent Access Table Class** | `mxgraph.aws4.dynamodb_standard_infrequent_access_table_class` | IA table class |
| **DynamoDB Stream** | `mxgraph.aws4.dynamodb_stream` | Change data capture |
| **Global Secondary Index** | `mxgraph.aws4.global_secondary_index` | DynamoDB GSI |
| **Amazon Redshift** | `mxgraph.aws4.redshift` | Data warehouse |
| **Redshift Auto Copy** | `mxgraph.aws4.redshift_auto_copy` | Automatic data loading |
| **Redshift Data Sharing Governance** | `mxgraph.aws4.redshift_data_sharing_governance` | Data sharing management |
| **Redshift ML** | `mxgraph.aws4.redshift_ml` | Machine learning in Redshift |
| **Redshift Query Editor v2.0 Light** | `mxgraph.aws4.redshift_query_editor_v20_light` | Query editor interface |
| **Redshift RA3** | `mxgraph.aws4.redshift_ra3` | Managed storage nodes |
| **Redshift Streaming Ingestion** | `mxgraph.aws4.redshift_streaming_ingestion` | Real-time data ingestion |
| **Amazon DocumentDB with MongoDB Compatibility** | `mxgraph.aws4.documentdb_with_mongodb_compatibility` | MongoDB-compatible database |
| **DocumentDB Elastic Clusters** | `mxgraph.aws4.documentdb_elastic_clusters` | Auto-scaling clusters |
| **Amazon Neptune** | `mxgraph.aws4.neptune` | Graph database |
| **Amazon ElastiCache** | `mxgraph.aws4.elasticache` | In-memory caching |
| **ElastiCache for Memcached** | `mxgraph.aws4.elasticache_for_memcached` | Memcached-compatible cache |
| **ElastiCache for Redis** | `mxgraph.aws4.elasticache_for_redis` | Redis-compatible cache |
| **ElastiCache for Valkey** | `mxgraph.aws4.elasticache_for_valkey` | Valkey-compatible cache |
| **Cache Node** | `mxgraph.aws4.cache_node` | Cache cluster node |
| **Amazon MemoryDB for Redis** | `mxgraph.aws4.memorydb_for_redis` | Redis-compatible database |
| **Amazon Keyspaces** | `mxgraph.aws4.keyspaces` | Apache Cassandra-compatible |
| **Amazon Timestream** | `mxgraph.aws4.timestream` | Time-series database |
| **Amazon QLDB** | `mxgraph.aws4.quantum_ledger_database` | Immutable ledger database |
| **Amazon Managed Apache Cassandra Service** | `mxgraph.aws4.managed_apache_cassandra_service` | Cassandra-compatible service |
| **Amazon Managed Streaming for Kafka** | `mxgraph.aws4.managed_streaming_for_kafka` | Apache Kafka service |
| **MSK Amazon MSK Connect** | `mxgraph.aws4.msk_amazon_msk_connect` | Kafka Connect integration |
| **Amazon OpenSearch Service** | `mxgraph.aws4.elasticsearch_service` | Search and analytics (Note: Use `elasticsearch_service` icon name as the icon library still uses the legacy Elasticsearch Service name) |
| **OpenSearch Service Cluster Administrator Node** | `mxgraph.aws4.opensearch_service_cluster_administrator_node` | Master node |
| **OpenSearch Service Data Node** | `mxgraph.aws4.opensearch_service_data_node` | Data node |
| **OpenSearch Service Index** | `mxgraph.aws4.opensearch_service_index` | Search index |
| **OpenSearch Service Traces** | `mxgraph.aws4.opensearch_service_traces` | Distributed tracing |
| **OpenSearch Service Ultrawarm Node** | `mxgraph.aws4.opensearch_service_ultrawarm_node` | Cost-optimized storage |
| **OpenSearch Dashboards** | `mxgraph.aws4.opensearch_dashboards` | Visualization interface |
| **OpenSearch Ingestion** | `mxgraph.aws4.opensearch_ingestion` | Data ingestion pipeline |
| **OpenSearch Observability** | `mxgraph.aws4.opensearch_observability` | Observability features |
| **Amazon Elasticsearch Service** | `mxgraph.aws4.elasticsearch_service` | Search service (legacy) |
| **Amazon CloudSearch** | `mxgraph.aws4.cloudsearch` | Managed search service |
| **CloudSearch 2** | `mxgraph.aws4.cloudsearch2` | CloudSearch variant |
| **Amazon RDS Proxy** | `mxgraph.aws4.rds_proxy` | Database connection pooling |
| **Data Table** | `mxgraph.aws4.data_table` | Tabular data |
| **Table** | `mxgraph.aws4.table` | Database table |
| **Data Set** | `mxgraph.aws4.data_set` | Dataset |
| **Data Stream** | `mxgraph.aws4.data_stream` | Streaming data |
| **Replication** | `mxgraph.aws4.replication` | Database replication |
| **Replication Time Control** | `mxgraph.aws4.replication_time_control` | RTC replication |

### Networking Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **VPC** | `mxgraph.aws4.group` with `grIcon=mxgraph.aws4.group_vpc` | Virtual Private Cloud container |
| **VPC 2** | `mxgraph.aws4.group` with `grIcon=mxgraph.aws4.group_vpc2` | VPC container variant |
| **Virtual Private Cloud** | `mxgraph.aws4.virtual_private_cloud` | VPC service |
| **VPC Virtual Private Cloud VPC** | `mxgraph.aws4.vpc_virtual_private_cloud_vpc` | VPC service variant |
| **Public Subnet** | `mxgraph.aws4.group` with `grIcon=mxgraph.aws4.group_public_subnet` | Public subnet container |
| **Private Subnet** | `mxgraph.aws4.group` with `grIcon=mxgraph.aws4.group_private_subnet` | Private subnet container |
| **Subnet** | `mxgraph.aws4.group` with `grIcon=mxgraph.aws4.group_subnet` | Generic subnet container |
| **Availability Zone** | `mxgraph.aws4.group` with `grIcon=mxgraph.aws4.group_availability_zone` | Availability zone container |
| **Region** | `mxgraph.aws4.group` with `grIcon=mxgraph.aws4.group_region` | Region container |
| **Internet Gateway** | `mxgraph.aws4.internet_gateway` | Internet gateway |
| **NAT Gateway** | `mxgraph.aws4.nat_gateway` | Network address translation |
| **VPC Carrier Gateway** | `mxgraph.aws4.vpc_carrier_gateway` | Mobile carrier gateway |
| **VPC Endpoint** | `mxgraph.aws4.vpc_endpoint` | Private AWS service access |
| **VPC Endpoints** | `mxgraph.aws4.endpoints` | Multiple VPC endpoints |
| **VPC Endpoint** | `mxgraph.aws4.endpoint` | Service endpoint |
| **VPC Privatelink** | `mxgraph.aws4.vpc_privatelink` | Private connectivity |
| **Privatelink** | `mxgraph.aws4.privatelink` | Private service access |
| **VPC Access Points** | `mxgraph.aws4.vpc_access_points` | S3 access points |
| **VPC Lattice** | `mxgraph.aws4.vpc_lattice` | Application networking |
| **VPC Network Access Analyzer** | `mxgraph.aws4.vpc_network_access_analyzer` | Network security analysis |
| **VPC Reachability Analyzer** | `mxgraph.aws4.vpc_reachability_analyzer` | Network path analysis |
| **VPC Traffic Mirroring** | `mxgraph.aws4.vpc_traffic_mirroring` | Network traffic inspection |
| **API Gateway** | `mxgraph.aws4.api_gateway` | REST/HTTP API management |
| **Application Load Balancer** | `mxgraph.aws4.application_load_balancer` | Layer 7 load balancer |
| **Network Load Balancer** | `mxgraph.aws4.network_load_balancer` | Layer 4 load balancer |
| **Classic Load Balancer** | `mxgraph.aws4.classic_load_balancer` | Classic load balancer |
| **Gateway Load Balancer** | `mxgraph.aws4.gateway_load_balancer` | Gateway load balancer |
| **Elastic Load Balancing** | `mxgraph.aws4.elastic_load_balancing` | Load balancing service |
| **Route 53** | `mxgraph.aws4.route_53` | DNS service |
| **Route 53 Application Recovery Controller** | `mxgraph.aws4.route_53_application_recovery_controller` | Multi-region failover |
| **Route 53 Readiness Checks** | `mxgraph.aws4.route_53_readiness_checks` | Resource readiness monitoring |
| **Route 53 Resolver** | `mxgraph.aws4.route_53_resolver` | DNS resolver |
| **Route 53 Resolver DNS Firewall** | `mxgraph.aws4.route_53_resolver_dns_firewall` | DNS filtering |
| **Route 53 Resolver Query Logging** | `mxgraph.aws4.route_53_resolver_query_logging` | DNS query logging |
| **Route 53 Routing Controls** | `mxgraph.aws4.route_53_routing_controls` | Traffic routing controls |
| **Hosted Zone** | `mxgraph.aws4.hosted_zone` | DNS hosted zone |
| **CloudFront** | `mxgraph.aws4.cloudfront` | Content delivery network |
| **CloudFront Functions** | `mxgraph.aws4.cloudfront_functions` | Edge computing functions |
| **Edge Location** | `mxgraph.aws4.edge_location` | CDN edge location |
| **Download Distribution** | `mxgraph.aws4.download_distribution` | Download CDN distribution |
| **Streaming Distribution** | `mxgraph.aws4.streaming_distribution` | Streaming CDN distribution |
| **AWS Global Accelerator** | `mxgraph.aws4.global_accelerator` | Network acceleration |
| **AWS Direct Connect** | `mxgraph.aws4.direct_connect` | Dedicated network connection |
| **AWS VPN Gateway** | `mxgraph.aws4.vpn_gateway` | VPN gateway |
| **VPN Connection** | `mxgraph.aws4.vpn_connection` | VPN connection |
| **Site-to-Site VPN** | `mxgraph.aws4.site_to_site_vpn` | Site-to-site VPN |
| **Client VPN** | `mxgraph.aws4.client_vpn` | Client VPN endpoint |
| **Customer Gateway** | `mxgraph.aws4.customer_gateway` | On-premises VPN gateway |
| **Virtual Gateway** | `mxgraph.aws4.virtual_gateway` | Virtual gateway |
| **AWS Transit Gateway** | `mxgraph.aws4.transit_gateway` | Network transit hub |
| **Transit Gateway Attachment** | `mxgraph.aws4.transit_gateway_attachment` | TGW attachment |
| **AWS Cloud WAN** | `mxgraph.aws4.cloud_wan` | Global network service |
| **Cloud WAN Segment Network** | `mxgraph.aws4.cloud_wan_segment_network` | Network segment |
| **Cloud WAN Transit Gateway Route Table Attachment** | `mxgraph.aws4.cloud_wan_transit_gateway_route_table_attachment` | Route table attachment |
| **Cloud WAN Virtual POP** | `mxgraph.aws4.cloud_wan_virtual_pop` | Virtual point of presence |
| **AWS Private 5G** | `mxgraph.aws4.private_5g` | Private 5G network |
| **AWS Telco Network Builder** | `mxgraph.aws4.telco_network_builder` | Network automation |
| **Route Table** | `mxgraph.aws4.route_table` | VPC route table |
| **Network Access Control List** | `mxgraph.aws4.network_access_control_list` | Network ACL |
| **Security Group** | `mxgraph.aws4.security_group` | Firewall rules |
| **Security Group** | `mxgraph.aws4.group` with `grIcon=mxgraph.aws4.group_security_group` | Security group container |
| **Network Firewall** | `mxgraph.aws4.network_firewall` | Managed firewall service |
| **Network Firewall Endpoints** | `mxgraph.aws4.network_firewall_endpoints` | Firewall endpoints |
| **Generic Firewall** | `mxgraph.aws4.generic_firewall` | Generic firewall icon |
| **Flow Logs** | `mxgraph.aws4.flow_logs` | VPC flow logging |
| **Peering** | `mxgraph.aws4.peering` | VPC peering connection |
| **Router** | `mxgraph.aws4.router` | Network router |
| **Internet** | `mxgraph.aws4.internet` | Internet connection |
| **Internet Alt 1** | `mxgraph.aws4.internet_alt1` | Internet variant 1 |
| **Internet Alt 2** | `mxgraph.aws4.internet_alt2` | Internet variant 2 |
| **Internet Alt 22** | `mxgraph.aws4.internet_alt22` | Internet variant 22 |
| **Globe** | `mxgraph.aws4.globe` | Global network |
| **Networking and Content Delivery** | `mxgraph.aws4.networking_and_content_delivery` | Networking category |

### AI/ML Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **Amazon Bedrock** | `mxgraph.aws4.bedrock` | Foundation models |
| **Amazon SageMaker** | `mxgraph.aws4.sagemaker` | Machine learning platform |
| **SageMaker 2** | `mxgraph.aws4.sagemaker_2` | SageMaker variant |
| **SageMaker Canvas** | `mxgraph.aws4.sagemaker_canvas` | No-code ML interface |
| **SageMaker Geospatial ML** | `mxgraph.aws4.sagemaker_geospatial_ml` | Geospatial machine learning |
| **SageMaker Ground Truth** | `mxgraph.aws4.sagemaker_ground_truth` | Data labeling |
| **SageMaker Model** | `mxgraph.aws4.sagemaker_model` | ML model |
| **SageMaker Notebook** | `mxgraph.aws4.sagemaker_notebook` | ML notebook instance |
| **SageMaker Shadow Testing** | `mxgraph.aws4.sagemaker_shadow_testing` | Model testing |
| **SageMaker Studio Lab** | `mxgraph.aws4.sagemaker_studio_lab` | Free ML environment |
| **SageMaker Train** | `mxgraph.aws4.sagemaker_train` | Model training |
| **Amazon Comprehend** | `mxgraph.aws4.comprehend` | NLP service |
| **Amazon Comprehend Medical** | `mxgraph.aws4.comprehend_medical` | Medical NLP |
| **Amazon Rekognition** | `mxgraph.aws4.rekognition` | Image/video analysis |
| **Rekognition 2** | `mxgraph.aws4.rekognition_2` | Rekognition variant |
| **Rekognition Image** | `mxgraph.aws4.rekognition_image` | Image analysis |
| **Rekognition Video** | `mxgraph.aws4.rekognition_video` | Video analysis |
| **Amazon Textract** | `mxgraph.aws4.textract` | Document text extraction |
| **Textract Analyze Lending** | `mxgraph.aws4.textract_analyze_lending` | Lending document analysis |
| **Amazon Transcribe** | `mxgraph.aws4.transcribe` | Speech-to-text |
| **Amazon Translate** | `mxgraph.aws4.translate` | Language translation |
| **Amazon Polly** | `mxgraph.aws4.polly` | Text-to-speech |
| **Amazon Lex** | `mxgraph.aws4.lex` | Conversational AI |
| **Amazon Personalize** | `mxgraph.aws4.personalize` | Recommendation engine |
| **Amazon Forecast** | `mxgraph.aws4.forecast` | Time-series forecasting |
| **Amazon Kendra** | `mxgraph.aws4.kendra` | Intelligent search |
| **Amazon Augmented AI** | `mxgraph.aws4.augmented_ai` | Human review workflows |
| **Amazon CodeWhisperer** | `mxgraph.aws4.codewhisperer` | AI code companion |
| **Amazon Lookout for Equipment** | `mxgraph.aws4.lookout_for_equipment` | Equipment monitoring |
| **Amazon Lookout for Metrics** | `mxgraph.aws4.lookout_for_metrics` | Anomaly detection |
| **Amazon Lookout for Vision** | `mxgraph.aws4.lookout_for_vision` | Visual anomaly detection |
| **Amazon Fraud Detector** | `mxgraph.aws4.fraud_detector` | Fraud detection |
| **Amazon Monitron** | `mxgraph.aws4.monitron` | Equipment monitoring |
| **Amazon DevOps Guru** | `mxgraph.aws4.devops_guru` | ML-powered operations |
| **DevOps Guru Insights** | `mxgraph.aws4.devops_guru_insights` | Operational insights |
| **Amazon CodeGuru** | `mxgraph.aws4.codeguru` | Code review service |
| **CodeGuru 2** | `mxgraph.aws4.codeguru_2` | CodeGuru variant |
| **Amazon CodeGuru Reviewer** | `mxgraph.aws4.codeguru` | Automated code reviews |
| **Amazon CodeGuru Profiler** | `mxgraph.aws4.codeguru` | Application profiling |
| **Machine Learning** | `mxgraph.aws4.machine_learning` | Generic ML service |

### Analytics Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **Amazon Kinesis** | `mxgraph.aws4.kinesis` | Real-time streaming |
| **Kinesis Data Streams** | `mxgraph.aws4.kinesis_data_streams` | Real-time data streaming |
| **Kinesis Data Firehose** | `mxgraph.aws4.kinesis_data_firehose` | Data delivery service |
| **Kinesis Data Analytics** | `mxgraph.aws4.kinesis_data_analytics` | Stream processing |
| **Kinesis Video Streams** | `mxgraph.aws4.kinesis_video_streams` | Video streaming |
| **Amazon Managed Service for Apache Flink** | `mxgraph.aws4.managed_service_for_apache_flink` | Stream processing |
| **Amazon EMR** | `mxgraph.aws4.emr` | Big data processing |
| **EMR Engine** | `mxgraph.aws4.emr_engine` | EMR processing engine |
| **EMR Engine MapR M3** | `mxgraph.aws4.emr_engine_mapr_m3` | MapR M3 engine |
| **EMR Engine MapR M5** | `mxgraph.aws4.emr_engine_mapr_m5` | MapR M5 engine |
| **EMR Engine MapR M7** | `mxgraph.aws4.emr_engine_mapr_m7` | MapR M7 engine |
| **HDFS Cluster** | `mxgraph.aws4.hdfs_cluster` | Hadoop cluster |
| **Amazon Athena** | `mxgraph.aws4.athena` | Interactive query service |
| **Athena Data Source Connectors** | `mxgraph.aws4.athena_data_source_connectors` | Data source connectors |
| **Amazon QuickSight** | `mxgraph.aws4.quicksight` | Business intelligence |
| **QuickSight Paginated Reports** | `mxgraph.aws4.quicksight_paginated_reports` | Scheduled reports |
| **Amazon DataZone** | `mxgraph.aws4.datazone` | Data governance |
| **DataZone Business Data Catalog** | `mxgraph.aws4.datazone_business_data_catalog` | Business catalog |
| **DataZone Data Portal** | `mxgraph.aws4.datazone_data_portal` | Data access portal |
| **DataZone Data Projects** | `mxgraph.aws4.datazone_data_projects` | Data projects |
| **AWS Glue** | `mxgraph.aws4.glue` | ETL service |
| **AWS Glue Data Quality** | `mxgraph.aws4.aws_glue_data_quality` | Data quality checks |
| **AWS Glue for Ray** | `mxgraph.aws4.aws_glue_for_ray` | Ray framework support |
| **Glue Crawlers** | `mxgraph.aws4.glue_crawlers` | Data catalog crawlers |
| **Glue Data Catalog** | `mxgraph.aws4.glue_data_catalog` | Data catalog |
| **Glue DataBrew** | `mxgraph.aws4.glue_databrew` | Data preparation |
| **Glue Elastic Views** | `mxgraph.aws4.glue_elastic_views` | Materialized views |
| **Amazon Lake Formation** | `mxgraph.aws4.lake_formation` | Data lake management |
| **Data Lake Resource Icon** | `mxgraph.aws4.data_lake_resource_icon` | Data lake resource |
| **Amazon FinSpace** | `mxgraph.aws4.finspace` | Financial data management |
| **Amazon Data Pipeline** | `mxgraph.aws4.data_pipeline` | Data workflow orchestration |
| **Amazon DataSync** | `mxgraph.aws4.datasync` | Data transfer service |
| **DataSync Discovery** | `mxgraph.aws4.datasync_discovery` | On-premises discovery |
| **AWS AppFlow** | `mxgraph.aws4.appflow` | SaaS data integration |
| **Amazon EventBridge Pipes** | `mxgraph.aws4.eventbridge_pipes` | Point-to-point integrations |
| **Analytics** | `mxgraph.aws4.analytics` | Generic analytics service |

### Security and Identity Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **AWS IAM** | `mxgraph.aws4.iam` | Identity and access management |
| **Identity and Access Management** | `mxgraph.aws4.identity_and_access_management` | IAM service |
| **IAM Roles Anywhere** | `mxgraph.aws4.identity_access_management_iam_roles_anywhere` | On-premises IAM roles |
| **IAM Role** | `mxgraph.aws4.role` | IAM role |
| **IAM Policy** | `mxgraph.aws4.policy` | IAM policy |
| **IAM Permissions** | `mxgraph.aws4.permissions` | Access permissions |
| **Permissions 2** | `mxgraph.aws4.permissions_2` | Permissions variant |
| **IAM User** | `mxgraph.aws4.user` | IAM user |
| **IAM Users** | `mxgraph.aws4.users` | Multiple IAM users |
| **Authenticated User** | `mxgraph.aws4.authenticated_user` | Authenticated user |
| **AWS Secrets Manager** | `mxgraph.aws4.secrets_manager` | Secrets management |
| **AWS KMS** | `mxgraph.aws4.kms` | Key management service |
| **Key Management Service** | `mxgraph.aws4.key_management_service` | KMS service |
| **KMS External Key Store** | `mxgraph.aws4.key_management_service_external_key_store` | External key management |
| **Data Encryption Key** | `mxgraph.aws4.data_encryption_key` | Encryption key |
| **AWS Certificate Manager** | `mxgraph.aws4.certificate_manager` | SSL/TLS certificates |
| **Certificate Manager 2** | `mxgraph.aws4.certificate_manager_2` | Certificate Manager variant |
| **Certificate Manager 3** | `mxgraph.aws4.certificate_manager_3` | Certificate Manager variant |
| **AWS Private Certificate Authority** | `mxgraph.aws4.private_certificate_authority` | Private CA |
| **AWS Signer** | `mxgraph.aws4.signer` | Code signing |
| **SSL Padlock** | `mxgraph.aws4.ssl_padlock` | SSL/TLS security |
| **AWS WAF** | `mxgraph.aws4.waf` | Web application firewall |
| **WAF Bad Bot** | `mxgraph.aws4.waf_bad_bot` | Bot protection |
| **WAF Bot** | `mxgraph.aws4.waf_bot` | Bot management |
| **WAF Bot Control** | `mxgraph.aws4.waf_bot_control` | Advanced bot control |
| **WAF Labels** | `mxgraph.aws4.waf_labels` | WAF labeling |
| **WAF Managed Rule** | `mxgraph.aws4.waf_managed_rule` | Managed rules |
| **WAF Rule** | `mxgraph.aws4.waf_rule` | Custom rules |
| **AWS Shield** | `mxgraph.aws4.shield` | DDoS protection |
| **Shield 2** | `mxgraph.aws4.shield2` | Shield variant |
| **Shield Advanced** | `mxgraph.aws4.shield_shield_advanced` | Advanced DDoS protection |
| **AWS GuardDuty** | `mxgraph.aws4.guardduty` | Threat detection |
| **Amazon Inspector** | `mxgraph.aws4.inspector` | Security assessment |
| **AWS Security Hub** | `mxgraph.aws4.security_hub` | Security findings aggregation |
| **Security Hub Finding** | `mxgraph.aws4.security_hub_finding` | Security finding |
| **AWS Macie** | `mxgraph.aws4.macie` | Data security and privacy |
| **AWS Detective** | `mxgraph.aws4.detective` | Security investigation |
| **AWS Access Analyzer** | `mxgraph.aws4.access_analyzer` | Access policy analysis |
| **AWS Verified Access** | `mxgraph.aws4.verified_access` | Zero-trust network access |
| **AWS Verified Permissions** | `mxgraph.aws4.verified_permissions` | Fine-grained authorization |
| **AWS Firewall Manager** | `mxgraph.aws4.firewall_manager` | Centralized firewall management |
| **AWS Artifact** | `mxgraph.aws4.artifact` | Compliance reports |
| **AWS Audit Manager** | `mxgraph.aws4.audit_manager` | Compliance auditing |
| **AWS Config** | `mxgraph.aws4.config` | Configuration management |
| **AWS CloudHSM** | `mxgraph.aws4.cloudhsm` | Hardware security module |
| **AWS Directory Service** | `mxgraph.aws4.directory_service` | Managed Microsoft AD |
| **Simple AD** | `mxgraph.aws4.simple_ad` | Simple Active Directory |
| **Managed MS AD** | `mxgraph.aws4.managed_ms_ad` | Managed Microsoft AD |
| **AD Connector** | `mxgraph.aws4.ad_connector` | AD connector |
| **AWS Single Sign-On** | `mxgraph.aws4.single_sign_on` | SSO service |
| **AWS Cognito** | `mxgraph.aws4.cognito` | User authentication |
| **AWS Security Incident Response** | `mxgraph.aws4.security_incident_response` | Incident response |
| **AWS Security Lake** | `mxgraph.aws4.security_lake` | Security data lake |
| **Security Identity and Compliance** | `mxgraph.aws4.security_identity_and_compliance` | Security category |
| **Long Term Security Credential** | `mxgraph.aws4.long_term_security_credential` | Long-term credentials |
| **Temporary Security Credential** | `mxgraph.aws4.temporary_security_credential` | Temporary credentials |
| **MFA Token** | `mxgraph.aws4.mfa_token` | Multi-factor authentication |
| **SAML Token** | `mxgraph.aws4.saml_token` | SAML authentication |
| **Credentials** | `mxgraph.aws4.credentials` | Access credentials |
| **Encrypted Data** | `mxgraph.aws4.encrypted_data` | Encrypted data storage |

### Monitoring and Management Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **Amazon CloudWatch** | `mxgraph.aws4.cloudwatch` | Monitoring and logging |
| **CloudWatch 2** | `mxgraph.aws4.cloudwatch_2` | CloudWatch variant |
| **CloudWatch Logs** | `mxgraph.aws4.cloudwatch_logs` | Log management |
| **CloudWatch Metrics Insights** | `mxgraph.aws4.cloudwatch_metrics_insights` | Metrics analysis |
| **CloudWatch Cross-Account Observability** | `mxgraph.aws4.cloudwatch_cross_account_observability` | Cross-account monitoring |
| **CloudWatch Data Protection** | `mxgraph.aws4.cloudwatch_data_protection` | Data protection monitoring |
| **CloudWatch Evidently** | `mxgraph.aws4.cloudwatch_evidently` | Feature experimentation |
| **CloudWatch RUM** | `mxgraph.aws4.cloudwatch_rum` | Real user monitoring |
| **CloudWatch Synthetics** | `mxgraph.aws4.cloudwatch_synthetics` | Canary monitoring |
| **AWS X-Ray** | `mxgraph.aws4.xray` | Distributed tracing |
| **AWS Systems Manager** | `mxgraph.aws4.systems_manager` | Operational management |
| **Systems Manager Application Manager** | `mxgraph.aws4.systems_manager_application_manager` | Application management |
| **Systems Manager Change Calendar** | `mxgraph.aws4.systems_manager_change_calendar` | Change scheduling |
| **Systems Manager Change Manager** | `mxgraph.aws4.systems_manager_change_manager` | Change management |
| **Systems Manager Compliance** | `mxgraph.aws4.systems_manager_compliance` | Compliance monitoring |
| **Systems Manager Distributor** | `mxgraph.aws4.systems_manager_distributor` | Software distribution |
| **Systems Manager Incident Manager** | `mxgraph.aws4.systems_manager_incident_manager` | Incident response |
| **Systems Manager OpsCenter** | `mxgraph.aws4.systems_manager_opscenter` | Operations center |
| **Systems Manager Session Manager** | `mxgraph.aws4.systems_manager_session_manager` | Secure shell access |
| **Systems Manager Parameter Store** | `mxgraph.aws4.parameter_store` | Configuration parameters |
| **Systems Manager Patch Manager** | `mxgraph.aws4.patch_manager` | Patch management |
| **Systems Manager State Manager** | `mxgraph.aws4.state_manager` | Configuration management |
| **Systems Manager Run Command** | `mxgraph.aws4.run_command` | Remote command execution |
| **Systems Manager Maintenance Windows** | `mxgraph.aws4.maintenance_windows` | Maintenance scheduling |
| **AWS Config** | `mxgraph.aws4.config` | Configuration management |
| **AWS CloudTrail** | `mxgraph.aws4.cloudtrail` | API logging |
| **CloudTrail Lake** | `mxgraph.aws4.cloudtrail_cloudtrail_lake` | Event data lake |
| **AWS Service Catalog** | `mxgraph.aws4.service_catalog` | IT service catalog |
| **AWS Control Tower** | `mxgraph.aws4.control_tower` | Multi-account governance |
| **AWS Organizations** | `mxgraph.aws4.organizations` | Account management |
| **Organizations Account** | `mxgraph.aws4.organizations_account` | Organization account |
| **Organizations Account 2** | `mxgraph.aws4.organizations_account2` | Account variant |
| **Organizations Management Account** | `mxgraph.aws4.organizations_management_account` | Management account |
| **Organizations Management Account 2** | `mxgraph.aws4.organizations_management_account2` | Management account variant |
| **Organizations Organizational Unit** | `mxgraph.aws4.organizations_organizational_unit` | Organizational unit |
| **Organizations Organizational Unit 2** | `mxgraph.aws4.organizations_organizational_unit2` | OU variant |
| **AWS Resource Access Manager** | `mxgraph.aws4.resource_access_manager` | Resource sharing |
| **AWS Resource Explorer** | `mxgraph.aws4.resource_explorer` | Resource search |
| **AWS Trusted Advisor** | `mxgraph.aws4.trusted_advisor` | Best practices recommendations |
| **AWS Well-Architected Tool** | `mxgraph.aws4.well_architect_tool` | Architecture review |
| **AWS Well-Architected Tool** | `mxgraph.aws4.well_architected_tool` | Architecture review variant |
| **AWS Personal Health Dashboard** | `mxgraph.aws4.personal_health_dashboard` | Service health status |
| **AWS Cost Explorer** | `mxgraph.aws4.cost_explorer` | Cost analysis |
| **AWS Cost and Usage Report** | `mxgraph.aws4.cost_and_usage_report` | Cost reporting |
| **AWS Cost Management** | `mxgraph.aws4.cost_management` | Cost management |
| **AWS Budgets** | `mxgraph.aws4.budgets` | Budget management |
| **Budgets 2** | `mxgraph.aws4.budgets_2` | Budgets variant |
| **AWS Savings Plans** | `mxgraph.aws4.savings_plans` | Compute savings |
| **AWS Reserved Instance Reporting** | `mxgraph.aws4.reserved_instance_reporting` | RI reporting |
| **AWS Custom Billing Manager** | `mxgraph.aws4.custom_billing_manager` | Custom billing |
| **AWS Application Cost Profiler** | `mxgraph.aws4.application_cost_profiler` | Application cost analysis |
| **AWS Application Discovery Service** | `mxgraph.aws4.application_discovery_service` | Application discovery |
| **Application Discovery Service AWS Agentless Collector** | `mxgraph.aws4.application_discovery_service_aws_agentless_collector` | Agentless discovery |
| **Application Discovery Service AWS Discovery Agent** | `mxgraph.aws4.application_discovery_service_aws_discovery_agent` | Discovery agent |
| **Application Discovery Service Migration Evaluator Collector** | `mxgraph.aws4.application_discovery_service_migration_evaluator_collector` | Migration evaluation |
| **AWS Migration Evaluator** | `mxgraph.aws4.migration_evaluator` | Migration assessment |
| **AWS Migration Hub** | `mxgraph.aws4.migration_hub` | Migration tracking |
| **Migration Hub Refactor Spaces Applications** | `mxgraph.aws4.migration_hub_refactor_spaces_applications` | Application refactoring |
| **Migration Hub Refactor Spaces Environments** | `mxgraph.aws4.migration_hub_refactor_spaces_environments` | Environment refactoring |
| **Migration Hub Refactor Spaces Services** | `mxgraph.aws4.migration_hub_refactor_spaces_services` | Service refactoring |
| **AWS Resilience Hub** | `mxgraph.aws4.resilience_hub` | Resilience management |
| **AWS Application Recovery Controller** | `mxgraph.aws4.application_recovery_controller` | Multi-region recovery |
| **AWS Fault Injection Simulator** | `mxgraph.aws4.fault_injection_simulator` | Chaos engineering |
| **Monitoring** | `mxgraph.aws4.monitoring` | Generic monitoring |
| **Logs** | `mxgraph.aws4.logs` | Log storage |
| **Metrics** | `mxgraph.aws4.metrics` | Performance metrics |
| **Alarm** | `mxgraph.aws4.alarm` | CloudWatch alarm |
| **Alert** | `mxgraph.aws4.alert` | Alert notification |
| **Instance with CloudWatch** | `mxgraph.aws4.instance_with_cloudwatch` | Monitored instance |
| **Instance with CloudWatch 2** | `mxgraph.aws4.instance_with_cloudwatch2` | Monitored instance variant |
| **Management and Governance** | `mxgraph.aws4.management_and_governance` | Management category |

### Developer Tools

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **AWS CodePipeline** | `mxgraph.aws4.codepipeline` | CI/CD pipeline |
| **AWS CodeBuild** | `mxgraph.aws4.codebuild` | Build service |
| **AWS CodeDeploy** | `mxgraph.aws4.codedeploy` | Deployment service |
| **AWS CodeCommit** | `mxgraph.aws4.codecommit` | Git repository service |
| **AWS CodeStar** | `mxgraph.aws4.codestar` | Project management |
| **AWS CodeCatalyst** | `mxgraph.aws4.codecatalyst` | Software development workspace |
| **AWS CodeArtifact** | `mxgraph.aws4.codeartifact` | Package management |
| **Git Repository** | `mxgraph.aws4.git_repository` | Source code repository |
| **Source Code** | `mxgraph.aws4.source_code` | Source code |
| **Developer Tools** | `mxgraph.aws4.developer_tools` | Developer tools category |
| **Development Environment** | `mxgraph.aws4.development_environment` | Development environment |

### Application Integration Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **Amazon SQS** | `mxgraph.aws4.sqs` | Message queue |
| **Amazon SNS** | `mxgraph.aws4.sns` | Notification service |
| **Amazon EventBridge** | `mxgraph.aws4.eventbridge` | Event bus |
| **EventBridge Custom Event Bus Resource** | `mxgraph.aws4.eventbridge_custom_event_bus_resource` | Custom event bus |
| **EventBridge Default Event Bus Resource** | `mxgraph.aws4.eventbridge_default_event_bus_resource` | Default event bus |
| **EventBridge SAAS Partner Event Bus Resource** | `mxgraph.aws4.eventbridge_saas_partner_event_bus_resource` | Partner event bus |
| **EventBridge Pipes** | `mxgraph.aws4.eventbridge_pipes` | Point-to-point integrations |
| **EventBridge Scheduler** | `mxgraph.aws4.eventbridge_scheduler` | Event scheduling |
| **EventBridge Schema** | `mxgraph.aws4.eventbridge_schema` | Event schema |
| **EventBridge Schema Registry** | `mxgraph.aws4.eventbridge_schema_registry` | Schema management |
| **Custom Event Bus Resource** | `mxgraph.aws4.custom_event_bus_resource` | Custom bus |
| **Default Event Bus Resource** | `mxgraph.aws4.default_event_bus_resource` | Default bus |
| **SAAS Event Bus Resource** | `mxgraph.aws4.saas_event_bus_resource` | SaaS bus |
| **Event Resource** | `mxgraph.aws4.event_resource` | Event resource |
| **Event Event Based** | `mxgraph.aws4.event_event_based` | Event-based trigger |
| **Event Time Based** | `mxgraph.aws4.event_time_based` | Time-based trigger |
| **Event** | `mxgraph.aws4.event` | Generic event |
| **AWS AppSync** | `mxgraph.aws4.appsync` | GraphQL API |
| **AWS Step Functions** | `mxgraph.aws4.step_functions` | Workflow orchestration |
| **Express Workflow** | `mxgraph.aws4.express_workflow` | High-throughput workflows |
| **AWS MQ** | `mxgraph.aws4.mq` | Message broker |
| **MQ Broker** | `mxgraph.aws4.mq_broker` | ActiveMQ/RabbitMQ broker |
| **AWS Application Integration** | `mxgraph.aws4.application_integration` | Integration category |
| **Application** | `mxgraph.aws4.application` | Generic application |
| **Generic Application** | `mxgraph.aws4.generic_application` | Generic application icon |
| **Business Application** | `mxgraph.aws4.business_application` | Business application |
| **Mobile Application** | `mxgraph.aws4.mobile_application` | Mobile app |
| **Application Composer** | `mxgraph.aws4.application_composer` | Visual application builder |
| **Queue** | `mxgraph.aws4.queue` | Message queue |
| **Topic** | `mxgraph.aws4.topic` | Message topic |
| **Topic 2** | `mxgraph.aws4.topic_2` | Topic variant |
| **Message** | `mxgraph.aws4.message` | Message |
| **Chat** | `mxgraph.aws4.chat` | Chat service |

### IoT Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **AWS IoT Core** | `mxgraph.aws4.iot_core` | IoT device connectivity |
| **IoT Device Gateway** | `mxgraph.aws4.iot_device_gateway` | Device communication |
| **IoT Device Management** | `mxgraph.aws4.iot_device_management` | Device lifecycle |
| **IoT Device Management Fleet** | `mxgraph.aws4.iot_device_management_fleet` | Device fleet management |
| **IoT Device Jobs Resource** | `mxgraph.aws4.iot_device_jobs_resource` | Device job execution |
| **IoT Core Device Advisor** | `mxgraph.aws4.iot_core_device_advisor` | Device testing |
| **IoT Core Device Location** | `mxgraph.aws4.iot_core_device_location` | Device location tracking |
| **IoT Device Defender** | `mxgraph.aws4.iot_device_defender` | Device security |
| **IoT Device Defender IoT Device Jobs** | `mxgraph.aws4.iot_device_defender_iot_device_jobs` | Security jobs |
| **IoT Device Tester** | `mxgraph.aws4.iot_device_tester` | Device testing tool |
| **IoT Over the Air Update** | `mxgraph.aws4.iot_over_the_air_update` | OTA updates |
| **IoT Analytics** | `mxgraph.aws4.iot_analytics` | IoT data analytics |
| **IoT Analytics Channel** | `mxgraph.aws4.iot_analytics_channel` | Data channel |
| **IoT Analytics Data Store** | `mxgraph.aws4.iot_analytics_data_store` | Data storage |
| **IoT Analytics Dataset** | `mxgraph.aws4.iot_analytics_dataset` | Dataset |
| **IoT Analytics Pipeline** | `mxgraph.aws4.iot_analytics_pipeline` | Data pipeline |
| **IoT Events** | `mxgraph.aws4.iot_events` | Event detection |
| **IoT SiteWise** | `mxgraph.aws4.iot_sitewise` | Industrial data |
| **IoT SiteWise Asset** | `mxgraph.aws4.iot_sitewise_asset` | Industrial asset |
| **IoT SiteWise Asset Hierarchy** | `mxgraph.aws4.iot_sitewise_asset_hierarchy` | Asset structure |
| **IoT SiteWise Asset Model** | `mxgraph.aws4.iot_sitewise_asset_model` | Asset model |
| **IoT SiteWise Asset Properties** | `mxgraph.aws4.iot_sitewise_asset_properties` | Asset properties |
| **IoT SiteWise Data Streams** | `mxgraph.aws4.iot_sitewise_data_streams` | Data streaming |
| **IoT TwinMaker** | `mxgraph.aws4.iot_twinmaker` | Digital twins |
| **IoT FleetWise** | `mxgraph.aws4.iot_fleetwise` | Vehicle fleet data |
| **IoT RoboRunner** | `mxgraph.aws4.iot_roborunner` | Robotic operations |
| **IoT Things Graph** | `mxgraph.aws4.iot_things_graph` | Device modeling |
| **AWS IoT Greengrass** | `mxgraph.aws4.greengrass` | Edge computing |
| **IoT Greengrass Artifact** | `mxgraph.aws4.iot_greengrass_artifact` | Deployment artifact |
| **IoT Greengrass Component** | `mxgraph.aws4.iot_greengrass_component` | Software component |
| **IoT Greengrass Component Machine Learning** | `mxgraph.aws4.iot_greengrass_component_machine_learning` | ML component |
| **IoT Greengrass Component Nucleus** | `mxgraph.aws4.iot_greengrass_component_nucleus` | Core runtime |
| **IoT Greengrass Component Private** | `mxgraph.aws4.iot_greengrass_component_private` | Private component |
| **IoT Greengrass Component Public** | `mxgraph.aws4.iot_greengrass_component_public` | Public component |
| **IoT Greengrass Interprocess Communication** | `mxgraph.aws4.iot_greengrass_interprocess_communication` | IPC |
| **IoT Greengrass Protocol** | `mxgraph.aws4.iot_greengrass_protocol` | Communication protocol |
| **IoT Greengrass Recipe** | `mxgraph.aws4.iot_greengrass_recipe` | Component recipe |
| **IoT Greengrass Stream Manager** | `mxgraph.aws4.iot_greengrass_stream_manager` | Stream management |
| **IoT LoRaWAN Protocol** | `mxgraph.aws4.iot_lorawan_protocol` | LoRaWAN connectivity |
| **IoT ExpressLink** | `mxgraph.aws4.iot_expresslink` | Secure connectivity module |
| **IoT EduKit** | `mxgraph.aws4.iot_edukit` | Educational kit |
| **IoT 1-Click** | `mxgraph.aws4.iot_1click` | One-click actions |
| **IoT Button** | `mxgraph.aws4.iot_button` | Physical button device |
| **IoT Sailboat** | `mxgraph.aws4.iot_sailboat` | IoT device icon |
| **IoT Thing FreeRTOS Device** | `mxgraph.aws4.iot_thing_freertos_device` | FreeRTOS device |
| **IoT Thing Humidity Sensor** | `mxgraph.aws4.iot_thing_humidity_sensor` | Humidity sensor |
| **IoT Thing Industrial PC** | `mxgraph.aws4.iot_thing_industrial_pc` | Industrial computer |
| **IoT Thing PLC** | `mxgraph.aws4.iot_thing_plc` | Programmable logic controller |
| **IoT Thing Relay** | `mxgraph.aws4.iot_thing_relay` | Relay device |
| **IoT Thing Stacklight** | `mxgraph.aws4.iot_thing_stacklight` | Stack light |
| **IoT Thing Temperature Humidity Sensor** | `mxgraph.aws4.iot_thing_temperature_humidity_sensor` | Combined sensor |
| **IoT Thing Temperature Sensor** | `mxgraph.aws4.iot_thing_temperature_sensor` | Temperature sensor |
| **IoT Thing Temperature Vibration Sensor** | `mxgraph.aws4.iot_thing_temperature_vibration_sensor` | Multi-sensor |
| **IoT Thing Vibration Sensor** | `mxgraph.aws4.iot_thing_vibration_sensor` | Vibration sensor |
| **Internet of Things** | `mxgraph.aws4.internet_of_things` | IoT category |
| **Sensor** | `mxgraph.aws4.sensor` | Generic sensor |
| **Actuator** | `mxgraph.aws4.actuator` | Actuator device |
| **Hardware Board** | `mxgraph.aws4.hardware_board` | Hardware device |
| **Thermostat** | `mxgraph.aws4.thermostat` | Thermostat device |
| **Door Lock** | `mxgraph.aws4.door_lock` | Smart lock |
| **Camera** | `mxgraph.aws4.camera` | Camera device |
| **Camera 2** | `mxgraph.aws4.camera2` | Camera variant |
| **Echo** | `mxgraph.aws4.echo` | Echo device |
| **Fire TV** | `mxgraph.aws4.firetv` | Fire TV device |
| **Fire TV Stick** | `mxgraph.aws4.firetv_stick` | Fire TV Stick |
| **Alexa Enabled Device** | `mxgraph.aws4.alexa_enabled_device` | Alexa device |
| **Alexa for Business** | `mxgraph.aws4.alexa_for_business` | Business Alexa |
| **Alexa Skill** | `mxgraph.aws4.alexa_skill` | Alexa skill |
| **Alexa Smart Home Skill** | `mxgraph.aws4.alexa_smart_home_skill` | Smart home skill |
| **Alexa Voice Service** | `mxgraph.aws4.alexa_voice_service` | Voice service |
| **MQTT Protocol** | `mxgraph.aws4.mqtt_protocol` | MQTT messaging |
| **HTTP Protocol** | `mxgraph.aws4.http_protocol` | HTTP communication |
| **HTTP2 Protocol** | `mxgraph.aws4.http2_protocol` | HTTP/2 communication |

### Media Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **AWS Elemental MediaConnect** | `mxgraph.aws4.elemental_mediaconnect` | Live video transport |
| **AWS Elemental MediaConvert** | `mxgraph.aws4.elemental_mediaconvert` | Video transcoding |
| **AWS Elemental MediaLive** | `mxgraph.aws4.elemental_medialive` | Live video processing |
| **AWS Elemental MediaPackage** | `mxgraph.aws4.elemental_mediapackage` | Video packaging |
| **AWS Elemental MediaStore** | `mxgraph.aws4.elemental_mediastore` | Media storage |
| **AWS Elemental MediaTailor** | `mxgraph.aws4.elemental_mediatailor` | Ad insertion |
| **AWS Elemental** | `mxgraph.aws4.elemental` | Media services category |
| **Elemental Link** | `mxgraph.aws4.elemental_link` | Broadcast link |
| **MediaConnect Gateway** | `mxgraph.aws4.mediaconnect_gateway` | Media gateway |
| **AWS Elastic Transcoder** | `mxgraph.aws4.elastic_transcoder` | Video transcoding (legacy) |
| **AWS Kinesis Video Streams** | `mxgraph.aws4.kinesis_video_streams` | Video streaming |
| **AWS Interactive Video** | `mxgraph.aws4.interactive_video` | Interactive video |
| **AWS Media Services** | `mxgraph.aws4.media_services` | Media category |
| **AWS Nimble Studio** | `mxgraph.aws4.nimble_studio` | Content creation |
| **AWS Panorama** | `mxgraph.aws4.panorama` | Computer vision appliance |

### Migration and Transfer Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **AWS Database Migration Service** | `mxgraph.aws4.database_migration_service` | Database migration |
| **Database Migration Workflow Job** | `mxgraph.aws4.database_migration_workflow_job` | Migration workflow |
| **AWS Server Migration Service** | `mxgraph.aws4.server_migration_service` | Server migration |
| **AWS Application Migration Service** | `mxgraph.aws4.server_migration_service` | Application migration |
| **AWS CloudEndure Disaster Recovery** | `mxgraph.aws4.cloudendure_disaster_recovery` | DR service |
| **AWS CloudEndure Migration** | `mxgraph.aws4.cloudendure_migration` | Migration service |
| **AWS Transfer Family** | `mxgraph.aws4.transfer_family` | File transfer |
| **Transfer Family AWS AS2** | `mxgraph.aws4.transfer_family_aws_as2` | AS2 protocol |
| **Transfer for FTP Resource** | `mxgraph.aws4.transfer_for_ftp_resource` | FTP transfer |
| **Transfer for FTPS Resource** | `mxgraph.aws4.transfer_for_ftps_resource` | FTPS transfer |
| **Transfer for SFTP** | `mxgraph.aws4.transfer_for_sftp` | SFTP transfer |
| **Transfer for SFTP Resource** | `mxgraph.aws4.transfer_for_sftp_resource` | SFTP resource |
| **Migration and Transfer** | `mxgraph.aws4.migration_and_transfer` | Migration category |

### Container Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **Container 1** | `mxgraph.aws4.container_1` | Container icon 1 |
| **Container 2** | `mxgraph.aws4.container_2` | Container icon 2 |
| **Container 3** | `mxgraph.aws4.container_3` | Container icon 3 |
| **Containers** | `mxgraph.aws4.containers` | Container cluster |
| **Container Registry Image** | `mxgraph.aws4.container_registry_image` | Container image |
| **Cluster** | `mxgraph.aws4.cluster` | Container cluster |

### Other Services

| AWS Service | Shape Name | Example Usage |
|------------|-----------|---------------|
| **AWS Cloud** | `mxgraph.aws4.group` with `grIcon=mxgraph.aws4.group_aws_cloud` | AWS cloud boundary |
| **AWS Cloud Alt** | `mxgraph.aws4.group` with `grIcon=mxgraph.aws4.group_aws_cloud_alt` | AWS cloud variant |
| **User** | `mxgraph.aws4.user` | End users |
| **Users** | `mxgraph.aws4.users` | Multiple users |
| **Corporate Data Center** | `mxgraph.aws4.corporate_data_center` | On-premises data center |
| **Corporate Data Center 2** | `mxgraph.aws4.corporate_data_center2` | Data center variant |
| **Group Corporate Data Center** | `mxgraph.aws4.group` with `grIcon=mxgraph.aws4.group_corporate_data_center` | Data center container |
| **On-Premise** | `mxgraph.aws4.group` with `grIcon=mxgraph.aws4.group_on_premise` | On-premises container |
| **AWS CloudFormation** | `mxgraph.aws4.cloudformation` | Infrastructure as code |
| **Change Set** | `mxgraph.aws4.change_set` | CloudFormation change set |
| **Stack** | `mxgraph.aws4.stack` | CloudFormation stack |
| **Stack 2** | `mxgraph.aws4.stack2` | Stack variant |
| **Template** | `mxgraph.aws4.template` | CloudFormation template |
| **AWS Proton** | `mxgraph.aws4.proton` | Container and serverless deployment |
| **AWS App Mesh** | `mxgraph.aws4.app_mesh` | Service mesh |
| **Virtual Node** | `mxgraph.aws4.virtual_node` | App Mesh node |
| **Virtual Router** | `mxgraph.aws4.virtual_router` | App Mesh router |
| **Virtual Service** | `mxgraph.aws4.virtual_service` | App Mesh service |
| **Mesh** | `mxgraph.aws4.mesh` | Service mesh |
| **AWS Cloud Map** | `mxgraph.aws4.cloud_map` | Service discovery |
| **Cloud Map Resource** | `mxgraph.aws4.cloud_map_resource` | Service registry |
| **Namespace** | `mxgraph.aws4.namespace` | Service namespace |
| **AWS AppConfig** | `mxgraph.aws4.app_config` | Application configuration |
| **AWS AppFabric** | `mxgraph.aws4.appfabric` | SaaS app connectivity |
| **AWS App Studio** | `mxgraph.aws4.app_studio` | Application builder |
| **AWS App Wizard** | `mxgraph.aws4.app_wizard` | Application wizard |
| **AWS Amplify** | `mxgraph.aws4.amplify` | Full-stack development |
| **Amplify AWS Amplify Studio** | `mxgraph.aws4.amplify_aws_amplify_studio` | Visual development |
| **AWS WorkSpaces** | `mxgraph.aws4.workspaces` | Virtual desktops |
| **WorkSpaces Family** | `mxgraph.aws4.workspaces_family` | WorkSpaces category |
| **WorkSpaces Family Amazon WorkSpaces** | `mxgraph.aws4.workspaces_family_amazon_workspaces` | WorkSpaces service |
| **WorkSpaces Family Amazon WorkSpaces Core** | `mxgraph.aws4.workspaces_family_amazon_workspaces_core` | WorkSpaces Core |
| **WorkSpaces Thin Client** | `mxgraph.aws4.workspaces_thin_client` | Thin client |
| **WorkSpaces WorkSpaces Web** | `mxgraph.aws4.workspaces_workspaces_web` | Web access |
| **AWS AppStream 2.0** | `mxgraph.aws4.appstream_20` | Application streaming |
| **Desktop and App Streaming** | `mxgraph.aws4.desktop_and_app_streaming` | Streaming category |
| **AWS WorkDocs** | `mxgraph.aws4.workdocs` | Document collaboration |
| **AWS WorkMail** | `mxgraph.aws4.workmail` | Business email |
| **AWS WorkLink** | `mxgraph.aws4.worklink` | Mobile web access |
| **AWS Simple Email Service** | `mxgraph.aws4.simple_email_service` | Email service |
| **Email** | `mxgraph.aws4.email` | Email icon |
| **Email 2** | `mxgraph.aws4.email_2` | Email variant |
| **Email Notification** | `mxgraph.aws4.email_notification` | Email alerts |
| **HTTP Notification** | `mxgraph.aws4.http_notification` | HTTP alerts |
| **AWS Pinpoint** | `mxgraph.aws4.pinpoint` | Customer engagement |
| **Pinpoint Journey** | `mxgraph.aws4.pinpoint_journey` | Customer journey |
| **AWS Chime** | `mxgraph.aws4.chime` | Communications service |
| **Chime SDK** | `mxgraph.aws4.chime_sdk` | Communications SDK |
| **AWS Connect** | `mxgraph.aws4.connect` | Contact center |
| **Contact Center** | `mxgraph.aws4.contact_center` | Contact center |
| **End User Messaging** | `mxgraph.aws4.end_user_messaging` | User messaging |
| **AWS Chatbot** | `mxgraph.aws4.chatbot` | ChatOps integration |
| **AWS IQ** | `mxgraph.aws4.iq` | Expert network |
| **AWS Wickr** | `mxgraph.aws4.wickr` | Secure messaging |
| **AWS Ground Station** | `mxgraph.aws4.ground_station` | Satellite communications |
| **Satellite** | `mxgraph.aws4.satellite` | Satellite |
| **AWS HealthLake** | `mxgraph.aws4.healthlake` | Healthcare data lake |
| **AWS HealthImaging** | `mxgraph.aws4.healthimaging` | Medical imaging |
| **AWS HealthScribe** | `mxgraph.aws4.healthscribe` | Clinical documentation |
| **Medical Emergency** | `mxgraph.aws4.medical_emergency` | Emergency services |
| **Police Emergency** | `mxgraph.aws4.police_emergency` | Emergency services |
| **AWS Supply Chain** | `mxgraph.aws4.supply_chain` | Supply chain management |
| **AWS B2B Data Interchange** | `mxgraph.aws4.b2b_data_interchange` | B2B data exchange |
| **AWS Entity Resolution** | `mxgraph.aws4.entity_resolution` | Entity matching |
| **AWS Clean Rooms** | `mxgraph.aws4.clean_rooms` | Secure data collaboration |
| **AWS Data Exchange** | `mxgraph.aws4.data_exchange` | Data marketplace |
| **Data Exchange for APIs** | `mxgraph.aws4.data_exchange_for_apis` | API data exchange |
| **AWS Marketplace** | `mxgraph.aws4.marketplace` | Software marketplace |
| **AWS Support** | `mxgraph.aws4.support` | Support services |
| **AWS Professional Services** | `mxgraph.aws4.professional_services` | Consulting services |
| **AWS Training and Certification** | `mxgraph.aws4.training_certification` | Training programs |
| **Customer Enablement** | `mxgraph.aws4.customer_enablement` | Customer support |
| **Customer Engagement** | `mxgraph.aws4.customer_engagement` | Customer services |
| **AWS Forums** | `mxgraph.aws4.forums` | Community forums |
| **AWS Repost** | `mxgraph.aws4.repost` | Open source projects |
| **Repost Private** | `mxgraph.aws4.repost_private` | Private repos |
| **AWS GameKit** | `mxgraph.aws4.gamekit` | Game development |
| **AWS GameLift** | `mxgraph.aws4.gamelift` | Game server hosting |
| **GameLift 2** | `mxgraph.aws4.gamelift_2` | GameLift variant |
| **GameLift Streams** | `mxgraph.aws4.gamelift_streams` | Game streaming |
| **Game Tech** | `mxgraph.aws4.game_tech` | Gaming technology |
| **Game Tech 2** | `mxgraph.aws4.game_tech2` | Game tech variant |
| **Games** | `mxgraph.aws4.games` | Gaming category |
| **GameSparks** | `mxgraph.aws4.gamesparks` | Game backend (legacy) |
| **AWS RoboMaker** | `mxgraph.aws4.robomaker` | Robotics development |
| **Robotics** | `mxgraph.aws4.robotics` | Robotics category |
| **AWS DeepRacer** | `mxgraph.aws4.deepracer` | Autonomous racing |
| **AWS DeepLens** | `mxgraph.aws4.deeplens` | Deep learning camera |
| **AWS DeepComposer** | `mxgraph.aws4.deepcomposer` | Music generation |
| **AWS DeepRacer** | `mxgraph.aws4.deepracer` | Autonomous racing |
| **AWS Device Farm** | `mxgraph.aws4.device_farm` | Mobile app testing |
| **AWS Honeycode** | `mxgraph.aws4.honeycode` | No-code app builder |
| **AWS Location Service** | `mxgraph.aws4.location_service` | Location services |
| **Location Service Geofence** | `mxgraph.aws4.location_service_geofence` | Geofencing |
| **Location Service Map** | `mxgraph.aws4.location_service_map` | Map rendering |
| **Location Service Place** | `mxgraph.aws4.location_service_place` | Place search |
| **Location Service Routes** | `mxgraph.aws4.location_service_routes` | Route calculation |
| **Location Service Track** | `mxgraph.aws4.location_service_track` | Asset tracking |
| **AWS Omics** | `mxgraph.aws4.omics` | Genomics data processing |
| **Genomics CLI** | `mxgraph.aws4.genomics_cli` | Genomics command line |
| **AWS Mainframe Modernization** | `mxgraph.aws4.mainframe_modernization` | Mainframe migration |
| **Mainframe Modernization Analyzer** | `mxgraph.aws4.mainframe_modernization_analyzer` | Analysis tool |
| **Mainframe Modernization Compiler** | `mxgraph.aws4.mainframe_modernization_compiler` | Code compiler |
| **Mainframe Modernization Converter** | `mxgraph.aws4.mainframe_modernization_converter` | Code converter |
| **Mainframe Modernization Developer** | `mxgraph.aws4.mainframe_modernization_developer` | Development tool |
| **Mainframe Modernization Runtime** | `mxgraph.aws4.mainframe_modernization_runtime` | Runtime environment |
| **AWS Elastic VMware Service** | `mxgraph.aws4.elastic_vmware_service` | VMware on AWS |
| **VMware Cloud on AWS** | `mxgraph.aws4.vmware_cloud_on_aws` | VMware service |
| **AWS Red Hat OpenShift** | `mxgraph.aws4.red_hat_openshift` | OpenShift service |
| **AWS Managed Services** | `mxgraph.aws4.managed_services` | Managed operations |
| **AWS Managed Service for Grafana** | `mxgraph.aws4.managed_service_for_grafana` | Grafana hosting |
| **AWS Managed Service for Prometheus** | `mxgraph.aws4.managed_service_for_prometheus` | Prometheus hosting |
| **AWS Managed Workflows for Apache Airflow** | `mxgraph.aws4.managed_workflows_for_apache_airflow` | Airflow hosting |
| **AWS OpsWorks** | `mxgraph.aws4.opsworks` | Configuration management |
| **OpsWorks Apps** | `mxgraph.aws4.opsworks_apps` | Application management |
| **OpsWorks Permissions** | `mxgraph.aws4.opsworks_permissions` | Access control |
| **AWS License Manager** | `mxgraph.aws4.license_manager` | License management |
| **License Manager Application Discovery** | `mxgraph.aws4.license_manager_application_discovery` | License discovery |
| **License Manager License Blending** | `mxgraph.aws4.license_manager_license_blending` | License optimization |
| **AWS Payment Cryptography** | `mxgraph.aws4.payment_cryptography` | Payment security |
| **AWS Cloud Directory** | `mxgraph.aws4.cloud_directory` | Directory service (legacy) |
| **AWS Cloud Digital Interface** | `mxgraph.aws4.cloud_digital_interface` | Broadcast interface |
| **AWS Cloud Extension ROS** | `mxgraph.aws4.cloud_extension_ros` | ROS extension |
| **AWS Open 3D Engine** | `mxgraph.aws4.open_3d_engine` | 3D game engine |
| **Open 3D Engine 2** | `mxgraph.aws4.open_3d_engine_2` | 3D engine variant |
| **AWS Lumberyard** | `mxgraph.aws4.lumberyard` | Game engine (legacy) |
| **AWS Sumerian** | `mxgraph.aws4.sumerian` | AR/VR platform (legacy) |
| **AR/VR** | `mxgraph.aws4.ar_vr` | AR/VR category |
| **AWS Travel** | `mxgraph.aws4.travel` | Travel services |
| **AWS Blockchain** | `mxgraph.aws4.blockchain` | Blockchain service |
| **Blockchain Resource** | `mxgraph.aws4.blockchain_resource` | Blockchain resource |
| **AWS Managed Blockchain** | `mxgraph.aws4.managed_blockchain` | Managed blockchain |
| **AWS CloudShell** | `mxgraph.aws4.cloudshell` | Browser-based shell |
| **AWS NICE DCV** | `mxgraph.aws4.nice_dcv` | Remote desktop |
| **AWS NICE EnginFrame** | `mxgraph.aws4.nice_enginframe` | HPC portal |
| **AWS SQL Workbench** | `mxgraph.aws4.sql_workbench` | SQL client |
| **AWS Activate** | `mxgraph.aws4.activate` | Startup program |
| **AWS All Products** | `mxgraph.aws4.all_products` | All services |
| **AWS Apps** | `mxgraph.aws4.apps` | Applications |
| **AWS Serverless** | `mxgraph.aws4.serverless` | Serverless category |
| **Serverless Application Repository** | `mxgraph.aws4.serverless_application_repository` | Serverless apps |
| **AWS General** | `mxgraph.aws4.general` | General category |
| **General Access Points** | `mxgraph.aws4.general_access_points` | Access points |
| **Generic** | `mxgraph.aws4.generic` | Generic resource |
| **Resource** | `mxgraph.aws4.resource` | Generic resource |
| **Resources** | `mxgraph.aws4.resources` | Multiple resources |
| **Service** | `mxgraph.aws4.service` | Generic service |
| **Services** | `mxgraph.aws4.servers` | Server resources |
| **Instance** | `mxgraph.aws4.instance` | Generic instance |
| **Instance 2** | `mxgraph.aws4.instance2` | Instance variant |
| **Instances** | `mxgraph.aws4.instances` | Multiple instances |
| **Instances 2** | `mxgraph.aws4.instances_2` | Instances variant |
| **Traditional Server** | `mxgraph.aws4.traditional_server` | On-premises server |
| **Gateway** | `mxgraph.aws4.gateway` | Network gateway |
| **Connector** | `mxgraph.aws4.connector` | Integration connector |
| **Service Management Connector** | `mxgraph.aws4.service_management_connector` | Service connector |
| **Vault** | `mxgraph.aws4.vault` | Secure storage |
| **Folder** | `mxgraph.aws4.folder` | File folder |
| **Folders** | `mxgraph.aws4.folders` | Multiple folders |
| **Document** | `mxgraph.aws4.document` | Document |
| **Documents** | `mxgraph.aws4.documents` | Multiple documents |
| **Documents 2** | `mxgraph.aws4.documents2` | Documents variant |
| **Documents 3** | `mxgraph.aws4.documents3` | Documents variant |
| **Search Documents** | `mxgraph.aws4.search_documents` | Document search |
| **JSON Script** | `mxgraph.aws4.json_script` | JSON file |
| **Object** | `mxgraph.aws4.object` | Storage object |
| **Item** | `mxgraph.aws4.item` | Data item |
| **Items** | `mxgraph.aws4.items` | Multiple items |
| **Table** | `mxgraph.aws4.table` | Data table |
| **Data Table** | `mxgraph.aws4.data_table` | Table data |
| **Data Set** | `mxgraph.aws4.data_set` | Dataset |
| **Data Stream** | `mxgraph.aws4.data_stream` | Streaming data |
| **Transform** | `mxgraph.aws4.transform` | Data transformation |
| **Replication** | `mxgraph.aws4.replication` | Data replication |
| **Replication Time Control** | `mxgraph.aws4.replication_time_control` | RTC replication |
| **Shadow** | `mxgraph.aws4.shadow` | Device shadow |
| **Desired State** | `mxgraph.aws4.desired_state` | Target state |
| **Reported State** | `mxgraph.aws4.reported_state` | Current state |
| **Deployment** | `mxgraph.aws4.deployment` | Application deployment |
| **Deployments** | `mxgraph.aws4.deployments` | Multiple deployments |
| **Work Package** | `mxgraph.aws4.work_package` | Work item |
| **Action** | `mxgraph.aws4.action` | Generic action |
| **Addon** | `mxgraph.aws4.addon` | Service addon |
| **Agent** | `mxgraph.aws4.agent` | Software agent |
| **Agent 2** | `mxgraph.aws4.agent2` | Agent variant |
| **Attribute** | `mxgraph.aws4.attribute` | Data attribute |
| **Attributes** | `mxgraph.aws4.attributes` | Multiple attributes |
| **Finding** | `mxgraph.aws4.finding` | Security finding |
| **Filtering Rule** | `mxgraph.aws4.filtering_rule` | Filter rule |
| **Rule** | `mxgraph.aws4.rule` | Business rule |
| **Rule 2** | `mxgraph.aws4.rule_2` | Rule variant |
| **Rule 3** | `mxgraph.aws4.rule_3` | Rule variant |
| **Checklist** | `mxgraph.aws4.checklist` | Checklist |
| **Checklist Cost** | `mxgraph.aws4.checklist_cost` | Cost checklist |
| **Checklist Fault Tolerant** | `mxgraph.aws4.checklist_fault_tolerant` | Fault tolerance |
| **Checklist Performance** | `mxgraph.aws4.checklist_performance` | Performance checklist |
| **Checklist Security** | `mxgraph.aws4.checklist_security` | Security checklist |
| **Question** | `mxgraph.aws4.question` | Help/question |
| **Q** | `mxgraph.aws4.q` | Question mark |
| **Magnifying Glass** | `mxgraph.aws4.magnifying_glass` | Search icon |
| **Magnifying Glass 2** | `mxgraph.aws4.magnifying_glass_2` | Search variant |
| **Lightbulb** | `mxgraph.aws4.lightbulb` | Idea/insight |
| **Gear** | `mxgraph.aws4.gear` | Settings/configuration |
| **Utility** | `mxgraph.aws4.utility` | Utility service |
| **Illustration Desktop** | `mxgraph.aws4.illustration_desktop` | Desktop illustration |
| **Illustration Devices** | `mxgraph.aws4.illustration_devices` | Devices illustration |
| **Illustration Notification** | `mxgraph.aws4.illustration_notification` | Notification illustration |
| **Illustration Office Building** | `mxgraph.aws4.illustration_office_building` | Office illustration |
| **Illustration Users** | `mxgraph.aws4.illustration_users` | Users illustration |
| **House** | `mxgraph.aws4.house` | Home/residential |
| **Office Building** | `mxgraph.aws4.office_building` | Corporate building |
| **Factory** | `mxgraph.aws4.factory` | Industrial facility |
| **Windfarm** | `mxgraph.aws4.windfarm` | Wind energy |
| **Bank** | `mxgraph.aws4.bank` | Financial institution |
| **Car** | `mxgraph.aws4.car` | Vehicle |
| **Bicycle** | `mxgraph.aws4.bycicle` | Bicycle |
| **Coffee Pot** | `mxgraph.aws4.coffee_pot` | IoT device example |
| **Servo** | `mxgraph.aws4.servo` | Servo motor |
| **Mobile** | `mxgraph.aws4.mobile` | Mobile device |
| **Mobile Client** | `mxgraph.aws4.mobile_client` | Mobile app client |
| **Mobile Hub** | `mxgraph.aws4.mobile_hub` | Mobile backend (legacy) |
| **Client** | `mxgraph.aws4.client` | Client application |
| **Group Account** | `mxgraph.aws4.group_account` | Account container |
| **Group Auto Scaling Group** | `mxgraph.aws4.group_auto_scaling_group` | ASG container |
| **Group Availability Zone** | `mxgraph.aws4.group_availability_zone` | AZ container |
| **Group AWS Cloud** | `mxgraph.aws4.group_aws_cloud` | Cloud container |
| **Group AWS Cloud Alt** | `mxgraph.aws4.group_aws_cloud_alt` | Cloud container variant |
| **Group AWS Step Functions Workflow** | `mxgraph.aws4.group_aws_step_functions_workflow` | Workflow container |
| **Group Corporate Data Center** | `mxgraph.aws4.group_corporate_data_center` | Data center container |
| **Group EC2 Instance Contents** | `mxgraph.aws4.group_ec2_instance_contents` | Instance container |
| **Group Elastic Beanstalk** | `mxgraph.aws4.group_elastic_beanstalk` | Beanstalk container |
| **Group Elastic Load Balancing** | `mxgraph.aws4.group_elastic_load_balancing` | ELB container |
| **Group IoT Greengrass** | `mxgraph.aws4.group_iot_greengrass` | Greengrass container |
| **Group IoT Greengrass Deployment** | `mxgraph.aws4.group_iot_greengrass_deployment` | Deployment container |
| **Group On-Premise** | `mxgraph.aws4.group_on_premise` | On-premises container |
| **Group Region** | `mxgraph.aws4.group_region` | Region container |
| **Group Security Group** | `mxgraph.aws4.group_security_group` | Security group container |
| **Group Spot Fleet** | `mxgraph.aws4.group_spot_fleet` | Spot fleet container |
| **Group Subnet** | `mxgraph.aws4.group_subnet` | Subnet container |
| **Group VPC** | `mxgraph.aws4.group_vpc` | VPC container |
| **Group VPC 2** | `mxgraph.aws4.group_vpc2` | VPC container variant |
| **AWS User Notifications** | `mxgraph.aws4.aws_user_notifications` | User notification service |
| **User Notifications** | `mxgraph.aws4.user_notifications` | Notification service |

## Icon Sizing Standards

Standard AWS icon size in draw.io:
- **Width**: 78 pixels (for AWS service icons)
- **Height**: 78 pixels (for AWS service icons)
- **Width**: 60 pixels (for User icons)
- **Height**: 60 pixels (for User icons)
- **Aspect**: `aspect=fixed` (maintains icon proportions)

Example geometry for AWS service:
```xml
<mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
```

Example geometry for User icon:
```xml
<mxGeometry x="100" y="100" width="60" height="60" as="geometry"/>
```

## Icon Color Codes

AWS icons use specific color codes per service. All AWS service icons must also include `strokeColor=#ffffff` (white stroke).

| Service Category | Fill Color Code | Stroke Color | Example Services |
|-----------------|----------------|--------------|------------------|
| **Lambda/ECS** | `#ED7100` (Orange) | `#ffffff` | Lambda, ECS |
| **Storage** | `#7AA116` (Green) | `#ffffff` | S3 |
| **API Gateway/CloudWatch** | `#E7157B` (Pink/Magenta) | `#ffffff` | API Gateway, CloudWatch |
| **Database** | `#C925D1` (Purple) | `#ffffff` | RDS |
| **AI/ML** | `#01A88D` (Teal) | `#ffffff` | Bedrock |
| **User** | `#232F3D` (Dark) | `none` | User icons |

In the style attribute, use:
```xml
fillColor=#ED7100;strokeColor=#ffffff
```

**Note**: Check `templates/base/AWS_diagram_design_patterns.drawio` (tab "AWS Icon Style") for the complete list of service-specific colors.

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
- [ ] AWS service icons use `shape=mxgraph.aws4.resourceIcon` with `resIcon=mxgraph.aws4.[SERVICE_NAME]`
- [ ] User icons use `shape=mxgraph.aws4.user` directly
- [ ] Shape name uses underscores, not spaces
- [ ] Shape name is lowercase
- [ ] Icon size is 78x78 pixels (for services) or 60x60 (for User)
- [ ] Style includes `aspect=fixed`
- [ ] AWS service icons include `strokeColor=#ffffff` (white stroke)
- [ ] AWS service icons include connection points: `points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]]`
- [ ] Color code matches service (check `AWS_diagram_design_patterns.drawio` tab "AWS Icon Style")
- [ ] Container shapes use `shape=mxgraph.aws4.group` with appropriate `grIcon`

## Example: Correct Icon Usage

### AWS Service Icon (Lambda)

```xml
<!-- AWS Lambda Function -->
<mxCell id="lambda-function" 
        value="My Lambda Function" 
        style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#ED7100;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.lambda;" 
        parent="private-subnet-1" 
        vertex="1">
    <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

**Key elements**:
- `shape=mxgraph.aws4.resourceIcon` - Use resourceIcon shape
- `resIcon=mxgraph.aws4.lambda` - Service name (lowercase)
- `fillColor=#ED7100` - Service-specific color (orange for Lambda)
- `strokeColor=#ffffff` - White stroke (required for AWS service icons)
- `points=[[...]]` - Connection points array (required)
- `aspect=fixed` - Maintains icon proportions
- `width="78" height="78"` - Standard icon size

### User Icon

```xml
<!-- User Icon -->
<mxCell id="user" 
        value="Users" 
        style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#232F3D;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.user;" 
        parent="1" 
        vertex="1">
    <mxGeometry x="100" y="100" width="60" height="60" as="geometry"/>
</mxCell>
```

**Key elements**:
- `shape=mxgraph.aws4.user` - Direct shape (not resourceIcon)
- `fillColor=#232F3D` - Dark color for user icon
- `strokeColor=none` - No stroke for user icon
- `width="60" height="60"` - Smaller size for user icon

## Template Usage

When using templates from this repository:
1. Reference this guide for correct icon shape names (use as `resIcon` values)
2. Copy icon examples from `templates/base/AWS_diagram_design_patterns.drawio` (tab "AWS Icon Style")
3. Use `shape=mxgraph.aws4.resourceIcon` with `resIcon` for AWS services
4. Include all required style attributes: connection points, white stroke, correct fill color
5. Modify only the `value` (label), `id`, `resIcon`, and `fillColor` attributes
6. Keep all other style attributes identical to template

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
1. **Always** use `shape=mxgraph.aws4.resourceIcon` with `resIcon` for AWS services (NOT `shape=mxgraph.aws4.[service]` directly)
2. **Always** use shape names from this reference guide as `resIcon` values (all lowercase)
3. **Never** guess shape names - if unsure, check this guide or the [m-radzikowski repository](https://github.com/m-radzikowski/diagrams-aws-icons)
4. **Always** use lowercase for icon shape names (e.g., `lambda`, not `Lambda`)
5. **Always** include `strokeColor=#ffffff` for AWS service icons
6. **Always** include connection points array in style
7. **Always** use standard icon size (78x78 for services, 60x60 for User)
8. **Always** include `aspect=fixed` in style
9. **Always** verify AWS library is loaded (preferably from m-radzikowski repository)
10. **Always** check `templates/base/AWS_diagram_design_patterns.drawio` (tab "AWS Icon Style") for correct colors and styles
11. If a service isn't listed, check the latest icon library or use a generic container shape as fallback

