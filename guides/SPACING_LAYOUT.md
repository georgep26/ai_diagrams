# Spacing and Layout Guide

This guide provides standards for spacing, alignment, and layout in AWS architecture diagrams.

## Overview

Consistent spacing and layout make diagrams readable and professional. This guide establishes standard spacing calculations and layout patterns.

## Standard Dimensions

### Icon Sizes

| Component Type | Width | Height | Notes |
|---------------|-------|--------|-------|
| **AWS Service Icons** | 78px | 78px | Standard size for all AWS icons |
| **User Icons** | 60px | 60px | Slightly smaller for users |
| **Text Labels** | Variable | Variable | Based on text length |

**Important**: Always use `aspect=fixed` in style to maintain icon proportions.

### Container Sizes

| Container Type | Minimum Width | Minimum Height | Notes |
|---------------|---------------|----------------|-------|
| **VPC** | 2800px | 2100px | Large container for entire network |
| **Subnet (Public)** | 1200px | 600px | Accommodates multiple services |
| **Subnet (Private)** | 1200px | 1100px | Taller for more services |
| **AWS Cloud Boundary** | 3200px | 2200px | Outermost container |

## Spacing Standards

**Reference**: All spacing values are based on `templates/AWS_diagram_design_patterns.drawio` tabs "AWS Connection Patterns" and "AWS Groups".

### Horizontal Spacing

| Spacing Type | Distance | Calculation | Use Case |
|-------------|----------|-------------|----------|
| **Icon to Icon (78px icons)** | 200px | Between icon x positions | Services in same row |
| **Icon to Icon (60px User icon)** | 200px | Between icon x positions | User to service spacing |
| **Edge-to-Edge Gap (78px icons)** | 122px | 200px - 78px | Actual gap between icon edges |
| **Edge-to-Edge Gap (User to 78px)** | 140px | 200px - 60px | Gap from User to service |
| **Subnet Padding** | 50-80px | From edge to first icon | Space around subnet edges (varies by example) |
| **Group Padding** | 30px | `spacingLeft=30` in groups | Left padding inside groups |
| **Group to Group** | 200px | Between group x positions | Horizontal spacing between groups |

**Formula**: `next_x = current_x + 200` (for 78px icons)

Example: If Lambda at x=80, next icon at x=280 (80 + 200)

### Vertical Spacing

| Spacing Type | Distance | Calculation | Use Case |
|-------------|----------|-------------|----------|
| **Row to Row (Connection Patterns)** | 250px | Between icon y positions | Services in same column |
| **Row to Row (Groups Examples)** | 200px | Between icon y positions | Services in nested groups |
| **Edge-to-Edge Gap (78px icons)** | 172px | 250px - 78px | Actual gap between icon edges (Connection Patterns) |
| **Edge-to-Edge Gap (Groups)** | 122px | 200px - 78px | Actual gap between icon edges (Groups) |
| **Group to Group (Vertical)** | 200px | Between group y positions | Vertical spacing between groups |
| **Container Top Padding** | 30-80px | From container top | Space for container label (varies by example) |

**Formula**: 
- Connection Patterns: `next_y = current_y + 250`
- Groups Examples: `next_y = current_y + 200`

Example: 
- Connection Patterns: If Lambda at y=84, next row at y=334 (84 + 250)
- Groups Examples: If Lambda at y=80, next row at y=280 (80 + 200)

## Grid-Based Positioning

### Grid System

Use a 10px grid for alignment:
- **Grid Size**: 10px (`gridSize="10"` in mxGraphModel)
- **Grid Visible**: `grid="0"` in mxGraphModel (default: no visible grid)
- **All positions**: Multiples of 10px for clean alignment
- **Note**: Grid alignment still works even when `grid="0"` (grid is not visible but positions still snap to 10px)

### Grid Calculation

Round all positions to nearest 10px:
- `x = 50` ✓ (multiple of 10)
- `x = 53` ✗ (not aligned)
- `x = 50` ✓ (rounded to 50)

