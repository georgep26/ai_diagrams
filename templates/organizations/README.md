# Organization-Specific Templates

This directory contains templates customized for specific organizations or companies.

## Purpose

Organization templates extend base templates with:
- Custom color schemes matching brand guidelines
- Organization-specific service patterns
- Custom styling and layout preferences
- Branded components and annotations

## Directory Structure

```
organizations/
├── README.md              # This file
└── example-org/           # Example organization
    └── custom-styles.drawio  # Custom styling template
```

## Creating Organization Templates

### Step 1: Create Organization Directory

Create a new directory for your organization:
```
organizations/your-org-name/
```

### Step 2: Copy Base Template

Start with a base template:
```bash
cp templates/base/aws-vpc-template.drawio organizations/your-org-name/custom-styles.drawio
```

### Step 3: Customize Colors

Modify color schemes to match organization branding:

**Color Overrides**:
- Update `fillColor` values in service icons
- Update `strokeColor` for containers
- Update `fontColor` for text

**Example**:
```xml
<!-- Base template uses: fillColor=#759C3E (green) -->
<!-- Organization uses: fillColor=#FF6B35 (custom orange) -->
<mxCell id="lambda" 
        style="...;fillColor=#FF6B35;..." 
        ...>
```

### Step 4: Add Organization Branding

Add organization-specific elements:
- Logo placeholders
- Custom annotations
- Branded color schemes
- Organization-specific patterns

### Step 5: Document Customizations

Add comments explaining:
- Why colors were changed
- What organization-specific elements were added
- How to use the template

## Example Organization Template

See `example-org/custom-styles.drawio` for a complete example.

## Template Inheritance

Organization templates inherit from base templates:

1. **Structure**: Inherit container hierarchy from base
2. **Layout**: Inherit spacing and positioning standards
3. **Icons**: Use same icon shapes (don't change)
4. **Connections**: Use same connection patterns
5. **Customize**: Only colors, branding, and styling

## Using Organization Templates

### For AI Agents

When generating diagrams for a specific organization:

1. **Check for org template**: Look in `organizations/[org-name]/`
2. **Use org template**: If exists, use organization template
3. **Fallback to base**: If not exists, use base templates
4. **Apply org colors**: Use organization color scheme
5. **Add org branding**: Include organization-specific elements

### For Human Users

1. **Select template**: Choose organization template if available
2. **Customize**: Modify as needed for your architecture
3. **Maintain branding**: Keep organization colors and styles
4. **Export**: Use for organization documentation

## Color Scheme Guidelines

### Standard AWS Colors

Base templates use AWS standard colors:
- Compute: `#759C3E` (Green)
- Storage: `#759C3E` (Green)
- Database: `#2E27AD` (Blue)
- Networking: `#8C4FFF` (Purple)
- Security: `#8C4FFF` (Purple)
- AI/ML: `#4D27AA` (Dark Purple)

### Organization Colors

When customizing:
- Keep contrast for readability
- Maintain color differentiation between service categories
- Follow organization brand guidelines
- Document color choices

## Best Practices

1. **Inherit structure** - Don't recreate base structure
2. **Customize minimally** - Only change what's necessary
3. **Document changes** - Explain why colors/styles changed
4. **Test thoroughly** - Verify icons and connections still work
5. **Maintain compatibility** - Keep structure compatible with base

## Template Naming

Use descriptive names:
- `custom-styles.drawio` - General styling template
- `branded-template.drawio` - Branded version
- `[org-name]-vpc-template.drawio` - Specific architecture

## Sharing Templates

To share organization templates:

1. **Create directory**: `organizations/[org-name]/`
2. **Add template**: Place template file(s)
3. **Document**: Add README if needed
4. **Test**: Verify template works
5. **Commit**: Add to repository

## Version Control

Organization templates follow same versioning:
- Track changes in git
- Tag releases for stable versions
- Document breaking changes

## Questions?

- See base templates for structure examples
- Check `templates/README.md` for general template usage
- Reference `guides/AI_AGENT_GUIDE.md` for AI agent workflow

