# Connection Patterns Guide

This guide explains how to create clean, readable connections between AWS service components in draw.io diagrams.

## Overview

Connections in draw.io represent data flow, API calls, triggers, and relationships between AWS services. Proper connection routing ensures diagrams are readable and professional.

## Connection Basics

### Connection Structure

A connection in draw.io XML is an `mxCell` with `edge="1"`:

**Important**: When connecting services that are nested inside groups (VPC, subnets, etc.), the connection itself should still have `parent="1"` (top-level), even though the source and target services have different parents. This allows connections to cross group boundaries properly.

```xml
<mxCell id="edge-1" 
        value="Connection Label" 
        style="endArrow=classic;html=1;rounded=0;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;" 
        parent="1" 
        source="source-id" 
        target="target-id" 
        edge="1">
    <mxGeometry relative="1" as="geometry" />
</mxCell>
```

### Key Attributes

- **id**: Unique identifier for the connection
- **value**: Label text displayed on the connection
- **source**: ID of the source component
- **target**: ID of the target component
- **edge="1"**: Indicates this is a connection (not a shape)
- **parent**: Parent container (usually "1" for top-level)

## Exit and Entry Points

Connections exit from the source component and enter the target component. The exit/entry points are specified as fractions (0.0 to 1.0) of the component's dimensions.

### Exit/Entry Point Values

| Value | Position |
|-------|----------|
| 0.0 | Left edge (horizontal) or Top edge (vertical) |
| 0.5 | Center |
| 1.0 | Right edge (horizontal) or Bottom edge (vertical) |
| 1.256 | Extended bottom connection point (20px below icon, for bottom connections) |

**Important**: All AWS service icons include 5 extended connection points below the icon (at y=1.256) to prevent connections from overlapping the label. These points are located at:
- `[0, 1.256, 0]` - bottom left corner
- `[0.25, 1.256, 0]` - between left and center
- `[0.5, 1.256, 0]` - bottom center (most common)
- `[0.75, 1.256, 0]` - between center and right
- `[1, 1.256, 0]` - bottom right corner

When connecting to the bottom of an icon, use `entryY=1.256` (or the appropriate x value: 0, 0.25, 0.5, 0.75, or 1) instead of `entryY=1` to connect below the label.

### Common Exit/Entry Patterns

#### Left to Right (Horizontal)
```xml
exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0
```
- Source: Exit from right side center
- Target: Enter at left side center
- Use case: Lambda → RDS, Lambda → S3, User → API Gateway → Lambda

#### Top to Bottom (Vertical)
```xml
exitX=0.5;exitY=1;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0
```
- Source: Exit from bottom center
- Target: Enter at top center
- Use case: Lambda → RDS (vertical layout)

#### Right to Left (Horizontal)
```xml
exitX=0;exitY=0.5;exitDx=0;exitDy=0;entryX=1;entryY=0.5;entryDx=0;entryDy=0
```
- Source: Exit from left side center
- Target: Enter at right side center
- Use case: S3 → Lambda (event-driven, reverse flow)

#### Bottom to Top (Vertical)
```xml
exitX=0.5;exitY=0;exitDx=0;exitDy=0;entryX=0.5;entryY=1.256;entryDx=0;entryDy=0
```
- Source: Exit from top center
- Target: Enter at extended bottom connection point (20px below icon, y=1.256)
- Use case: Connecting to bottom of icon (e.g., ECR → ECS container pull)
- **Note**: All AWS icons include 5 extended connection points below the icon (at y=1.256) to avoid overlapping the label. Use `entryY=1.256` with the appropriate `entryX` value (0, 0.25, 0.5, 0.75, or 1) when connecting to the bottom.

## Connection Styles

### Solid Line (Default)
```xml
style="endArrow=classic;html=1;rounded=0;...;dashed=0;"
```
**Use for**: Data flow, API calls, direct service connections
**Example**: User → API Gateway → Lambda