## Layout Patterns

### Pattern 1: Single Row Layout

**Use case**: Services that interact sequentially (e.g., User → API Gateway → Lambda)

**Reference**: See `AWS_diagram_design_patterns.drawio` tab "AWS Connection Patterns" (User → API Gateway → Lambda example)

```
[Icon] --200px-- [Icon] --200px-- [Icon]
```

**Positioning**:
- Start x: 80px (as shown in Connection Patterns tab)
- Icon width: 78px (or 60px for User)
- Spacing: 200px between x positions
- Next icon x: `previous_x + 200`
- Example: User at x=80, API Gateway at x=280, Lambda at x=480

### Pattern 2: Multi-Row Layout

**Use case**: Multiple services in same subnet (e.g., Lambda functions)

**Reference**: See `AWS_diagram_design_patterns.drawio` tab "AWS Connection Patterns" (S3 → Lambda, Lambda → RDS examples)

```
Row 1: [Icon] --200px-- [Icon]
Row 2: [Icon] --200px-- [Icon]
        ↑
      250px spacing (Connection Patterns)
      200px spacing (Groups Examples)
```

**Positioning** (Connection Patterns style):
- Row 1 y: 84px (as shown in examples)
- Row 2 y: `84 + 250 = 334px`
- Row 3 y: `334 + 250 = 584px`

**Positioning** (Groups Examples style):
- Row 1 y: 80px (as shown in nested examples)
- Row 2 y: `80 + 200 = 280px`
- Row 3 y: `280 + 200 = 480px`

### Pattern 3: Grid Layout

**Use case**: Multiple services arranged in rows and columns

**Reference**: See `AWS_diagram_design_patterns.drawio` tab "AWS Groups", section "AWS Services in Group Examples" (S3, Lambda, CloudWatch in VPC)

```
[Icon] --200px-- [Icon] --173px-- [Icon]
  |                |                |
200px           200px           200px
  |                |                |
[Icon] --200px-- [Icon] --173px-- [Icon]
```

**Positioning** (Groups Examples style):
- Standard spacing: 200px between icon positions
- Example from template: S3 at x=55, Lambda at x=228 (173px spacing), CloudWatch at x=401 (173px spacing)
- **Recommended**: Use 200px standard spacing: `x = start_x + (column_index * 200)`
- Calculate y for each row: `y = 85 + (row_index * 200)` (starting at 85px with 200px spacing)
- Note: The example shows 173px spacing, but use 200px as the standard for consistency

## Container Layout

**Reference**: See `templates/AWS_diagram_design_patterns.drawio` tab "AWS Groups" for actual group layouts and spacing.

### VPC Layout (Conceptual)

```
┌─────────────────────────────────────┐
│ AWS Cloud                            │
│  ┌───────────────────────────────┐  │
│  │ VPC                             │  │
│  │  ┌────────────┐ ┌────────────┐ │  │
│  │  │ Public AZ1 │ │ Public AZ2 │ │  │
│  │  └────────────┘ └────────────┘ │  │
│  │  ┌────────────┐ ┌────────────┐ │  │
│  │  │Private AZ1 │ │Private AZ2 │ │  │
│  │  └────────────┘ └────────────┘ │  │
│  └───────────────────────────────┘  │
└─────────────────────────────────────┘
```

**Note**: This is a conceptual layout. For actual positioning and spacing, reference:
- `AWS_diagram_design_patterns.drawio` tab "AWS Groups" for group examples
- Section "AWS Services in Group Examples" for nested VPC structure
- Groups use 200px spacing between group positions
- Services inside groups use 200px spacing (Groups style) or 250px (Connection Patterns style)

### Subnet Layout

**Reference**: See `AWS_diagram_design_patterns.drawio` tab "AWS Groups", section "AWS Services in Group Examples"

