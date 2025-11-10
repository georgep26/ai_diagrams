# AI Agent Guide for Generating draw.io Diagrams

This guide provides a comprehensive workflow for AI coding agents (Cursor, GitHub Copilot) to generate professional AWS architecture diagrams using the templates and reference materials in this repository.

## Overview

This repository contains templates and guides to help AI agents generate draw.io diagrams with:
- ✅ Proper AWS icons that display correctly
- ✅ Clean, readable connections
- ✅ Consistent spacing and layout
- ✅ Professional appearance
- ✅ Logical paths textbox explaining application flows
- ✅ Numbered step badges matching logical paths

## Quick Start Workflow

### Step 1: Reference the Template System

Before generating any diagram XML, always:
1. Read `templates/AWS_diagram_design_patterns.drawio`:
   - Tab "AWS Icon Style" for icon styles
   - Tab "AWS Connection Patterns" for connection styles
   - Tab "AWS Groups" for container/group styles and nesting examples
   - Tab "Logical Paths" for logical paths textbox and numbered badge examples
2. Reference `guides/ICON_REFERENCE.md` for icon shape names
3. Reference `guides/CONNECTION_PATTERNS.md` for routing
4. Reference `guides/SPACING_LAYOUT.md` for positioning

### Step 2: Identify Required Components

List all AWS services and components needed:
- Compute: Lambda, ECS, EC2, etc.
- Storage: S3, RDS, DynamoDB, etc.
- Networking: VPC, Subnets, API Gateway, etc.
- AI/ML: Bedrock, Knowledge Bases, etc.
- Monitoring: CloudWatch, X-Ray, etc.

### Step 3: Create Component Outline

**CRITICAL**: Before generating any diagram XML, create a text-only outline of all components, their hierarchy, and connections. This helps ensure proper structure and nesting before implementation.

Create a structured text outline that combines containers, services, and connections in one integrated hierarchy:

**Example**: S3 Event Pattern (from `AWS_diagram_design_patterns.drawio` tab "AWS Groups")

```
Component Outline: S3 Event Processing Architecture

Example AWS Account (AWS Account group)
└── Example VPC (VPC group)
    └── S3 Bucket → ("S3 Event", solid) Lambda Function → ("Logs", dashed) CloudWatch
```

**Format guidelines**:
- Use indentation to show nesting hierarchy
- List containers with their group type in parentheses
- Show services and connections on one line: `Service → ("Label", style) Target Service → ("Label", style) Next Service`
- Use "solid" for data flow connections, "dashed" for monitoring/replication
- Chain multiple connections in sequence on the same line
- Keep the entire structure in one integrated tree

This outline serves as a blueprint before generating XML and helps catch structural issues early.

### Step 4: Look Up Icon Shape Names

**CRITICAL**: Never guess icon shape names. Always use `guides/ICON_REFERENCE.md`.


### Step 5: Copy Template Structure

Copy the base structure from `templates/AWS_diagram_design_patterns.drawio` (tab "AWS Groups"):
- Root mxGraphModel structure
- Container hierarchy (AWS Cloud → Region → VPC → Subnets)
- Group/container examples with proper nesting
- See "AWS Services in Group Examples" section for complete structure examples

### Step 6: Calculate Positions

Use formulas from `guides/SPACING_LAYOUT.md`:
- Icon spacing: 150px between icons
- Subnet padding: 50px from edges
- Row spacing: 150px between rows
- Always align to 10px grid

### Step 7: Add Connections

Copy connection patterns from `templates/AWS_diagram_design_patterns.drawio` (tab "AWS Connection Patterns"):
- Use right-angle routing (never diagonal)
- Label all connections
- Use appropriate styles (solid vs dashed)
- Add waypoints for complex routing
- See "AWS Services in Group Examples" section for connections with nested services

### Step 8: Add Logical Paths Textbox

**CRITICAL**: Add a "Logical Paths" textbox to explain typical application flows. This helps readers understand the architecture logic.

**Positioning**: Place the textbox on the **left side** of the diagram (x=100-200px) so it's one of the first things viewers see.

**Structure**:
1. Create a title cell: "Logical Paths" (fontSize=16, fontStyle=1)
2. Create a content cell with HTML formatting:
   - Use flexbox layout (`display:flex;align-items:flex-start;`)
   - Each path has a title (fontSize=15px, bold)
   - Each step uses a circular badge (24x24px) matching the diagram icon badges
   - Badge colors should match the numbered badges on diagram icons
   - Text wraps below badges (not underneath) using flex layout

