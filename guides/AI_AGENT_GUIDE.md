# AI Agent Guide for Generating draw.io Diagrams

This guide provides a comprehensive workflow for AI coding agents (Cursor, GitHub Copilot) to generate professional AWS architecture diagrams using the templates and reference materials in this repository.

## Overview

This repository contains templates and guides to help AI agents generate draw.io diagrams with:
- ✅ Proper AWS icons that display correctly
- ✅ Clean, readable connections
- ✅ Consistent spacing and layout
- ✅ Professional appearance

## Quick Start Workflow

### Step 1: Reference the Template System

Before generating any diagram XML, always:
1. Read `templates/base/aws-vpc-template.drawio` for structure
2. Read `templates/base/aws-connection-patterns.drawio` for connections
3. Reference `guides/ICON_REFERENCE.md` for icon shape names
4. Reference `guides/CONNECTION_PATTERNS.md` for routing
5. Reference `guides/SPACING_LAYOUT.md` for positioning

### Step 2: Identify Required Components

List all AWS services and components needed:
- Compute: Lambda, ECS, EC2, etc.
- Storage: S3, RDS, DynamoDB, etc.
- Networking: VPC, Subnets, API Gateway, etc.
- AI/ML: Bedrock, Knowledge Bases, etc.
- Monitoring: CloudWatch, X-Ray, etc.

### Step 3: Look Up Icon Shape Names

**CRITICAL**: Never guess icon shape names. Always use `guides/ICON_REFERENCE.md`.

Example:
- ❌ Wrong: `shape=mxgraph.aws4.lambda` (wrong case)
- ❌ Wrong: `shape=mxgraph.aws4.AWS_Lambda` (wrong name)
- ✅ Correct: `shape=mxgraph.aws4.Lambda` (from reference)

### Step 4: Copy Template Structure

Copy the base structure from `templates/base/aws-vpc-template.drawio`:
- Root mxGraphModel structure
- Container hierarchy (Internet → VPC → Subnets)
- Example component placements

### Step 5: Calculate Positions

Use formulas from `guides/SPACING_LAYOUT.md`:
- Icon spacing: 150px between icons
- Subnet padding: 50px from edges
- Row spacing: 150px between rows
- Always align to 10px grid

### Step 6: Add Connections

Copy connection patterns from `templates/base/aws-connection-patterns.drawio`:
- Use right-angle routing (never diagonal)
- Label all connections
- Use appropriate styles (solid vs dashed)
- Add waypoints for complex routing

### Step 7: Verify and Test

Check:
- [ ] All icon shape names match ICON_REFERENCE.md
- [ ] All connections use right-angle routing
- [ ] Spacing follows SPACING_LAYOUT.md standards
- [ ] All components are properly nested (parent-child)
- [ ] Icon sizes are 78x78 (standard AWS icon size)

## Detailed Workflow

### Phase 1: Setup Diagram Structure

#### 1.1 Create Root Elements

```xml
<mxfile host="app.diagrams.net" modified="2025-01-27T00:00:00.000Z" agent="draw.io" version="22.1.16" etag="diagram-id" type="device">
    <diagram id="diagram-name" name="Diagram Title">
        <mxGraphModel dx="1422" dy="794" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="3300" pageHeight="2339" background="#ffffff" math="0" shadow="0">
            <root>
                <mxCell id="0" />
                <mxCell id="1" parent="0" />
```

**Notes**:
- Always include these root elements
- Set `grid="1"` and `gridSize="10"` for alignment
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

Copy container structure from `aws-vpc-template.drawio`:
1. Internet/AWS Cloud container
2. VPC container (inside Internet)
3. Public subnets (inside VPC)
4. Private subnets (inside VPC)

**Important**: Maintain proper parent-child relationships.

### Phase 2: Add AWS Services

#### 2.1 Look Up Icon Shape Name

**ALWAYS** check `guides/ICON_REFERENCE.md` first.

Example workflow:
1. Need: AWS Lambda
2. Check ICON_REFERENCE.md → `mxgraph.aws4.Lambda`
3. Use in XML: `shape=mxgraph.aws4.Lambda`

#### 2.2 Copy Icon Template

From `aws-vpc-template.drawio`, copy an example icon:

```xml
<mxCell id="lambda-example" 
        value="My Lambda Function" 
        style="sketch=0;points=[];outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#759C3E;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.Lambda;" 
        parent="private-subnet-1" 
        vertex="1">
    <mxGeometry x="50" y="100" width="78" height="78" as="geometry" />
</mxCell>
```

#### 2.3 Modify for Your Service

