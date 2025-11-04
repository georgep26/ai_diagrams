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

### Horizontal Spacing

| Spacing Type | Distance | Calculation | Use Case |
|-------------|----------|-------------|----------|
| **Icon to Icon** | 150px | 78px (icon) + 72px (padding) | Services in same row |
| **Subnet Padding** | 50px | From edge to first icon | Space around subnet edges |
| **Subnet to Subnet** | 200px | Between subnet boundaries | Space between AZs |
| **Container Padding** | 100px | From container edge | Space inside containers |

**Formula**: `next_x = current_x + icon_width + spacing`

Example: If Lambda at x=50, next icon at x=278 (50 + 78 + 150)

### Vertical Spacing

| Spacing Type | Distance | Calculation | Use Case |
|-------------|----------|-------------|----------|
| **Row to Row** | 150px | 78px (icon) + 72px (padding) | Services in same column |
| **Subnet Label to Content** | 100px | Below subnet label | Space for label |
| **Subnet to Subnet** | 100px | Between subnet boundaries | Vertical spacing |
| **Container Top Padding** | 50px | From container top | Space for container label |

**Formula**: `next_y = current_y + icon_height + spacing`

Example: If Lambda at y=100, next row at y=328 (100 + 78 + 150)

## Grid-Based Positioning

### Grid System

Use a 10px grid for alignment:
- **Grid Size**: 10px
- **Grid Enabled**: `grid="1"` in mxGraphModel
- **All positions**: Multiples of 10px for clean alignment

### Grid Calculation

Round all positions to nearest 10px:
- `x = 50` ✓ (multiple of 10)
- `x = 53` ✗ (not aligned)
- `x = 50` ✓ (rounded to 50)

## Layout Patterns

### Pattern 1: Single Row Layout

**Use case**: Services that interact sequentially (e.g., User → API Gateway → Lambda)

```
[Icon] --150px-- [Icon] --150px-- [Icon]
```

**Positioning**:
- Start x: 50px (subnet padding)
- Icon width: 78px
- Spacing: 150px
- Next icon x: `previous_x + 78 + 150 = previous_x + 228`

### Pattern 2: Multi-Row Layout

**Use case**: Multiple services in same subnet (e.g., Lambda functions)

```
Row 1: [Icon] --150px-- [Icon] --150px-- [Icon]
Row 2: [Icon] --150px-- [Icon] --150px-- [Icon]
        ↑
      150px spacing
```

**Positioning**:
- Row 1 y: 100px (below subnet label)
- Row 2 y: `100 + 78 + 150 = 328px`
- Row 3 y: `328 + 78 + 150 = 556px`

### Pattern 3: Grid Layout

**Use case**: Multiple services arranged in rows and columns

```
[Icon] --150px-- [Icon] --150px-- [Icon]
  |                |                |
150px           150px           150px
  |                |                |
[Icon] --150px-- [Icon] --150px-- [Icon]
```

**Positioning**:
- Calculate x for each column: `x = 50 + (column_index * 228)`
- Calculate y for each row: `y = 100 + (row_index * 228)`

## Container Layout

### VPC Layout

```
┌─────────────────────────────────────┐
│ AWS Cloud (Internet Container)      │
│  ┌───────────────────────────────┐  │
│  │ VPC (10.0.0.0/16)             │  │
│  │  ┌────────────┐ ┌────────────┐ │  │
│  │  │ Public AZ1 │ │ Public AZ2 │ │  │
│  │  └────────────┘ └────────────┘ │  │
│  │  ┌────────────┐ ┌────────────┐ │  │
│  │  │Private AZ1 │ │Private AZ2 │ │  │
│  │  └────────────┘ └────────────┘ │  │
│  └───────────────────────────────┘  │
└─────────────────────────────────────┘
```

**Positioning**:
- Internet container: x=40, y=100, width=3200, height=2200
- VPC: x=400, y=150, width=2800, height=2100
- Public Subnet 1: x=100, y=200, width=1200, height=600
- Public Subnet 2: x=1500, y=200, width=1200, height=600
- Private Subnet 1: x=100, y=900, width=1200, height=1100
- Private Subnet 2: x=1500, y=900, width=1200, height=1100

### Subnet Layout

```
┌────────────────────────────┐
│ Public Subnet (AZ-1)       │  ← Label at top
│                             │
│  [Icon] [Icon] [Icon]      │  ← 50px padding from edge
│                             │
│  [Icon] [Icon] [Icon]      │  ← 150px row spacing
│                             │
└────────────────────────────┘
```

**Positioning**:
- Subnet label: Automatic (container label)
- First icon x: 50px (padding)
- First icon y: 100px (below label)
- Icon spacing: 150px horizontal, 150px vertical

## Alignment Rules

### Horizontal Alignment

**Same Row**: All icons in same row have same `y` value
```xml
<!-- Row 1: All at y=100 -->
<mxGeometry x="50" y="100" ... />
<mxGeometry x="278" y="100" ... />
<mxGeometry x="506" y="100" ... />
```

**Centered**: Center icons in container
```xml
<!-- Container width: 1200px, icon width: 78px -->
<!-- Center calculation: (1200 - 78) / 2 = 561px -->
<mxGeometry x="561" y="100" ... />
```