```
┌────────────────────────────┐
│ Example VPC                 │  ← Label at top
│                             │
│  [Icon] [Icon] [Icon]       │  ← 80px padding from edge (VPC example)
│                             │
│  [Icon] [Icon] [Icon]       │  ← 200px row spacing (Groups style)
│                             │
└────────────────────────────┘
```

**Positioning** (based on Groups Examples):
- Subnet/VPC label: Automatic (container label)
- First icon x: 80px (as shown in VPC example) or 55px (as shown in nested VPC example)
- First icon y: 80px (as shown in VPC example) or 85px (as shown in nested VPC example)
- Icon spacing: 200px horizontal, 200px vertical (Groups style)
- Group padding: `spacingLeft=30` in group style

## Alignment Rules

### Horizontal Alignment

**Same Row**: All icons in same row have same `y` value
```xml
<!-- Row 1: All at y=84 (Connection Patterns style) -->
<mxGeometry x="80" y="84" ... />
<mxGeometry x="280" y="84" ... />
<mxGeometry x="480" y="84" ... />

<!-- Row 1: All at y=85 (Groups Examples style) -->
<mxGeometry x="55" y="85" ... />
<mxGeometry x="255" y="85" ... />
<mxGeometry x="455" y="85" ... />
```

**Centered**: Center icons in container
```xml
<!-- Container width: 1000px, icon width: 78px -->
<!-- Center calculation: (1000 - 78) / 2 = 461px -->
<mxGeometry x="461" y="85" ... />
```

### Vertical Alignment

**Same Column**: All icons in same column have same `x` value
```xml
<!-- Column 1: All at x=80 (Connection Patterns style) -->
<mxGeometry x="80" y="84" ... />
<mxGeometry x="80" y="334" ... />
<mxGeometry x="80" y="584" ... />

<!-- Column 1: All at x=55 (Groups Examples style) -->
<mxGeometry x="55" y="85" ... />
<mxGeometry x="55" y="285" ... />
<mxGeometry x="55" y="485" ... />
```

## Spacing Calculations

**Reference**: Based on `templates/AWS_diagram_design_patterns.drawio` tabs "AWS Connection Patterns" and "AWS Groups".

### Formula: Next Icon Position

**Horizontal (same row)**:
```
next_x = current_x + 200
```
- Standard spacing: 200px between icon x positions
- Edge-to-edge gap: 200px - 78px = 122px (for 78px icons)
- Example: Lambda at x=80, next icon at x=280 (80 + 200)

**Vertical (same column)**:
```
# Connection Patterns style:
next_y = current_y + 250

# Groups Examples style:
next_y = current_y + 200
```
- Connection Patterns: 250px between icon y positions
- Groups Examples: 200px between icon y positions
- Edge-to-edge gap: 250px - 78px = 172px (Connection Patterns) or 200px - 78px = 122px (Groups)
- Example: Lambda at y=84, next row at y=334 (84 + 250) for Connection Patterns
- Example: Lambda at y=80, next row at y=280 (80 + 200) for Groups Examples

### Formula: Grid Position

**Round to nearest 10px**:
```
grid_x = round(current_x / 10) * 10
```

Example: `53 → 50`, `57 → 60`, `155 → 160`

### Formula: Container Size

**Subnet/VPC width calculation** (Groups Examples style):
```
subnet_width = (num_icons_per_row * 200) + padding
```
- Padding: 80px left + 80px right = 160px (or adjust based on content)
- 200px = spacing between icon x positions
- Example: 3 icons = (3 * 200) + 160 = 760px minimum

**Subnet/VPC height calculation** (Groups Examples style):
```
subnet_height = (num_rows * 200) + padding
```
- Padding: 80px top + 80px bottom = 160px (or adjust based on content)
- 200px = spacing between icon y positions
- Example: 2 rows = (2 * 200) + 160 = 560px minimum

**Note**: Actual container sizes in examples vary. Size containers to accommodate all nested services with appropriate padding.