1. Change `id` to unique value
2. Change `value` to your label
3. Change `shape` to correct service (from ICON_REFERENCE.md)
4. Change `fillColor` to service category color (from ICON_REFERENCE.md)
5. Change `parent` to correct container
6. Calculate `x` and `y` positions (from SPACING_LAYOUT.md)
7. Keep `width="78" height="78"` (standard icon size)
8. Keep `aspect=fixed` (required)

#### 2.4 Calculate Positions

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

### Phase 3: Add Connections

#### 3.1 Identify Connection Flow

Map the data flow:
- User → API Gateway → Lambda
- S3 → Lambda (event trigger)
- Lambda → RDS (database query)

#### 3.2 Copy Connection Pattern

From `aws-connection-patterns.drawio`, copy appropriate pattern:

```xml
<mxCell id="edge-1" 
        value="Invoke" 
        style="endArrow=classic;html=1;rounded=0;exitX=0.5;exitY=1;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0;" 
        parent="1" 
        source="api-gateway" 
        target="lambda" 
        edge="1">
    <mxGeometry relative="1" as="geometry" />
</mxCell>
```

#### 3.3 Modify Connection

1. Change `id` to unique value
2. Change `value` to descriptive label (action verb)
3. Change `source` to source component id
4. Change `target` to target component id
5. Adjust `exitX/exitY` and `entryX/entryY` based on relative positions
6. Add waypoints if needed (see CONNECTION_PATTERNS.md)

#### 3.4 Determine Exit/Entry Points

Use patterns from `guides/CONNECTION_PATTERNS.md`:

- **Top to bottom**: `exitX=0.5;exitY=1;entryX=0.5;entryY=0`
- **Left to right**: `exitX=1;exitY=0.5;entryX=0;entryY=0.5`
- **Right to left**: `exitX=0;exitY=0.5;entryX=1;entryY=0.5`

#### 3.5 Add Waypoints for Complex Routing

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

### Phase 4: Apply Connection Styles

#### 4.1 Solid Line (Default)

For data flow, API calls:
```xml
style="...;dashed=0;"
```

#### 4.2 Dashed Line

For replication, monitoring:
```xml
style="...;dashed=1;dashPattern=8 8;"
```

## Common Patterns

### Pattern 1: User → API Gateway → Lambda

```xml
<!-- User -->
<mxCell id="user" value="Users" style="...;shape=mxgraph.aws4.user;" parent="1" vertex="1">
    <mxGeometry x="100" y="100" width="60" height="60" as="geometry" />
</mxCell>

<!-- API Gateway -->
<mxCell id="api-gateway" value="API Gateway" style="...;shape=mxgraph.aws4.API_Gateway;" parent="1" vertex="1">
    <mxGeometry x="250" y="100" width="78" height="78" as="geometry" />
</mxCell>

<!-- Lambda -->
<mxCell id="lambda" value="Lambda Function" style="...;shape=mxgraph.aws4.Lambda;" parent="1" vertex="1">
    <mxGeometry x="450" y="100" width="78" height="78" as="geometry" />
</mxCell>

<!-- Connections -->
<mxCell id="edge-user-api" value="HTTP Request" style="...;exitX=0.5;exitY=1;entryX=0.5;entryY=0;" parent="1" source="user" target="api-gateway" edge="1">
    <mxGeometry relative="1" as="geometry" />
</mxCell>

<mxCell id="edge-api-lambda" value="Invoke" style="...;exitX=0.5;exitY=1;entryX=0.5;entryY=0;" parent="1" source="api-gateway" target="lambda" edge="1">
    <mxGeometry relative="1" as="geometry" />
</mxCell>
```

### Pattern 2: S3 Event Trigger

```xml
<!-- S3 Bucket -->
<mxCell id="s3" value="S3 Bucket" style="...;shape=mxgraph.aws4.S3;" parent="1" vertex="1">
    <mxGeometry x="100" y="300" width="78" height="78" as="geometry" />
</mxCell>

<!-- Lambda -->
<mxCell id="lambda-s3" value="S3 Handler" style="...;shape=mxgraph.aws4.Lambda;" parent="1" vertex="1">
    <mxGeometry x="300" y="300" width="78" height="78" as="geometry" />
</mxCell>

<!-- Connection -->
<mxCell id="edge-s3-lambda" value="S3 Event" style="...;exitX=1;exitY=0.5;entryX=0;entryY=0.5;" parent="1" source="s3" target="lambda-s3" edge="1">
    <mxGeometry relative="1" as="geometry" />
</mxCell>
```

### Pattern 3: Lambda → RDS