### Dashed Line
```xml
style="...;dashed=1;dashPattern=8 8;"
```
**Use for**: Replication, monitoring, logging, backup, container registry (ECR)
**Example**: RDS Primary → RDS Read Replica, Lambda → CloudWatch, ECR → ECS/Lambda (Pull Container)

**Dash Patterns**:
- `8 8`: Standard dashed (8px dash, 8px gap)
- `4 4`: Fine dashed (4px dash, 4px gap)
- `12 4`: Long dash (12px dash, 4px gap)

### Dotted Line
```xml
style="...;dashed=1;dashPattern=1 3;"
```
**Use for**: Optional connections, conditional flows
**Example**: Optional backup connections

## Right-Angle Routing

Always use right-angle (L-shaped) routing instead of diagonal connections. This creates clean, professional diagrams.

### Simple Right-Angle (No Waypoints)

For components that are directly aligned:
```xml
<mxCell id="edge-1" 
        value="Data Flow" 
        style="endArrow=classic;html=1;rounded=0;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;" 
        parent="1" 
        source="source-id" 
        target="target-id" 
        edge="1">
    <mxGeometry relative="1" as="geometry" />
</mxCell>
```

### Complex Right-Angle (With Waypoints)

For components that are far apart or need to route around obstacles:

```xml
<mxCell id="edge-1" 
        value="Data Flow" 
        style="endArrow=classic;html=1;rounded=0;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;" 
        parent="1" 
        source="source-id" 
        target="target-id" 
        edge="1">
    <mxGeometry relative="1" as="geometry">
        <Array as="points">
            <mxPoint x="400" y="500" />
            <mxPoint x="400" y="600" />
        </Array>
    </mxGeometry>
</mxCell>
```

**Waypoint Calculation**:
1. Determine source position: `source_x, source_y`
2. Determine target position: `target_x, target_y`
3. Calculate midpoint: `mid_x = (source_x + target_x) / 2`
4. Create waypoints:
   - First waypoint: Extend horizontally from source: `(mid_x, source_y + icon_height/2)`
   - Second waypoint: Turn vertical toward target: `(mid_x, target_y + icon_height/2)`

## Connection Labeling

### Best Practices

1. **Use Action Verbs**: "Invoke", "Query", "Store", "Trigger", "Replicate"
2. **Be Concise**: 1-2 words maximum
3. **Be Descriptive**: Clearly indicate the connection type
4. **Use Capitalization**: Capitalize first letter for consistency

### Common Labels

| Connection Type | Example Labels |
|----------------|----------------|
| API Calls | "Invoke", "API Request", "HTTP Request" |
| Database | "Query", "Read", "Write", "Store" |
| Events | "S3 Event", "Event Trigger", "Notification" |
| Replication | "Replicate", "Sync", "Backup" |
| Monitoring | "Logs", "Metrics", "Monitor" |
| Storage | "Store Data", "Save", "Upload" |
| Container Registry | "Pull Container", "Pull Image", "Container Image" |

### Label Placement

Labels automatically appear at the midpoint of the connection. No manual positioning needed.

## Routing Algorithms

### Algorithm 1: Direct Connection (No Routing)

**When to use**: Components are directly aligned (vertically or horizontally)

**Steps**:
1. Identify alignment: vertical or horizontal
2. If vertical: `exitX=0.5, exitY=1, entryX=0.5, entryY=0`
3. If horizontal: `exitX=1, exitY=0.5, entryX=0, entryY=0.5`
4. No waypoints needed

### Algorithm 2: Simple Right-Angle Routing

**When to use**: Components are offset but not too far apart

**Steps**:
1. Calculate midpoint between source and target
2. Create one waypoint at midpoint
3. Route: Source → Waypoint → Target
4. Creates L-shaped connection

### Algorithm 3: Complex Routing (Multiple Waypoints)

**When to use**: Components are far apart or need to route around obstacles

