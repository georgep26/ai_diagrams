# Draw.io Templates for AWS Architecture Diagrams

This directory contains the primary template file for generating professional AWS architecture diagrams in draw.io format.

## Directory Structure

```
templates/
└── AWS_diagram_design_patterns.drawio  # Primary template with multiple tabs
```

## Primary Template

### AWS_diagram_design_patterns.drawio

**Purpose**: Comprehensive template file containing all design patterns, styles, and examples for AWS architecture diagrams.

**Contains Multiple Tabs**:

1. **AWS Icon Style** - Icon styles and examples
   - Standard AWS service icon styles
   - Proper icon shape references
   - Correct spacing calculations
   - Standard AWS color codes
   - Grid-based positioning

2. **AWS Connection Patterns** - Connection routing patterns
   - User → API Gateway → Lambda pattern
   - S3 event trigger pattern
   - Lambda → RDS database pattern
   - Multi-point routing examples
   - Dashed line patterns (replication, monitoring)
   - Cross-container connections
   - Right-angle routing (no diagonals)
   - Proper exit/entry point calculations
   - Labeled connections with action verbs

3. **AWS Groups** - Group/container styles and nesting examples
   - Complete VPC container structure
   - Public and private subnet examples
   - Internet Gateway and NAT Gateway placement
   - Example service placements (Lambda, RDS)
   - AWS Services in Group Examples section
   - Proper parent-child relationships

4. **Logical Paths** - Logical paths textbox and numbered badge examples
   - Textbox positioning and formatting
   - Numbered badge styles
   - Color schemes for different paths
   - Flexbox layout examples

**Usage**:
1. Open the template file in draw.io
2. Navigate to the relevant tab for the pattern you need
3. Copy the structure, styles, or patterns you need
4. Modify IDs, labels, and positions as needed
5. Maintain the parent-child relationships and style attributes

## Template Commenting Standards

The template includes extensive XML comments:

1. **File-level comments**: Purpose and usage instructions
2. **Section comments**: Major component groups
3. **Element comments**: For each mxCell explaining:
   - What it represents
   - Why it's positioned here
   - How to modify it
   - Related components
4. **Style comments**: Explaining style attributes
5. **Geometry comments**: Explaining positioning calculations

## Using Templates

### For AI Agents

1. **Read first**: Always read the template file (all tabs) before generating diagrams
2. **Reference tabs**: Use the appropriate tab for the pattern you need:
   - "AWS Icon Style" for icon styles
   - "AWS Connection Patterns" for connection patterns
   - "AWS Groups" for container/group styles and nesting
   - "Logical Paths" for logical paths textbox and badges
3. **Copy structure**: Copy the container hierarchy from "AWS Groups" tab
4. **Copy patterns**: Copy icon and connection patterns from relevant tabs
5. **Modify carefully**: Change only IDs, labels, and positions
6. **Maintain style**: Keep all style attributes identical

### For Human Users

1. **Open in draw.io**: Import the template file
2. **Navigate tabs**: Switch between tabs to see different patterns
3. **Customize**: Modify components as needed
4. **Maintain structure**: Keep container hierarchy intact
5. **Follow comments**: Read XML comments for guidance

## Template Customization

### Modifying the Template

When customizing based on the template:

1. **Keep structure**: Maintain container hierarchy
2. **Keep styles**: Don't change style attributes unnecessarily
3. **Update comments**: Update comments if you change structure
4. **Test icons**: Verify icons display correctly
5. **Test connections**: Verify connections route correctly

### Creating New Diagrams

To create a new diagram:

1. **Start with template**: Reference `AWS_diagram_design_patterns.drawio` for all patterns
2. **Add your components**: Add services specific to your architecture
3. **Add comments**: Document every component extensively
4. **Test thoroughly**: Verify icons and connections work
5. **Follow guides**: Use the guides in `guides/` directory for reference

## Icon Reference

For icon shape names, see:
- `guides/ICON_REFERENCE.md` - Complete icon reference

Never guess icon names. Always check the reference guide.

## Connection Reference

For connection patterns, see:
- `guides/CONNECTION_PATTERNS.md` - Connection routing guide
- Template file "AWS Connection Patterns" tab - Pattern examples

## Spacing Reference

For layout and spacing, see:
- `guides/SPACING_LAYOUT.md` - Spacing standards and calculations

## Best Practices

1. **Always reference templates** - Don't start from scratch
2. **Copy, don't recreate** - Use template patterns
3. **Maintain consistency** - Keep style attributes identical
4. **Document changes** - Update comments when modifying
5. **Test thoroughly** - Verify icons and connections

## Version Control

Templates are versioned with the repository:
- Check git history for template changes
- Tag releases for stable template versions
- Document breaking changes in commit messages

## Contributing

To contribute templates:

1. Follow commenting standards
2. Test thoroughly in draw.io
3. Verify icons display correctly
4. Include example usage
5. Update this README if adding new templates

## Questions?

- See `guides/AI_AGENT_GUIDE.md` for comprehensive workflow
- Check individual template files for specific examples
- Reference guide files in `guides/` directory

