# Draw.io Templates for AWS Architecture Diagrams

This directory contains template files for generating professional AWS architecture diagrams in draw.io format.

## Directory Structure

```
templates/
├── base/                          # Base templates (start here)
│   ├── aws-vpc-template.drawio   # VPC structure and layout
│   └── aws-connection-patterns.drawio  # Connection routing patterns
├── organizations/                 # Organization-specific templates
│   ├── README.md                  # Organization template guide
│   └── example-org/               # Example organization
│       └── custom-styles.drawio   # Custom styling example
└── README.md                      # This file
```

## Base Templates

### aws-vpc-template.drawio

**Purpose**: Foundational template for AWS VPC architecture diagrams.

**Contains**:
- Complete VPC container structure
- Public and private subnet examples
- Internet Gateway and NAT Gateway placement
- Example service placements (Lambda, RDS)
- Extensive XML comments explaining each component

**Usage**:
1. Copy the container hierarchy structure
2. Modify subnet positions and sizes as needed
3. Add your services using the example patterns
4. Maintain the parent-child relationships

**Key Features**:
- Proper icon shape references
- Correct spacing calculations
- Standard AWS color codes
- Grid-based positioning

### aws-connection-patterns.drawio

**Purpose**: Connection routing patterns for AWS services.

**Contains**:
- User → API Gateway → Lambda pattern
- S3 event trigger pattern
- Lambda → RDS database pattern
- Multi-point routing examples
- Dashed line patterns (replication, monitoring)
- Cross-container connections

**Usage**:
1. Copy connection patterns that match your architecture
2. Modify source and target component IDs
3. Adjust exit/entry points for your layout
4. Add waypoints for complex routing

**Key Features**:
- Right-angle routing (no diagonals)
- Proper exit/entry point calculations
- Labeled connections with action verbs
- Appropriate line styles (solid vs dashed)

## Template Commenting Standards

All templates include extensive XML comments:

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

1. **Read first**: Always read the template file before generating diagrams
2. **Copy structure**: Copy the container hierarchy
3. **Copy patterns**: Copy icon and connection patterns
4. **Modify carefully**: Change only IDs, labels, and positions
5. **Maintain style**: Keep all style attributes identical

### For Human Users

1. **Open in draw.io**: Import the template file
2. **Customize**: Modify components as needed
3. **Maintain structure**: Keep container hierarchy intact
4. **Follow comments**: Read XML comments for guidance

## Template Customization

### Modifying Base Templates

When customizing templates:

1. **Keep structure**: Maintain container hierarchy
2. **Keep styles**: Don't change style attributes unnecessarily
3. **Update comments**: Update comments if you change structure
4. **Test icons**: Verify icons display correctly
5. **Test connections**: Verify connections route correctly

### Creating New Templates

To create a new template:

1. **Start with base**: Copy from `aws-vpc-template.drawio`
2. **Add your components**: Add services specific to your architecture
3. **Add comments**: Document every component extensively
4. **Test thoroughly**: Verify icons and connections work
5. **Share**: Add to appropriate directory

## Icon Reference

For icon shape names, see:
- `guides/ICON_REFERENCE.md` - Complete icon reference

Never guess icon names. Always check the reference guide.

## Connection Reference

For connection patterns, see:
- `guides/CONNECTION_PATTERNS.md` - Connection routing guide
- `templates/base/aws-connection-patterns.drawio` - Pattern examples

## Spacing Reference

For layout and spacing, see:
- `guides/SPACING_LAYOUT.md` - Spacing standards and calculations

## Organization Templates

Organization-specific templates extend base templates with:
- Custom color schemes
- Organization branding
- Specific service patterns
- Custom styling

See `organizations/README.md` for details.

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