**Steps**:
1. Identify routing path around obstacles
2. Create waypoints at each turn point
3. Route: Source → Waypoint1 → Waypoint2 → ... → Target
4. Maintains right-angle routing

## Avoiding Connection Overlaps

### Problem: Overlapping Connections

When multiple connections share the same path, they can overlap and become hard to read.

### Solutions

1. **Space Vertically**: Offset connections vertically when multiple connections exist
2. **Use Different Entry/Exit Points**: Vary exit/entry points for parallel connections
3. **Group Related Connections**: Keep related connections together
4. **Use Waypoints**: Route connections around each other

### Example: Multiple Connections from Same Source

```xml
<!-- Connection 1: Top exit point -->
<mxCell id="edge-1" 
        style="...;exitX=0.5;exitY=0;entryX=0.5;entryY=1;..." 
        source="lambda" 
        target="s3" 
        edge="1">
    <mxGeometry relative="1" as="geometry">
        <Array as="points">
            <mxPoint x="200" y="50" />
        </Array>
    </mxGeometry>
</mxCell>

<!-- Connection 2: Bottom exit point -->
<mxCell id="edge-2" 
        style="...;exitX=0.5;exitY=1;entryX=0.5;entryY=0;..." 
        source="lambda" 
        target="rds" 
        edge="1">
    <mxGeometry relative="1" as="geometry" />
</mxCell>
```

## Connection Examples

### Example 1: User → API Gateway → Lambda

```xml
<!-- User to API Gateway -->
<mxCell id="edge-user-api" 
        value="HTTP Request" 
        style="endArrow=classic;html=1;rounded=0;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;" 
        parent="1" 
        source="user" 
        target="api-gateway" 
        edge="1">
    <mxGeometry relative="1" as="geometry" />
</mxCell>

<!-- API Gateway to Lambda -->
<mxCell id="edge-api-lambda" 
        value="Invoke" 
        style="endArrow=classic;html=1;rounded=0;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;" 
        parent="1" 
        source="api-gateway" 
        target="lambda" 
        edge="1">
    <mxGeometry relative="1" as="geometry" />
</mxCell>
```

### Example 2: S3 Event Trigger

```xml
<!-- S3 to Lambda (Event-driven) -->
<mxCell id="edge-s3-lambda" 
        value="S3 Event" 
        style="endArrow=classic;html=1;rounded=0;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;" 
        parent="1" 
        source="s3-bucket" 
        target="lambda-function" 
        edge="1">
    <mxGeometry relative="1" as="geometry" />
</mxCell>
```

### Example 3: Monitoring Connection (Dashed)

```xml
<!-- Lambda to CloudWatch (Monitoring) -->
<mxCell id="edge-lambda-cloudwatch" 
        value="Logs" 
        style="endArrow=classic;html=1;rounded=0;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;dashed=1;dashPattern=8 8;" 
        parent="1" 
        source="lambda-monitored" 
        target="cloudwatch-1" 
        edge="1">
    <mxGeometry relative="1" as="geometry" />
</mxCell>
```

### Example 3b: ECR Container Pull (Dashed)

```xml
<!-- ECR to ECS (Container Registry) -->
<mxCell id="edge-ecr-ecs" 
        value="Pull Container" 
        style="endArrow=classic;html=1;rounded=0;exitX=0.5;exitY=0;exitDx=0;exitDy=0;entryX=0.5;entryY=1.256;entryDx=0;entryDy=0;dashed=1;dashPattern=8 8;" 
        parent="1" 
        source="ecr" 
        target="ecs-frontend" 
        edge="1">
    <mxGeometry relative="1" as="geometry">
        <Array as="points">
            <mxPoint x="708" y="659" />
            <mxPoint x="419" y="400" />
        </Array>
    </mxGeometry>
</mxCell>
```