### Vertical Alignment

**Same Column**: All icons in same column have same `x` value
```xml
<!-- Column 1: All at x=50 -->
<mxGeometry x="50" y="100" ... />
<mxGeometry x="50" y="328" ... />
<mxGeometry x="50" y="556" ... />
```

## Spacing Calculations

### Formula: Next Icon Position

**Horizontal (same row)**:
```
next_x = current_x + icon_width + spacing
next_x = current_x + 78 + 150
next_x = current_x + 228
```

**Vertical (same column)**:
```
next_y = current_y + icon_height + spacing
next_y = current_y + 78 + 150
next_y = current_y + 228
```

### Formula: Grid Position

**Round to nearest 10px**:
```
grid_x = round(current_x / 10) * 10
```

Example: `53 → 50`, `57 → 60`, `155 → 160`

### Formula: Container Size

**Subnet width calculation**:
```
subnet_width = (num_icons_per_row * 228) + 100
```
- 100px = 50px left padding + 50px right padding
- 228px = 78px icon + 150px spacing

**Subnet height calculation**:
```
subnet_height = (num_rows * 228) + 200
```
- 200px = 100px top padding + 100px bottom padding
- 228px = 78px icon + 150px spacing

## Example Layouts

### Example 1: Three Lambda Functions in Row

```xml
<!-- Lambda 1 -->
<mxCell id="lambda-1" ...>
    <mxGeometry x="50" y="100" width="78" height="78" as="geometry" />
</mxCell>

<!-- Lambda 2: 228px to the right -->
<mxCell id="lambda-2" ...>
    <mxGeometry x="278" y="100" width="78" height="78" as="geometry" />
</mxCell>

<!-- Lambda 3: Another 228px to the right -->
<mxCell id="lambda-3" ...>
    <mxGeometry x="506" y="100" width="78" height="78" as="geometry" />
</mxCell>
```

### Example 2: Lambda Functions in Grid (2x2)

```xml
<!-- Row 1, Column 1 -->
<mxCell id="lambda-1" ...>
    <mxGeometry x="50" y="100" width="78" height="78" as="geometry" />
</mxCell>

<!-- Row 1, Column 2 -->
<mxCell id="lambda-2" ...>
    <mxGeometry x="278" y="100" width="78" height="78" as="geometry" />
</mxCell>

<!-- Row 2, Column 1 -->
<mxCell id="lambda-3" ...>
    <mxGeometry x="50" y="328" width="78" height="78" as="geometry" />
</mxCell>

<!-- Row 2, Column 2 -->
<mxCell id="lambda-4" ...>
    <mxGeometry x="278" y="328" width="78" height="78" as="geometry" />
</mxCell>
```

## Container Sizing Guidelines

### Minimum Subnet Size

For a subnet with 3 icons per row and 2 rows:
- Width: `(3 * 228) + 100 = 784px` (round to 800px)
- Height: `(2 * 228) + 200 = 656px` (round to 700px)

### Recommended Subnet Size

For a subnet with 4 icons per row and 3 rows:
- Width: `(4 * 228) + 100 = 1012px` (round to 1200px)
- Height: `(3 * 228) + 200 = 884px` (round to 1100px)

### VPC Size

For a VPC with 2 subnets side-by-side:
- Width: `(2 * 1200) + 200 = 2600px` (round to 2800px)
- Height: `1100px` (private subnet height, round to 2100px for flexibility)

## Best Practices

1. **Use Grid Alignment**: Always align to 10px grid
2. **Consistent Spacing**: Use 150px between icons
3. **Padding**: 50px from container edges
4. **Standard Icon Size**: Always 78x78 for AWS icons
5. **Calculate Positions**: Use formulas, don't guess
6. **Round to Grid**: Round all positions to nearest 10px
7. **Group Related**: Keep related services together
8. **Visual Hierarchy**: Use spacing to show relationships

## Common Mistakes to Avoid

1. **Inconsistent Spacing**: Mixing different spacing values
2. **Off-Grid Positioning**: Positions not aligned to 10px grid
3. **Too Dense**: Icons too close together (less than 150px)
4. **Too Sparse**: Icons too far apart (more than 200px)
5. **Wrong Icon Size**: Not using standard 78x78 size
6. **Missing Padding**: Icons touching container edges
7. **Misaligned Rows**: Icons in same row with different y values
8. **Misaligned Columns**: Icons in same column with different x values

## Quick Reference

### Standard Values

- **Icon Size**: 78x78px
- **Icon Spacing**: 150px
- **Subnet Padding**: 50px
- **Subnet Spacing**: 200px
- **Container Padding**: 100px
- **Grid Size**: 10px

### Position Formulas

- **Next Icon (Horizontal)**: `x = previous_x + 228`
- **Next Icon (Vertical)**: `y = previous_y + 228`
- **Grid Align**: `position = round(position / 10) * 10`
- **Subnet Width**: `(icons_per_row * 228) + 100`
- **Subnet Height**: `(num_rows * 228) + 200`

## Reference Template

See `templates/base/aws-vpc-template.drawio` for complete layout examples.

