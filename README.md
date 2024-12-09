# Userware Documentation

This repository manages official documentation for Userware products.

## Structure
```
src/
└── docs/
  ├── General/
  │   ├── General.md  
  │   ├── Overview.md 
  │   └── Getting Started.md  
  └── Advanced/
      ├── Advanced.md   
      ├── features.md  
      └── migration.md  
```
## Documentation Structure

The documentation structure is managed in `docs.yml`:
```
product: OpenSilver
items:
 - title: General
   path: General.md
   type: Section
   items:
     - title: Overview
       path: Overview.md
       type: Item
     - title: Getting Started
       path: Getting Started.md
       type: Item
 - title: Advanced
   path: Advanced.md
   type: Section
   items:
     - title: Features
       path: features.md
       type: Item
     - title: Migration Guide
       path: migration.md
       type: Item
```
## Documentation Guide

### Adding New Documents
1. Create markdown file in appropriate section folder
2. Add entry to docs.yml
3. Write content

### Modifying Documents
1. Edit the .md file directly
2. Create PR

### Writing Guidelines
- Use clear titles
- Include brief descriptions
- Add example code when needed
- Include screenshots if necessary

## Build
Documentation is automatically built and deployed as a website.