**Notes**: 
- ECR connections should always use dashed lines (`dashed=1;dashPattern=8 8;`) to indicate container image retrieval operations, distinguishing them from active data flow connections.
- Uses `entryY=1.256` to connect to the extended bottom connection point (20px below icon), avoiding overlap with the icon label.

### Example 4: Complex Routing with Waypoints

```xml
<!-- Lambda to S3 (far apart) -->
<mxCell id="edge-lambda-s3" 
        value="Store Data" 
        style="endArrow=classic;html=1;rounded=0;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;" 
        parent="1" 
        source="lambda" 
        target="s3" 
        edge="1">
    <mxGeometry relative="1" as="geometry">
        <Array as="points">
            <mxPoint x="500" y="400" />
            <mxPoint x="500" y="600" />
            <mxPoint x="800" y="600" />
        </Array>
    </mxGeometry>
</mxCell>
```

## Best Practices Summary

1. **Always use right-angle routing** - Never use diagonal connections
2. **Label all connections** - Use descriptive action verbs
3. **Use appropriate line styles** - Solid for data flow, dashed for monitoring/replication
4. **Avoid overlaps** - Space connections vertically or use waypoints
5. **Use extended bottom connection points** - When connecting to bottom of icon, use `entryY=1.256` to connect below the label (20px below icon)
6. **Keep connections parallel** - When multiple connections exist, keep them aligned
7. **Group related connections** - Keep related flows together visually
8. **Use consistent arrow styles** - Always use `endArrow=classic`
9. **Calculate waypoints carefully** - Ensure waypoints create clean routing

## Common Mistakes to Avoid

1. **Diagonal connections** - Always use right-angle routing
2. **Unlabeled connections** - Always label connections
3. **Overlapping connections** - Space them vertically
4. **Wrong exit/entry points** - Use nearest points to target
5. **Connecting through labels** - When connecting to bottom of icon, use `entryY=1.256` (extended connection point) instead of `entryY=1` to avoid overlapping the label
6. **Missing waypoints** - Add waypoints for complex routing
7. **Inconsistent styles** - Use same style for same connection types
8. **Too many waypoints** - Keep routing simple (2-3 waypoints max)

## Connections with Nested Services

When services are nested inside groups (VPC, subnets, etc.), connections work the same way but must be placed at the top level:

**Example**: Lambda (in Private Subnet) → RDS (in Private Subnet)
```xml
<!-- Lambda inside Private Subnet -->
<mxCell id="lambda-1" 
        value="Lambda Function" 
        style="...;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.lambda;..." 
        parent="private-subnet-1" 
        vertex="1">
    <mxGeometry x="50" y="50" width="78" height="78" as="geometry" />
</mxCell>

<!-- RDS inside Private Subnet -->
<mxCell id="rds-1" 
        value="RDS" 
        style="...;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.rds;..." 
        parent="private-subnet-1" 
        vertex="1">
    <mxGeometry x="250" y="50" width="78" height="78" as="geometry" />
</mxCell>

<!-- Connection (parent="1" even though services are in groups) -->
<mxCell id="edge-lambda-rds" 
        value="Query" 
        style="endArrow=classic;html=1;rounded=0;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;" 
        parent="1" 
        source="lambda-1" 
        target="rds-1" 
        edge="1">
    <mxGeometry relative="1" as="geometry" />
</mxCell>
```

**Key points**:
- Services have `parent="group-id"` (nested in groups)
- Connections have `parent="1"` (top-level, can cross group boundaries)
- Connections automatically route through group boundaries
- See `templates/base/AWS_diagram_design_patterns.drawio` (tab "AWS Groups", section "AWS Services in Group Examples") for complete examples

## Reference Template

See `templates/base/AWS_diagram_design_patterns.drawio`:
- Tab "AWS Connection Patterns" - Connection styling examples
- Tab "AWS Groups", section "AWS Services in Group Examples" - Connections with nested services

This is the authoritative source for connection styling.