## Example Layouts

### Example 1: Three Services in Row (Connection Patterns Style)

**Reference**: See `AWS_diagram_design_patterns.drawio` tab "AWS Connection Patterns" (User → API Gateway → Lambda)

```xml
<!-- User -->
<mxCell id="user-1" ...>
    <mxGeometry x="80" y="93" width="60" height="60" as="geometry" />
</mxCell>

<!-- API Gateway: 200px to the right -->
<mxCell id="api-gateway-1" ...>
    <mxGeometry x="280" y="84" width="78" height="78" as="geometry" />
</mxCell>

<!-- Lambda: Another 200px to the right -->
<mxCell id="lambda-1" ...>
    <mxGeometry x="480" y="84" width="78" height="78" as="geometry" />
</mxCell>
```

### Example 2: Services in Grid (Groups Examples Style)

**Reference**: See `AWS_diagram_design_patterns.drawio` tab "AWS Groups", section "AWS Services in Group Examples" (S3, Lambda, CloudWatch in VPC)

```xml
<!-- Row 1, Column 1: S3 -->
<mxCell id="example-s3" ...>
    <mxGeometry x="55" y="85" width="78" height="78" as="geometry" />
</mxCell>

<!-- Row 1, Column 2: Lambda (173px spacing in example) -->
<mxCell id="example-lambda-nested" ...>
    <mxGeometry x="228" y="85" width="78" height="78" as="geometry" />
</mxCell>

<!-- Row 1, Column 3: CloudWatch (173px spacing in example) -->
<mxCell id="example-cloudwatch" ...>
    <mxGeometry x="401" y="85" width="78" height="78" as="geometry" />
</mxCell>
```

**Note**: Spacing can vary. Use 200px as standard, but adjust as needed (example shows 173px between some icons).

## Container Sizing Guidelines

**Reference**: Based on `AWS_diagram_design_patterns.drawio` tab "AWS Groups", section "AWS Services in Group Examples".

### Minimum Subnet/VPC Size

For a container with 3 icons per row and 2 rows (Groups Examples style):
- Width: `(3 * 200) + 160 = 760px` (minimum, round up as needed)
- Height: `(2 * 200) + 160 = 560px` (minimum, round up as needed)
- Example from template: VPC with 3 icons in row = 437px width (actual size varies)

### Recommended Subnet/VPC Size

For a container with 4 icons per row and 3 rows (Groups Examples style):
- Width: `(4 * 200) + 160 = 960px` (minimum, round to 1000px+)
- Height: `(3 * 200) + 160 = 760px` (minimum, round to 800px+)
- Add extra padding for labels and visual spacing

### VPC Size

For a VPC with nested subnets:
- Size based on content: Calculate based on nested services
- Example from template: VPC with 3 services = 437px width, 263px height
- Nested VPC in Account: 534px width, 248px height
- **Recommendation**: Size containers to accommodate all nested services with 30px+ padding (`spacingLeft=30`)

## Best Practices

1. **Use Grid Alignment**: Always align to 10px grid
2. **Consistent Spacing**: Use 200px between icon positions (horizontal and vertical for Groups style)
3. **Reference Examples**: Check `AWS_diagram_design_patterns.drawio` for actual spacing used
4. **Padding**: 30px (`spacingLeft=30`) inside groups, 50-80px from container edges
5. **Standard Icon Size**: Always 78x78 for AWS service icons, 60x60 for User icons
6. **Calculate Positions**: Use formulas based on examples, don't guess
7. **Round to Grid**: Round all positions to nearest 10px
8. **Group Related**: Keep related services together
9. **Visual Hierarchy**: Use spacing to show relationships
10. **Match Style**: Use Connection Patterns spacing (250px vertical) or Groups spacing (200px vertical) consistently

## Common Mistakes to Avoid

