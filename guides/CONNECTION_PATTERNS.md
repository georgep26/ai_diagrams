# Connection Patterns Guide

This guide explains how to create clean, readable connections between AWS service components in draw.io diagrams.

## Overview

Connections in draw.io represent data flow, API calls, triggers, and relationships between AWS services. Proper connection routing ensures diagrams are readable and professional.

## Connection Basics

### Connection Structure

A connection in draw.io XML is an `mxCell` with `edge="1"`:

```xml
<mxCell id="edge-1" 
        value="Connection Label" 
        style="endArrow=classic;html=1;rounded=0;exitX=0.5;exitY=1;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0;" 
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

### Common Exit/Entry Patterns

#### Top to Bottom (Vertical)
```xml
exitX=0.5;exitY=1;entryX=0.5;entryY=0
```
- Source: Exit from bottom center
- Target: Enter at top center
- Use case: User → API Gateway → Lambda

#### Left to Right (Horizontal)
```xml
exitX=1;exitY=0.5;entryX=0;entryY=0.5
```
- Source: Exit from right side center
- Target: Enter at left side center
- Use case: Lambda → RDS, Lambda → S3

#### Right to Left (Horizontal)
```xml
exitX=0;exitY=0.5;entryX=1;entryY=0.5
```
- Source: Exit from left side center
- Target: Enter at right side center
- Use case: S3 → Lambda (event-driven)

#### Bottom to Top (Vertical)
```xml
exitX=0.5;exitY=0;entryX=0.5;entryY=1
```
- Source: Exit from top center
- Target: Enter at bottom center
- Use case: Rare, but used for reverse flows

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
**Use for**: Replication, monitoring, logging, backup
**Example**: RDS Primary → RDS Read Replica, Lambda → CloudWatch

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
        style="endArrow=classic;html=1;rounded=0;exitX=0.5;exitY=1;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0;" 
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
        style="endArrow=classic;html=1;rounded=0;exitX=0.5;exitY=1;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0;" 
        parent="1" 
        source="user" 
        target="api-gateway" 
        edge="1">
    <mxGeometry relative="1" as="geometry" />
</mxCell>

<!-- API Gateway to Lambda -->
<mxCell id="edge-api-lambda" 
        value="Invoke" 
        style="endArrow=classic;html=1;rounded=0;exitX=0.5;exitY=1;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0;" 
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

### Example 3: RDS Replication (Dashed)

```xml
<!-- RDS Primary to Read Replica -->
<mxCell id="edge-rds-replica" 
        value="Replication" 
        style="endArrow=classic;html=1;rounded=0;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;dashed=1;dashPattern=8 8;" 
        parent="1" 
        source="rds-primary" 
        target="rds-replica" 
        edge="1">
    <mxGeometry relative="1" as="geometry" />
</mxCell>
```

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
5. **Keep connections parallel** - When multiple connections exist, keep them aligned
6. **Group related connections** - Keep related flows together visually
7. **Use consistent arrow styles** - Always use `endArrow=classic`
8. **Calculate waypoints carefully** - Ensure waypoints create clean routing

## Common Mistakes to Avoid

1. **Diagonal connections** - Always use right-angle routing
2. **Unlabeled connections** - Always label connections
3. **Overlapping connections** - Space them vertically
4. **Wrong exit/entry points** - Use nearest points to target
5. **Missing waypoints** - Add waypoints for complex routing
6. **Inconsistent styles** - Use same style for same connection types
7. **Too many waypoints** - Keep routing simple (2-3 waypoints max)

## Reference Template

See `templates/base/aws-connection-patterns.drawio` for complete examples of all connection patterns.

