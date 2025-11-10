# ai_diagrams
Repository for generating code diagrams via AI coding agents.

## Template System for AI Agents

This repository provides a comprehensive template system to help AI coding agents (Cursor, GitHub Copilot) generate professional AWS architecture diagrams in draw.io format.

### Quick Start for AI Agents

1. **Read the AI Agent Guide**: Start with [`guides/AI_AGENT_GUIDE.md`](guides/AI_AGENT_GUIDE.md) for the complete workflow
2. **Reference Templates**: Use the template file [`templates/AWS_diagram_design_patterns.drawio`](templates/AWS_diagram_design_patterns.drawio) as the primary reference
3. **Check Icon Names**: Always verify icon shape names in [`guides/ICON_REFERENCE.md`](guides/ICON_REFERENCE.md)
4. **Follow Patterns**: Use connection patterns from the "AWS Connection Patterns" tab in the template file
5. **Calculate Spacing**: Use formulas from [`guides/SPACING_LAYOUT.md`](guides/SPACING_LAYOUT.md)

### Repository Structure

```
ai_diagrams/
├── templates/              # Draw.io template files
│   └── AWS_diagram_design_patterns.drawio  # Primary template with multiple tabs
├── guides/                # Reference guides
│   ├── AI_AGENT_GUIDE.md        # Complete workflow for AI agents
│   ├── ICON_REFERENCE.md        # AWS icon shape names
│   ├── CONNECTION_PATTERNS.md    # Connection routing guide
│   └── SPACING_LAYOUT.md        # Layout and spacing standards
├── examples/              # Example diagrams
│   └── rag-application.drawio  # RAG application example
├── .cursor/               # Cursor IDE custom commands
│   └── commands/
│       └── diagram.md     # Custom /diagram command for Cursor
├── .github/               # GitHub Copilot custom prompts
│   ├── copilot-instructions.md  # Repository-wide Copilot instructions
│   └── prompts/
│       └── diagram.prompt.md    # Custom /diagram prompt for Copilot
└── README.md             # This file
```

### Key Features

- ✅ **Proper AWS Icons**: Correct icon shape names that display correctly
- ✅ **Clean Connections**: Right-angle routing with proper labeling
- ✅ **Consistent Spacing**: Grid-based layout with standard spacing
- ✅ **Extensive Comments**: XML comments explain every component
- ✅ **Template System**: Base templates + organization-specific customization
- ✅ **Clean Appearance**: White background with no visible grid (default settings)

### Guides

| Guide | Purpose |
|-------|---------|
| [AI Agent Guide](guides/AI_AGENT_GUIDE.md) | Complete workflow for generating diagrams |
| [Icon Reference](guides/ICON_REFERENCE.md) | AWS icon shape names and loading instructions |
| [Connection Patterns](guides/CONNECTION_PATTERNS.md) | Connection routing algorithms and best practices |
| [Spacing & Layout](guides/SPACING_LAYOUT.md) | Layout standards and spacing calculations |

### Templates

| Template | Purpose |
|----------|---------|
| [AWS Diagram Design Patterns](templates/AWS_diagram_design_patterns.drawio) | Primary template with multiple tabs: AWS Icon Style, Connection Patterns, Groups, and Logical Paths |

### Priority Fixes

The template system addresses the most common issues:

1. **Icons Not Showing** (Highest Priority)
   - Solution: Use correct shape names from `ICON_REFERENCE.md`
   - Ensure AWS library is loaded: `libs=aws4` parameter

2. **Messy Connections** (Second Priority)
   - Solution: Use right-angle routing from `CONNECTION_PATTERNS.md`
   - Add waypoints for complex routing

3. **Poor Spacing** (Third Priority)
   - Solution: Use spacing formulas from `SPACING_LAYOUT.md`
   - Align to 10px grid

### Custom AI Agent Commands

This repository includes custom commands for both **Cursor** and **GitHub Copilot** to streamline diagram generation.

#### Setup

The custom commands are already configured in this repository:
- **Cursor**: `.cursor/commands/diagram.md`
- **GitHub Copilot**: `.github/prompts/diagram.prompt.md` and `.github/copilot-instructions.md`

No additional setup is required - the commands are ready to use!

#### Using the `/diagram` Command

**In Cursor:**
1. Open Cursor's chat interface
2. Type `/` to see available commands
3. Select `/diagram` from the list
4. The AI agent will automatically follow the workflow in `guides/AI_AGENT_GUIDE.md`

**In GitHub Copilot:**
1. Open Copilot Chat in your IDE
2. Type `/diagram` in the chat
3. Copilot will use the custom prompt that references `guides/AI_AGENT_GUIDE.md`
4. The agent will follow all guidelines and standards automatically

**What the Command Does:**
- References the complete workflow in `guides/AI_AGENT_GUIDE.md`
- Ensures proper icon names from `guides/ICON_REFERENCE.md`
- Follows spacing and layout standards from `guides/SPACING_LAYOUT.md`
- Uses connection patterns from the template file
- Includes logical paths textbox and numbered badges
- Verifies against all checklists in the guide

### For AI Agents

