# GitHub Copilot Custom Instructions for Diagram Generation

## Diagram Generation Guidelines

When generating draw.io diagrams for this repository, always follow the comprehensive workflow and guidelines in `guides/AI_AGENT_GUIDE.md`.

### Key Requirements

- **Reference Document**: Follow the complete workflow outlined in `guides/AI_AGENT_GUIDE.md`
- **Template System**: Reference templates in `templates/base/AWS_diagram_design_patterns.drawio`
- **Component Outlines**: Create a text-only component outline first before generating XML
- **Icon Names**: Always check `guides/ICON_REFERENCE.md` for correct icon shape names (never guess)
- **Layout Standards**: Follow spacing, connection, and layout standards from `guides/SPACING_LAYOUT.md`
- **Connection Patterns**: Use right-angle routing patterns from `guides/CONNECTION_PATTERNS.md`
- **Logical Paths**: Include logical paths textbox and numbered badges as specified in the guide

### Critical Rules

- ❌ Never guess icon shape names - always check ICON_REFERENCE.md
- ❌ Never use uppercase icon names - all icon names are lowercase
- ❌ Never use diagonal connections - always use right-angle routing
- ❌ Never use custom icon sizes - always use 78x78 for AWS icons
- ✅ Always include `aspect=fixed` in icon styles
- ✅ Always label connections with action verbs
- ✅ Always align positions to 10px grid
- ✅ Always nest services inside appropriate groups/containers
- ✅ Always include white stroke (`strokeColor=#ffffff`) for AWS service icons

### Workflow

1. Read `guides/AI_AGENT_GUIDE.md` for complete workflow
2. Reference template system and guides
3. Create component outline (containers, services, connections)
4. Look up icon names in `guides/ICON_REFERENCE.md`
5. Copy template structures from `templates/base/AWS_diagram_design_patterns.drawio`
6. Calculate positions using spacing formulas
7. Add connections with proper routing
8. Add logical paths textbox and numbered badges
9. Verify using checklist in AI_AGENT_GUIDE.md