**Numbered Badges on Icons**:
- Add circular badges (24x24px) at the upper left of icons involved in logical paths
- Use same colors as textbox badges (e.g., #FF6B6B for path 1, #4A90E2 for path 2)
- Position badges at `x=icon_x-10, y=icon_y-10` (upper left corner)
- If an icon appears in multiple paths, show multiple badges side-by-side

**Reference**: See `templates/AWS_diagram_design_patterns.drawio` tab "Logical Paths" for template example, or `examples/rag-application.drawio` for complete implementation example.

### Step 9: Verify and Test

Check:
- [ ] All icon shape names match ICON_REFERENCE.md
- [ ] All connections use right-angle routing
- [ ] Spacing follows SPACING_LAYOUT.md standards
- [ ] All components are properly nested (parent-child)
- [ ] Icon sizes are 78x78 (standard AWS icon size)
- [ ] Logical paths textbox is positioned on the left side
- [ ] Numbered badges on icons match logical paths textbox
- [ ] Badge colors are consistent between textbox and diagram icons

## Detailed Workflow

### Phase 1: Setup Diagram Structure

#### 1.1 Create Root Elements

```xml
<mxfile host="app.diagrams.net" modified="2025-01-27T00:00:00.000Z" agent="draw.io" version="22.1.16" etag="diagram-id" type="device">
    <diagram id="diagram-name" name="Diagram Title">
        <mxGraphModel dx="1422" dy="794" grid="0" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="3300" pageHeight="2339" background="#ffffff" math="0" shadow="0">
            <root>
                <mxCell id="0" />
                <mxCell id="1" parent="0" />
```

**Notes**:
- Always include these root elements
- Set `grid="0"` to disable grid (default: no grid visible)
- Set `background="#ffffff"` for white background (default)
- Standard page size: 3300x2339

#### 1.2 Add Title

```xml
<mxCell id="title" 
        value="Architecture Title" 
        style="text;html=1;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;whiteSpace=wrap;rounded=0;fontSize=24;fontStyle=1" 
        parent="1" 
        vertex="1">
    <mxGeometry x="1050" y="20" width="600" height="40" as="geometry" />
</mxCell>
```

#### 1.3 Add Container Hierarchy

**ALWAYS** use groups/containers to organize your diagram. Reference `templates/AWS_diagram_design_patterns.drawio` (tab "AWS Groups") for group styles.

Copy container structure from `AWS_diagram_design_patterns.drawio` (tab "AWS Groups"):
1. AWS Cloud container (outermost)
2. Region container (optional, inside AWS Cloud)
3. VPC container (inside Region or AWS Cloud)
4. Availability Zone containers (optional, inside Region)
5. Public subnets (inside VPC)
6. Private subnets (inside VPC)

See the "AWS Services in Group Examples" section for complete structure examples with nested services.

**Important**: 
- Maintain proper parent-child relationships
- All AWS services should be nested inside appropriate groups (VPC, subnet, etc.)
- Use group styles from "AWS Groups" tab for consistency
- See "AWS Services in Group Examples" section for nesting patterns

### Phase 2: Add Groups and Containers

#### 2.1 Choose Appropriate Groups

Before adding services, determine which groups/containers you need. Reference `templates/AWS_diagram_design_patterns.drawio` (tab "AWS Groups") for available group types:

- **AWS Cloud**: Outermost container for all AWS resources
- **Region**: Geographic region container
- **VPC**: Virtual Private Cloud container
- **Availability Zone**: AZ container (nested in Region)
- **Public Subnet**: Public subnet container (nested in VPC)
- **Private Subnet**: Private subnet container (nested in VPC)
- **Security Group**: Security group container
- **Auto Scaling Group**: ASG container
- **Corporate Data Center**: On-premises container

#### 2.2 Copy Group Template

From `AWS_diagram_design_patterns.drawio` (tab "AWS Groups"), copy the appropriate group:

```xml
<!-- VPC Container Example -->
<mxCell id="vpc-container" 
        value="VPC" 
        style="points=[[0,0],[0.25,0],[0.5,0],[0.75,0],[1,0],[1,0.25],[1,0.5],[1,0.75],[1,1],[0.75,1],[0.5,1],[0.25,1],[0,1],[0,0.75],[0,0.5],[0,0.25]];outlineConnect=0;gradientColor=none;html=1;whiteSpace=wrap;fontSize=12;fontStyle=0;container=1;pointerEvents=0;collapsible=0;recursiveResize=0;shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_vpc2;strokeColor=#8C4FFF;fillColor=none;verticalAlign=top;align=left;spacingLeft=30;fontColor=#AAB7B8;dashed=0;" 
        vertex="1" 
        parent="1">
    <mxGeometry x="100" y="100" width="600" height="400" as="geometry" />
</mxCell>
```

**Key elements**:
- `container=1` - Makes this a container (children can be nested inside)
- `shape=mxgraph.aws4.group` - Group shape type
- `grIcon=mxgraph.aws4.group_vpc2` - Group icon (check "AWS Groups" tab for correct icon)
- `parent` - Parent container (usually "1" for top-level, or another group's id)
- Size the group to accommodate all nested services

#### 2.3 Nest Groups Properly

Groups can be nested. Example hierarchy:
- AWS Cloud (parent="1")
  - Region (parent="aws-cloud-id")
    - VPC (parent="region-id")
      - Private Subnet (parent="vpc-id")
        - Lambda (parent="private-subnet-id")

### Phase 3: Add AWS Services

#### 3.1 Look Up Icon Shape Name

**ALWAYS** check `guides/ICON_REFERENCE.md` first.

Example workflow:
1. Need: AWS Lambda
2. Check ICON_REFERENCE.md → `mxgraph.aws4.lambda` (lowercase!)
3. Use in XML: `shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.lambda` (lowercase!)

#### 2.2 Copy Icon Template

From `AWS_diagram_design_patterns.drawio` (tab "AWS Icon Style"), copy an example icon:

```xml
<mxCell id="lambda-example" 
        value="My Lambda Function" 
        style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0],[0,1.256,0],[0.25,1.256,0],[0.5,1.256,0],[0.75,1.256,0],[1,1.256,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#ED7100;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.lambda;" 
        parent="private-subnet-1" 
        vertex="1">
    <mxGeometry x="50" y="100" width="78" height="78" as="geometry" />
</mxCell>
```

#### 2.3 Modify for Your Service

1. Change `id` to unique value
2. Change `value` to your label
3. Change `resIcon` to correct service (from ICON_REFERENCE.md) - keep `shape=mxgraph.aws4.resourceIcon`
4. Change `fillColor` to service-specific color (from ICON_REFERENCE.md)
5. Keep `strokeColor=#ffffff` (white stroke for all AWS service icons)
6. Keep connection points: `points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0],[0,1.256,0],[0.25,1.256,0],[0.5,1.256,0],[0.75,1.256,0],[1,1.256,0]]` (includes 5 extended connection points 20px below icon for bottom connections)
7. Change `parent` to correct container
8. Calculate `x` and `y` positions (from SPACING_LAYOUT.md)
9. Keep `width="78" height="78"` (standard icon size)
10. Keep `aspect=fixed` (required)

**Note**: For User icons, use `shape=mxgraph.aws4.user` directly (not `resourceIcon`) with `fillColor=#232F3D` and `strokeColor=none`.

#### 3.2 Nest Services in Groups

**CRITICAL**: All AWS services must be nested inside appropriate groups. Reference `templates/AWS_diagram_design_patterns.drawio` (tab "AWS Groups", section "AWS Services in Group Examples") for examples.

**Rules for nesting**:
- Services inside VPC should have `parent="vpc-container-id"`
- Services inside subnets should have `parent="subnet-container-id"`
- Services outside VPC (like S3, API Gateway) can have `parent="1"` or be in an AWS Cloud container
- Connections between services in different groups still use `parent="1"` (top-level)

**Example**: Lambda inside Private Subnet
```xml
<!-- Private Subnet Container -->
<mxCell id="private-subnet-1" 
        value="Private subnet" 
        style="...;container=1;shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_security_group;..." 
        parent="vpc-container" 
        vertex="1">
    <mxGeometry x="50" y="50" width="500" height="300" as="geometry" />
</mxCell>

<!-- Lambda inside Private Subnet -->
<mxCell id="lambda-1" 
        value="Lambda Function" 
        style="...;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.lambda;..." 
        parent="private-subnet-1" 
        vertex="1">
    <mxGeometry x="50" y="50" width="78" height="78" as="geometry" />
</mxCell>
```

#### 3.3 Calculate Positions

Use formulas from `guides/SPACING_LAYOUT.md`:

**Horizontal spacing**:
```
next_x = current_x + 78 + 150 = current_x + 228
```

**Vertical spacing**:
```
next_y = current_y + 78 + 150 = current_y + 228
```

**Grid alignment**:
```
grid_x = round(x / 10) * 10
```

### Phase 4: Add Connections

#### 4.1 Identify Connection Flow

Map the data flow:
- User → API Gateway → Lambda
- S3 → Lambda (event trigger)
- Lambda → RDS (database query)

#### 4.2 Copy Connection Pattern

From `AWS_diagram_design_patterns.drawio` (tab "AWS Connection Patterns"), copy appropriate pattern:

```xml
<mxCell id="edge-1" 
        value="Invoke" 
        style="endArrow=classic;html=1;rounded=0;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;" 
        parent="1" 
        source="api-gateway" 
        target="lambda" 
        edge="1">
    <mxGeometry relative="1" as="geometry" />
</mxCell>
```

#### 4.3 Modify Connection

1. Change `id` to unique value
2. Change `value` to descriptive label (action verb)
3. Change `source` to source component id
4. Change `target` to target component id
5. Adjust `exitX/exitY` and `entryX/entryY` based on relative positions
6. For monitoring/replication connections, add `dashed=1;dashPattern=8 8;` to the style
7. Add waypoints if needed (see CONNECTION_PATTERNS.md)

#### 4.4 Determine Exit/Entry Points

Use patterns from `guides/CONNECTION_PATTERNS.md` and `AWS_diagram_design_patterns.drawio`:

- **Left to right (horizontal)**: `exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0`
- **Top to bottom (vertical)**: `exitX=0.5;exitY=1;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0`
- **Bottom to top (vertical, connecting to bottom)**: `exitX=0.5;exitY=0;exitDx=0;exitDy=0;entryX=0.5;entryY=1.256;entryDx=0;entryDy=0` (uses extended connection point 20px below icon to avoid label)
- **Right to left (horizontal)**: `exitX=0;exitY=0.5;exitDx=0;exitDy=0;entryX=1;entryY=0.5;entryDx=0;entryDy=0`

#### 4.5 Add Waypoints for Complex Routing

If components are far apart:

```xml
<mxGeometry relative="1" as="geometry">
    <Array as="points">
        <mxPoint x="400" y="500" />
        <mxPoint x="400" y="600" />
    </Array>
</mxGeometry>
```

Calculate waypoints:
1. Determine midpoint between source and target
2. Create waypoints at turn points
3. Maintain right-angle routing

### Phase 5: Apply Connection Styles

#### 5.1 Solid Line (Default)

For data flow, API calls:
```xml
style="...;dashed=0;"
```

#### 5.2 Dashed Line

For replication, monitoring, container registry (ECR):
```xml
style="...;dashed=1;dashPattern=8 8;"
```

**Note**: ECR (Elastic Container Registry) connections should always use dashed lines to indicate container image retrieval/pull operations, not active data flow.

### Phase 6: Add Logical Paths Textbox

**CRITICAL**: The logical paths textbox explains typical application flows and helps readers understand the architecture logic. It should be positioned on the **left side** of the diagram (x=100-200px) so it's one of the first things viewers see.

#### 6.1 Create Title Cell

```xml
<mxCell id="logical-paths-box" 
        value="Logical Paths" 
        style="text;html=1;strokeColor=#000000;fillColor=none;align=left;verticalAlign=top;whiteSpace=wrap;rounded=0;fontSize=16;fontStyle=1" 
        vertex="1" 
        parent="1">
    <mxGeometry x="123" y="113" width="350" height="30" as="geometry" />
</mxCell>
```

**Key elements**:
- `fontSize=16;fontStyle=1` - Bold, larger title
- Position on left: `x=100-200px` (adjust based on diagram layout)
- `y` should align with diagram start (typically 100-150px)

#### 6.2 Create Content Cell with HTML Formatting

```xml
<mxCell id="logical-paths-content" 
        value="&lt;div style=&quot;padding:10px;&quot;&gt;&lt;b style=&quot;font-size:15px;&quot;&gt;Path Name:&lt;/b&gt;&lt;br&gt;&lt;br&gt;&lt;div style=&quot;margin-bottom:8px;display:flex;align-items:flex-start;&quot;&gt;&lt;span style=&quot;display:inline-block;width:24px;height:24px;line-height:24px;text-align:center;border-radius:50%;background-color:#FF6B6B;color:#FFFFFF;font-weight:bold;margin-right:8px;flex-shrink:0;&quot;&gt;1&lt;/span&gt;&lt;div style=&quot;flex:1;&quot;&gt;Step description text&lt;/div&gt;&lt;/div&gt;&lt;/div&gt;" 
        style="text;html=1;strokeColor=#000000;fillColor=#F5F5F5;align=left;verticalAlign=top;whiteSpace=wrap;rounded=0;fontSize=12;fontStyle=0" 
        vertex="1" 
        parent="1">
    <mxGeometry x="123" y="143" width="350" height="389" as="geometry" />
</mxCell>
```

**HTML Structure**:
- Outer div with `padding:10px`
- Path title: `<b style="font-size:15px;">Path Name:</b>`
- Each step: `<div style="margin-bottom:8px;display:flex;align-items:flex-start;">`
  - Badge: `<span>` with circular style (24x24px, border-radius:50%)
  - Text: `<div style="flex:1;">` - allows text to wrap below badge

**Badge Colors**:
- Path 1: `#FF6B6B` (red)
- Path 2: `#4A90E2` (blue)
- Path 3: Use different color (e.g., `#4CAF50` green)
- Each path should have a distinct color

**Text Wrapping**:
- Use flexbox: `display:flex;align-items:flex-start;`
- Badge: `flex-shrink:0` (doesn't shrink)
- Text: `flex:1` (takes remaining space, wraps below badge)

#### 6.3 Add Numbered Badges to Diagram Icons

For each icon involved in a logical path, add a circular badge at the upper left corner:

```xml
<mxCell id="step-1-badge-red" 
        value="1" 
        style="ellipse;whiteSpace=wrap;html=1;fillColor=#FF6B6B;strokeColor=#FFFFFF;fontColor=#FFFFFF;fontSize=14;fontStyle=1" 
        vertex="1" 
        parent="1">
    <mxGeometry x="icon_x-10" y="icon_y-10" width="24" height="24" as="geometry" />
</mxCell>
```

**Positioning**:
- Calculate badge position: `x = icon_x - 10`, `y = icon_y - 10` (upper left corner)
- Badge size: 24x24px (matches textbox badges)
- Color: Must match the path color in textbox

**Multiple Paths on Same Icon**:
If an icon appears in multiple paths, add multiple badges side-by-side:
- First badge: `x = icon_x - 10`
- Second badge: `x = icon_x + 20` (30px spacing between badges)

**Example**: Icon at x=633, y=277 with badges for path 1 and path 2:
```xml
<!-- Path 1 badge (red) -->
<mxCell id="step-1-badge-red" ...>
    <mxGeometry x="623" y="267" width="24" height="24" as="geometry" />
</mxCell>

<!-- Path 2 badge (blue) -->
<mxCell id="step-1-badge-blue" ...>
    <mxGeometry x="653" y="267" width="24" height="24" as="geometry" />
</mxCell>
```

#### 6.4 Best Practices

1. **Position on Left**: Always place textbox on left side (x=100-200px) for visibility
2. **Color Consistency**: Use same colors for textbox badges and diagram icon badges
3. **Clear Descriptions**: Use concise, action-oriented step descriptions
4. **Multiple Paths**: Support multiple logical paths with different colors
5. **Badge Alignment**: Position badges consistently at upper left of icons
6. **Text Wrapping**: Use flexbox so text wraps below badges, not underneath

**Reference**: See `templates/AWS_diagram_design_patterns.drawio` tab "Logical Paths" for template example, or `examples/rag-application.drawio` for complete implementation example.

## Common Patterns

### Pattern 1: User → API Gateway → Lambda

```xml
<!-- User -->
<mxCell id="user" value="Users" style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#232F3D;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.user;" parent="1" vertex="1">
    <mxGeometry x="100" y="100" width="60" height="60" as="geometry" />
</mxCell>

<!-- API Gateway -->
<mxCell id="api-gateway" value="API Gateway" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0],[0,1.256,0],[0.25,1.256,0],[0.5,1.256,0],[0.75,1.256,0],[1,1.256,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#E7157B;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.api_gateway;" parent="1" vertex="1">
    <mxGeometry x="250" y="100" width="78" height="78" as="geometry" />
</mxCell>

<!-- Lambda -->
<mxCell id="lambda" value="Lambda Function" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0],[0,1.256,0],[0.25,1.256,0],[0.5,1.256,0],[0.75,1.256,0],[1,1.256,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#ED7100;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.lambda;" parent="1" vertex="1">
    <mxGeometry x="450" y="100" width="78" height="78" as="geometry" />
</mxCell>

<!-- Connections -->
<mxCell id="edge-user-api" value="HTTP Request" style="endArrow=classic;html=1;rounded=0;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;" parent="1" source="user" target="api-gateway" edge="1">
    <mxGeometry relative="1" as="geometry" />
</mxCell>

<mxCell id="edge-api-lambda" value="Invoke" style="endArrow=classic;html=1;rounded=0;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;" parent="1" source="api-gateway" target="lambda" edge="1">
    <mxGeometry relative="1" as="geometry" />
</mxCell>
```

### Pattern 2: S3 Event Trigger

```xml
<!-- S3 Bucket -->
<mxCell id="s3" value="S3 Bucket" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0],[0,1.256,0],[0.25,1.256,0],[0.5,1.256,0],[0.75,1.256,0],[1,1.256,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#7AA116;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.s3;" parent="1" vertex="1">
    <mxGeometry x="100" y="300" width="78" height="78" as="geometry" />
</mxCell>

<!-- Lambda -->
<mxCell id="lambda-s3" value="S3 Handler" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0],[0,1.256,0],[0.25,1.256,0],[0.5,1.256,0],[0.75,1.256,0],[1,1.256,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#ED7100;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.lambda;" parent="1" vertex="1">
    <mxGeometry x="300" y="300" width="78" height="78" as="geometry" />
</mxCell>

<!-- Connection -->
<mxCell id="edge-s3-lambda" value="S3 Event" style="endArrow=classic;html=1;rounded=0;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;" parent="1" source="s3" target="lambda-s3" edge="1">
    <mxGeometry relative="1" as="geometry" />
</mxCell>
```

### Pattern 3: Lambda → RDS

```xml
<!-- Lambda -->
<mxCell id="lambda-db" value="Query Handler" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0],[0,1.256,0],[0.25,1.256,0],[0.5,1.256,0],[0.75,1.256,0],[1,1.256,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#ED7100;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.lambda;" parent="private-subnet-1" vertex="1">
    <mxGeometry x="50" y="100" width="78" height="78" as="geometry" />
</mxCell>

<!-- RDS -->
<mxCell id="rds" value="RDS PostgreSQL" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0],[0,1.256,0],[0.25,1.256,0],[0.5,1.256,0],[0.75,1.256,0],[1,1.256,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#C925D1;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.rds;" parent="private-subnet-1" vertex="1">
    <mxGeometry x="50" y="328" width="78" height="78" as="geometry" />
</mxCell>

<!-- Connection -->
<mxCell id="edge-lambda-rds" value="Query" style="endArrow=classic;html=1;rounded=0;exitX=0.5;exitY=1;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0;" parent="1" source="lambda-db" target="rds" edge="1">
    <mxGeometry relative="1" as="geometry" />
</mxCell>
```

## Checklist for AI Agents

Before finalizing diagram XML, verify:

### Icons
- [ ] All icon shape names checked against ICON_REFERENCE.md
- [ ] All AWS service icons use `shape=mxgraph.aws4.resourceIcon` with `resIcon=mxgraph.aws4.[service]`
- [ ] All icons use standard size (78x78 for services, 60x60 for User)
- [ ] All icons have `aspect=fixed` in style
- [ ] All AWS service icons have `strokeColor=#ffffff` (white stroke)
- [ ] All icons have connection points defined: `points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0],[0,1.256,0],[0.25,1.256,0],[0.5,1.256,0],[0.75,1.256,0],[1,1.256,0]]` (includes extended bottom connection points)
- [ ] All icons have correct `fillColor` for service (from ICON_REFERENCE.md)
- [ ] All icons have correct `parent` (proper nesting)

### Connections
- [ ] All connections use right-angle routing (no diagonals)
- [ ] All connections use style: `endArrow=classic;html=1;rounded=0`
- [ ] All connections include `exitDx=0;exitDy=0;entryDx=0;entryDy=0` in style
- [ ] All connections are labeled with action verbs
- [ ] Exit/entry points are correct (nearest to target)
- [ ] Monitoring/replication connections use `dashed=1;dashPattern=8 8`
- [ ] Waypoints added for complex routing
- [ ] Connection styles appropriate (solid vs dashed)

### Spacing
- [ ] All icons spaced 150px apart (horizontal and vertical)
- [ ] All positions aligned to 10px grid
- [ ] Subnet padding is 50px from edges
- [ ] Container sizes accommodate all components

### Structure
- [ ] Proper container hierarchy (AWS Cloud → Region → VPC → Subnets)
- [ ] All groups use styles from `AWS_diagram_design_patterns.drawio` (tab "AWS Groups")
- [ ] All services are nested inside appropriate groups (not floating at top level)
- [ ] Group containers have `container=1` attribute
- [ ] Group containers use correct `grIcon` from "AWS Groups" tab
- [ ] All components have unique IDs
- [ ] All components have correct parent attribute (services in groups, connections at top level)
- [ ] Root elements present (mxfile, diagram, mxGraphModel)

### Logical Paths
- [ ] Logical paths textbox is positioned on left side (x=100-200px)
- [ ] Textbox title uses fontSize=16, fontStyle=1
- [ ] Textbox content uses flexbox layout for proper text wrapping
- [ ] Each path has distinct color (e.g., #FF6B6B for path 1, #4A90E2 for path 2)
- [ ] Circular badges in textbox are 24x24px matching diagram icon badges
- [ ] Numbered badges on icons are positioned at upper left corner (icon_x-10, icon_y-10)
- [ ] Badge colors match between textbox and diagram icons
- [ ] Multiple badges on same icon are positioned side-by-side (30px spacing)
- [ ] Text wraps below badges (not underneath) using flex layout
- [ ] All steps in logical paths are clearly described

## Common Mistakes to Avoid

1. **Guessing Icon Names**: Always check ICON_REFERENCE.md
2. **Wrong Icon Shape**: Use `shape=mxgraph.aws4.resourceIcon` with `resIcon` for AWS services (not `shape=mxgraph.aws4.[service]` directly)
3. **Missing White Stroke**: AWS service icons must have `strokeColor=#ffffff`
4. **Missing Connection Points**: Include the full `points=[[...]]` array for proper connection routing
5. **Wrong Icon Size**: Always use 78x78 for AWS service icons, 60x60 for User icons
6. **Missing aspect=fixed**: Required for icon display
7. **Diagonal Connections**: Always use right-angle routing
8. **Unlabeled Connections**: Always label connections
9. **Missing exitDx/exitDy**: Include `exitDx=0;exitDy=0;entryDx=0;entryDy=0` in connection styles
10. **Inconsistent Spacing**: Use 150px standard spacing
11. **Wrong Parent**: Components must be children of their container
12. **Services Not Nested**: All AWS services should be inside groups (VPC, subnet, etc.)
13. **Missing container=1**: Group containers must have `container=1` attribute
14. **Wrong Group Icon**: Use correct `grIcon` from "AWS Groups" tab
15. **Off-Grid Positions**: Align all positions to 10px grid
16. **Logical Paths on Wrong Side**: Logical paths textbox must be on left side (x=100-200px), not right
17. **Mismatched Badge Colors**: Badge colors in textbox must match badge colors on diagram icons
18. **Text Under Badges**: Text should wrap below badges using flexbox, not underneath badges
19. **Missing Numbered Badges**: All icons involved in logical paths must have numbered badges
20. **Incorrect Badge Position**: Badges should be at upper left corner (icon_x-10, icon_y-10), not centered

## Template Inheritance

### Base Templates

Start with base templates:
- `templates/AWS_diagram_design_patterns.drawio` - **Primary and only reference**:
  - Tab "AWS Icon Style" - Icon styles
  - Tab "AWS Connection Patterns" - Connection styles
  - Tab "AWS Groups" - Group/container styles and nesting examples
  - Tab "Logical Paths" - Logical paths textbox and numbered badge examples

### Template Customization

The template file contains all necessary patterns and styles. For organization-specific customization:
- Reference the template file for base patterns
- Override only organization-specific elements as needed

## Reference Files

Always reference these files when generating diagrams:

1. **AWS_diagram_design_patterns.drawio** - Primary template (all styles and examples)
   - Tab "AWS Icon Style" - Icon styles
   - Tab "AWS Connection Patterns" - Connection styles
   - Tab "AWS Groups" - Group/container styles and nesting examples
   - Tab "Logical Paths" - Logical paths textbox and numbered badge examples
2. **ICON_REFERENCE.md** - Icon shape names (CRITICAL)
3. **CONNECTION_PATTERNS.md** - Connection routing
4. **SPACING_LAYOUT.md** - Position calculations

## Example: Complete Workflow

### Task: Generate RAG Application Diagram

1. **Read templates**:
   - Read `AWS_diagram_design_patterns.drawio`:
     - Tab "AWS Icon Style" for icon styles
     - Tab "AWS Connection Patterns" for connection styles
     - Tab "AWS Groups" for group styles, nesting examples, and complete structure examples
     - Tab "Logical Paths" for logical paths textbox and numbered badge examples

2. **List components**:
   - Users, API Gateway, Lambda (query handler)
   - Bedrock Knowledge Base, Bedrock
   - S3, RDS, OpenSearch

3. **Create component outline**:
   - Create text-only outline showing container hierarchy, services, and connections in one integrated structure
   - Example format:
     ```
     AWS Cloud
     ├── User → ("HTTP Request", solid) API Gateway → ("Invoke", solid) Lambda
     ├── Bedrock
     ├── S3
     └── VPC
         └── Private Subnet
             └── Lambda → ("API Call", solid) Bedrock
     ```

4. **Look up icons**:
   - Check ICON_REFERENCE.md for each service
   - Use `shape=mxgraph.aws4.resourceIcon` with `resIcon=mxgraph.aws4.[service]` (lowercase!)
   - Lambda: `resIcon=mxgraph.aws4.lambda` (lowercase!)
   - Bedrock: `resIcon=mxgraph.aws4.bedrock` (lowercase!)
   - S3: `resIcon=mxgraph.aws4.s3` (lowercase!)
   - etc.
   - **Important**: All icon names are lowercase per [m-radzikowski/diagrams-aws-icons](https://github.com/m-radzikowski/diagrams-aws-icons)

5. **Add groups/containers**:
   - Copy group examples from `AWS_diagram_design_patterns.drawio` tab "AWS Groups"
   - Create hierarchy: AWS Cloud → Region → VPC → Subnets
   - Use correct `grIcon` for each group type
   - Size groups to accommodate nested services

6. **Add services**:
   - Copy icon examples from `AWS_diagram_design_patterns.drawio` tab "AWS Icon Style"
   - Use `shape=mxgraph.aws4.resourceIcon` with `resIcon` for each service
   - Include connection points and white stroke
   - **Nest services inside appropriate groups** (see "AWS Services in Group Examples")
   - Set `parent` to group container id (not "1")
   - Modify for each service
   - Calculate positions using spacing formulas

7. **Add connections**:
   - Copy connection patterns from `AWS_diagram_design_patterns.drawio` tab "AWS Connection Patterns"
   - Use `endArrow=classic;html=1;rounded=0` with exit/entry points
   - Modify for each flow
   - Add waypoints for complex routing

8. **Add logical paths textbox**:
   - Position on left side (x=100-200px) so it's visible first
   - Create title cell: "Logical Paths" (fontSize=16, fontStyle=1)
   - Create content cell with HTML using flexbox layout
   - Use circular badges (24x24px) matching diagram icon badges
   - Add numbered badges to diagram icons (upper left corner)
   - Use consistent colors for each path (e.g., #FF6B6B for path 1, #4A90E2 for path 2)
   - See `templates/AWS_diagram_design_patterns.drawio` tab "Logical Paths" for template example
   - See `examples/rag-application.drawio` for complete implementation example

9. **Verify**:
   - Check all icons against ICON_REFERENCE.md
   - Check all connections use right-angle routing
   - Check spacing follows standards
   - Check logical paths textbox is on left side
   - Check numbered badges match logical paths

## Summary

1. **Always reference templates and guides** - Don't guess
2. **Use resourceIcon shape** - Use `shape=mxgraph.aws4.resourceIcon` with `resIcon` for AWS services
3. **Check icon names** - Use ICON_REFERENCE.md for `resIcon` values
4. **Include white stroke** - All AWS service icons need `strokeColor=#ffffff`
5. **Use template structure** - Copy from base templates
6. **Calculate positions** - Use spacing formulas
7. **Right-angle routing** - Never use diagonal connections
8. **Label connections** - Use action verbs
9. **Add logical paths textbox** - Position on left side, explain application flows with numbered badges
10. **Add numbered badges to icons** - Match textbox badges, position at upper left corner
11. **Verify everything** - Use checklist before finalizing

## Questions?

If unsure about:
- Icon shape name → Check `guides/ICON_REFERENCE.md`
- Icon style → Check `templates/AWS_diagram_design_patterns.drawio` tab "AWS Icon Style"
- Group/container styles → Check `templates/AWS_diagram_design_patterns.drawio` tab "AWS Groups"
- Service nesting → Check `templates/AWS_diagram_design_patterns.drawio` tab "AWS Groups", section "AWS Services in Group Examples"
- Connection routing → Check `guides/CONNECTION_PATTERNS.md`
- Connection style → Check `templates/AWS_diagram_design_patterns.drawio` tab "AWS Connection Patterns"
- Position calculation → Check `guides/SPACING_LAYOUT.md`
- Structure examples → Check `templates/AWS_diagram_design_patterns.drawio` tab "AWS Groups", section "AWS Services in Group Examples"
- Logical paths textbox → Check `templates/AWS_diagram_design_patterns.drawio` tab "Logical Paths" for template example, or `examples/rag-application.drawio` for complete implementation
- Numbered badges → Check Phase 6 in this guide, `templates/AWS_diagram_design_patterns.drawio` tab "Logical Paths", or `examples/rag-application.drawio`