```xml
<!-- Lambda -->
<mxCell id="lambda-db" value="Query Handler" style="...;shape=mxgraph.aws4.Lambda;" parent="private-subnet-1" vertex="1">
    <mxGeometry x="50" y="100" width="78" height="78" as="geometry" />
</mxCell>

<!-- RDS -->
<mxCell id="rds" value="RDS PostgreSQL" style="...;shape=mxgraph.aws4.RDS;" parent="private-subnet-1" vertex="1">
    <mxGeometry x="50" y="328" width="78" height="78" as="geometry" />
</mxCell>

<!-- Connection -->
<mxCell id="edge-lambda-rds" value="Query" style="...;exitX=0.5;exitY=1;entryX=0.5;entryY=0;" parent="1" source="lambda-db" target="rds" edge="1">
    <mxGeometry relative="1" as="geometry" />
</mxCell>
```

## Checklist for AI Agents

Before finalizing diagram XML, verify:

### Icons
- [ ] All icon shape names checked against ICON_REFERENCE.md
- [ ] All icons use standard size (78x78)
- [ ] All icons have `aspect=fixed` in style
- [ ] All icons have correct `fillColor` for service category
- [ ] All icons have correct `parent` (proper nesting)

### Connections
- [ ] All connections use right-angle routing (no diagonals)
- [ ] All connections are labeled with action verbs
- [ ] Exit/entry points are correct (nearest to target)
- [ ] Waypoints added for complex routing
- [ ] Connection styles appropriate (solid vs dashed)

### Spacing
- [ ] All icons spaced 150px apart (horizontal and vertical)
- [ ] All positions aligned to 10px grid
- [ ] Subnet padding is 50px from edges
- [ ] Container sizes accommodate all components

### Structure
- [ ] Proper container hierarchy (Internet → VPC → Subnets)
- [ ] All components have unique IDs
- [ ] All components have correct parent attribute
- [ ] Root elements present (mxfile, diagram, mxGraphModel)

## Common Mistakes to Avoid

1. **Guessing Icon Names**: Always check ICON_REFERENCE.md
2. **Wrong Icon Size**: Always use 78x78 for AWS icons
3. **Missing aspect=fixed**: Required for icon display
4. **Diagonal Connections**: Always use right-angle routing
5. **Unlabeled Connections**: Always label connections
6. **Inconsistent Spacing**: Use 150px standard spacing
7. **Wrong Parent**: Components must be children of their container
8. **Off-Grid Positions**: Align all positions to 10px grid

## Template Inheritance

### Base Templates

Start with base templates:
- `templates/base/aws-vpc-template.drawio` - Structure
- `templates/base/aws-connection-patterns.drawio` - Connections

### Organization Templates

If organization-specific templates exist:
- Check `templates/organizations/[org-name]/` directory
- Inherit styles from base templates
- Override only organization-specific elements

## Reference Files

Always reference these files when generating diagrams:

1. **ICON_REFERENCE.md** - Icon shape names (CRITICAL)
2. **CONNECTION_PATTERNS.md** - Connection routing
3. **SPACING_LAYOUT.md** - Position calculations
4. **aws-vpc-template.drawio** - Structure examples
5. **aws-connection-patterns.drawio** - Connection examples

## Example: Complete Workflow

### Task: Generate RAG Application Diagram

1. **Read templates**:
   - Read `aws-vpc-template.drawio` for structure
   - Read `aws-connection-patterns.drawio` for connections

2. **List components**:
   - Users, API Gateway, Lambda (query handler)
   - Bedrock Knowledge Base, Bedrock
   - S3, RDS, OpenSearch

3. **Look up icons**:
   - Check ICON_REFERENCE.md for each service
   - Lambda: `mxgraph.aws4.Lambda`
   - Bedrock: `mxgraph.aws4.Bedrock`
   - S3: `mxgraph.aws4.S3`
   - etc.

4. **Copy structure**:
   - Copy VPC container structure from template
   - Copy subnet containers
   - Modify as needed

5. **Add services**:
   - Copy icon examples from template
   - Modify for each service
   - Calculate positions using spacing formulas

6. **Add connections**:
   - Copy connection patterns
   - Modify for each flow
   - Add waypoints for complex routing

7. **Verify**:
   - Check all icons against ICON_REFERENCE.md
   - Check all connections use right-angle routing
   - Check spacing follows standards

## Summary

1. **Always reference templates and guides** - Don't guess
2. **Check icon names** - Use ICON_REFERENCE.md
3. **Use template structure** - Copy from base templates
4. **Calculate positions** - Use spacing formulas
5. **Right-angle routing** - Never use diagonal connections
6. **Label connections** - Use action verbs
7. **Verify everything** - Use checklist before finalizing

## Questions?

If unsure about:
- Icon shape name → Check `guides/ICON_REFERENCE.md`
- Connection routing → Check `guides/CONNECTION_PATTERNS.md`
- Position calculation → Check `guides/SPACING_LAYOUT.md`
- Structure examples → Check `templates/base/aws-vpc-template.drawio`
- Connection examples → Check `templates/base/aws-connection-patterns.drawio`

