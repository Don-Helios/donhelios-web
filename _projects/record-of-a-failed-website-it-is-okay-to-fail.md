---
layout: project
title: Record of a failed website [IT IS OKAY TO FAIL]
image: /assets/images/screenshot-2025-07-19-021656.png
---
# Initial Assessment and Path Forward

**Problem Identified**: Theme was cloned instead of properly installed as a gem, creating a "Frankenstein" setup.

**Decision Made**: Clean up current repo and install the awesome-jekyll-theme as a gem following the "Advanced Installation" method from the theme's README.

**Rationale**: 
- Keep existing AWS S3/CloudFront/Decap CMS integration
- Avoid unnecessary GitHub Pages files and settings  
- Maintain full control over deployment pipeline
- Proper gem-based installation for cleaner maintenance

**Planned Approach**:
1. Clean up current repo (remove old theme files, keep content and config)
2. Install theme as a gem (update `Gemfile` and `_config.yml`)
3. Test locally in WSL environment
4. Deploy to S3 as usual

## Summary of Changes Made

### **Infrastructure Changes**
- Migrated from "Frankenstein" theme installation to proper gem-based setup
- Restructured repository from `site/` subfolder to root-level organization
- Updated deployment workflow to build from repository root

### **Configuration Updates**
- **Gemfile**: Added `awesome-jekyll-theme` gem, removed conflicting themes
- **_config.yml**: Set proper theme configuration and site metadata
- **admin/config.yml**: Updated all folder paths to match new structure
- **.gitattributes**: Enforced LF line endings for Markdown files

### **Content Migration and Creation**
- Converted all `.markdown` files to `.md` for CMS consistency
- Created missing page files (`blog.md`, `projects.md`)
- Enhanced homepage with proper front matter and personalized content
- Fixed image paths from relative to absolute for cross-page compatibility

### **Theme Customizations**
- **Strategic file copying**: Only copied theme files that needed customization
- **String localization**: Fixed missing theme string keys
- **Contact channels**: Removed unwanted GitHub icons
- **Footer**: Removed attribution text, added personalized content

### **Bug Fixes**
- **Line endings issue**: Identified and resolved CRLF/LF problem affecting excerpt display
- **Path inconsistencies**: Fixed all file and folder references
- **CMS integration**: Aligned DecapCMS configuration with new structure

---

## Files Modified

### **Root Level**
- `Gemfile` - Added theme gem
- `_config.yml` - Theme and site configuration
- `.gitattributes` - Line ending enforcement
- `index.md` - Homepage enhancement
- `blog.md` - Created new
- `projects.md` - Created new

### **Admin/CMS**
- `admin/config.yml` - Updated all folder paths

### **Theme Customizations**
- `_data/en/strings.yml` - Fixed missing localization strings
- `_includes/contact_channels.html` - Removed GitHub section
- `_includes/footer.html` - Removed attribution, added personalization

### **Content**
- All `.markdown` → `.md` conversions
- Multiple project files with line ending fixes
