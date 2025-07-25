---
layout: project
title: Record of a failed website [IT IS OKAY TO FAIL]
image: /assets/images/screenshot-2025-07-19-021656.png
---
And Failing we are

 Current Situation

* **Status**: Broken/Frankenstein setup - theme improperly installed over previous setup
* **Domain**: donhelios.com
* **Purpose**: Document infrastructure for complete rebuild
* **Theme Issues**: awesome-jekyll-theme improperly installed (cloned over incompatible theme)
* **Key Issue**: Site in `site/` subfolder but AWS S3 configured for root deployment (resolved by GitHub Actions)
* **Main Problem**: Theme not properly installed via Gemfile - was cloned instead

**Current Status**: The infrastructure and deployment pipeline are actually solid. The main issue is the improper theme installation method, which is why the site appears broken.

 Infrastructure Components

Infrastructure Stack

* **AWS S3 Bucket**: Static site hosting
* **AWS CloudFront Distribution**: CDN with custom SSL certificate
* **Porkbun**: DNS management for donhelios.com
* **AWS Certificate Manager**: for SSL Certificate
* **AWS Lambda**: Enable GitHub OAuth proxy for Decap CMS authentication
* **AWS API Gateway**: For triggering Lamba function
* **Repository**: GitHub repo where the Jekyll site + DecapCMS and Deployment code are stored
* **CMS**: Decap CMS integration
* **GitHub Actions**: For static site (with Jekyll) deployment
* **GitHub OAuth app**: Enables Decap CMS authentication via GitHub OAuth

 Additional Components

* **LigthSail**: WordPress instance for subdomain

 Documentation Index

* A bunch of links that actually show the only important stuff on this entry, but this is just a placeholder

 Key Insights

1. **✅ Deployment Structure is CORRECT**: The GitHub Actions workflow properly handles the `site/` subfolder by building to `_site/` at the repository root, then syncing to S3 root. This matches your AWS configuration.
2. **✅ Professional Workflow**: Your GitHub Actions workflow is sophisticated with:

   * OIDC authentication (more secure than access keys)
   * Build analytics and monitoring
   * S3 request usage tracking
   * CloudFront invalidation
   * Proper caching headers
3. **❌ Theme Installation Issue**: The real problem is the theme was cloned instead of properly installed as a gem, which is why it's "Frankenstein" setup.
4. **Jekyll Configuration**:

   * Uses `baseurl: ""` (correct for root deployment)
   * Built for "Solarium" theme
   * Has multilingual support configured but only uses English
   * Missing theme gem specification in Gemfile