**Workflow**:
1. Read `guides/AI_AGENT_GUIDE.md` for complete instructions
2. Reference the template file `templates/AWS_diagram_design_patterns.drawio` (all tabs)
3. Look up icon names in `guides/ICON_REFERENCE.md`
4. Copy connection patterns from the "AWS Connection Patterns" tab in the template
5. Calculate positions using `guides/SPACING_LAYOUT.md` formulas
6. Verify using checklist in AI Agent Guide

**Critical Rules**:
- ❌ Never guess icon shape names - always check `ICON_REFERENCE.md`
- ❌ Never use uppercase icon names - all icon names are lowercase (e.g., `lambda`, not `Lambda`)
- ❌ Never use diagonal connections - always use right-angle routing
- ❌ Never use custom icon sizes - always use 78x78 for AWS icons
- ✅ Always include `aspect=fixed` in icon styles
- ✅ Always label connections with action verbs
- ✅ Always align positions to 10px grid
- ✅ Always use icons from [m-radzikowski/diagrams-aws-icons](https://github.com/m-radzikowski/diagrams-aws-icons) for latest lowercase names
- ✅ Always set `grid="0"` to disable visible grid (default)
- ✅ Always set `background="#ffffff"` for white background (default)

### For Human Users

1. **Load AWS Icons in draw.io** (Recommended):
   - **Best Option**: Load from [m-radzikowski/diagrams-aws-icons](https://github.com/m-radzikowski/diagrams-aws-icons):
     - File → Open Library from → URL
     - Enter: `https://raw.githubusercontent.com/m-radzikowski/diagrams-aws-icons/master/20240206/AWS%20Architecture%20Icons%2020240206.xml`
     - Check repository for latest version
   - **Alternative**: Open draw.io with built-in library:
     - Visit [https://app.diagrams.net/?splash=0&libs=aws4](https://app.diagrams.net/?splash=0&libs=aws4)
     - Note: Built-in library may use uppercase names; m-radzikowski library uses lowercase

2. **Open templates in draw.io**:
   - File → Open from → Device → Select template file

3. **Customize as needed**:
   - Modify components, labels, and positions
   - Maintain structure and styling from the template
   - Read XML comments for guidance

### Contributing

To contribute templates or guides:
1. Follow commenting standards (extensive XML comments)
2. Test thoroughly in draw.io
3. Verify icons display correctly
4. Update appropriate README files

## RAG Application Architecture Diagram

This repository contains a comprehensive architecture diagram for a Retrieval-Augmented Generation (RAG) application deployed on AWS.

### File: `examples/rag-application.drawio`

A detailed draw.io architecture diagram showcasing a RAG application on AWS with the following components:

#### Architecture Components

**Networking Layer:**
- Virtual Private Cloud (VPC) with public and private subnets across multiple Availability Zones
- Internet Gateway for public internet access
- NAT Gateways for private subnet outbound access
- VPC Endpoints for private access to AWS services

**Compute Services:**
- **AWS Lambda Functions:**
  - S3 Event Handler Lambda
  - Document Processor Lambda
  - Query Handler Lambda
  - Knowledge Base Sync Lambda
- **Amazon ECS (Fargate):** Containerized processing services
- **Amazon ECR:** Container image registry

**Data Storage:**
- **Amazon S3:** Raw and processed document storage
- **Amazon RDS (PostgreSQL with pgvector):** Structured metadata and vector embeddings storage
- **Amazon OpenSearch Serverless:** Vector store for semantic search

**AI/ML Services:**
- **Amazon Bedrock Knowledge Bases:** Automated RAG workflow management
- **Amazon Bedrock:** Foundation models for generation

**API & Access:**
- **API Gateway:** REST API for user queries
- **Amazon Cognito:** User authentication (optional)

**Monitoring & Security:**
- **Amazon CloudWatch:** Logs and metrics
- **AWS Secrets Manager:** Secure credential storage

### How to Use

1. **Open in draw.io:**
   - Visit [https://app.diagrams.net/?splash=0&libs=aws4](https://app.diagrams.net/?splash=0&libs=aws4) (ensures AWS icons are loaded)
   - Or open draw.io and enable the AWS library: More Shapes → Cloud → AWS

2. **Open the file:**
   - File → Open from → Device
   - Select `examples/rag-application.drawio`

3. **Edit and customize:**
   - All components are editable
   - Add or remove services as needed
   - Adjust connections and labels

4. **Export:**
   - File → Export as → PNG/PDF/SVG for documentation
   - Keep the `.drawio` format for future edits

### Architecture Flow

1. **Document Ingestion:**
   - Documents uploaded to S3 → Lambda triggered → ECS processes → Stored in S3 → Knowledge Base syncs

2. **Query Processing:**
   - User query → API Gateway → Query Handler Lambda → Bedrock Knowledge Base retrieves context → Bedrock generates response

3. **Data Flow:**
   - All services communicate through VPC with proper security groups and network ACLs
   - Private subnets for compute and database resources
   - Public subnets for NAT Gateways and Internet Gateway

### Notes

- The diagram uses AWS Architecture Icons (aws4 library)
- All components are properly labeled and connected
- VPC structure shows high availability with multiple AZs
- Security best practices are reflected in the network design