1. **Inconsistent Spacing**: Mixing different spacing values (use 200px standard)
2. **Off-Grid Positioning**: Positions not aligned to 10px grid
3. **Too Dense**: Icons too close together (less than 200px between positions)
4. **Too Sparse**: Icons too far apart (more than 250px between positions)
5. **Wrong Icon Size**: Not using standard 78x78 size for services, 60x60 for User
6. **Missing Padding**: Icons touching container edges (use 30px+ inside groups)
7. **Misaligned Rows**: Icons in same row with different y values
8. **Misaligned Columns**: Icons in same column with different x values
9. **Not Following Examples**: Not checking actual spacing in `AWS_diagram_design_patterns.drawio`
10. **Mixing Styles**: Using Connection Patterns spacing (250px vertical) with Groups spacing (200px vertical) inconsistently

## Quick Reference

### Standard Values

**Based on `AWS_diagram_design_patterns.drawio` tabs "AWS Connection Patterns" and "AWS Groups":**

- **Icon Size**: 78x78px (services), 60x60px (User)
- **Icon Spacing (Horizontal)**: 200px between x positions
- **Icon Spacing (Vertical - Connection Patterns)**: 250px between y positions
- **Icon Spacing (Vertical - Groups Examples)**: 200px between y positions
- **Group Padding**: 30px (`spacingLeft=30`)
- **Container Edge Padding**: 50-80px (varies by example)
- **Grid Size**: 10px

### Position Formulas

- **Next Icon (Horizontal)**: `x = previous_x + 200`
- **Next Icon (Vertical - Connection Patterns)**: `y = previous_y + 250`
- **Next Icon (Vertical - Groups Examples)**: `y = previous_y + 200`
- **Grid Align**: `position = round(position / 10) * 10`
- **Subnet Width**: `(icons_per_row * 200) + padding` (padding typically 160px+)
- **Subnet Height**: `(num_rows * 200) + padding` (padding typically 160px+)

## Logical Paths Textbox Positioning

**Reference**: See `examples/rag-application.drawio` for complete implementation.

### Textbox Position

The logical paths textbox should be positioned on the **left side** of the diagram so it's one of the first things viewers see.

**Standard Positioning**:
- **X Position**: 100-200px from left edge (typically 123px)
- **Y Position**: Align with diagram start (typically 100-150px, e.g., 113px)
- **Width**: 350px (adjustable based on content)
- **Height**: Variable (calculate based on number of paths and steps)

**Example**:
```xml
<!-- Title -->
<mxGeometry x="123" y="113" width="350" height="30" as="geometry" />

<!-- Content -->
<mxGeometry x="123" y="143" width="350" height="389" as="geometry" />
```

### Numbered Badge Positioning

Numbered badges on diagram icons should be positioned at the **upper left corner** of each icon.

**Badge Size**: 24x24px (circular)

**Position Calculation**:
- Badge X: `icon_x - 10` (10px to the left of icon)
- Badge Y: `icon_y - 10` (10px above icon)

**Example**: Icon at x=633, y=277
- Badge position: x=623, y=267

**Multiple Badges on Same Icon**:
If an icon appears in multiple logical paths, position badges side-by-side:
- First badge: `x = icon_x - 10`
- Second badge: `x = icon_x + 20` (30px spacing between badges)

**Example**: Icon at x=633, y=277 with two badges
- Path 1 badge: x=623, y=267
- Path 2 badge: x=653, y=267

### Spacing Considerations

When positioning the logical paths textbox:
1. **Reserve Left Space**: Leave 100-200px on left side for textbox
2. **Main Diagram Start**: Main diagram components should start at x=600-800px (after textbox)
3. **Vertical Alignment**: Textbox y-position should align with diagram start
4. **Badge Spacing**: Badges should not overlap icons or other badges

## Reference Template

See `templates/AWS_diagram_design_patterns.drawio` (tab "AWS Groups", section "AWS Services in Group Examples") for complete layout examples with proper spacing and nesting.

