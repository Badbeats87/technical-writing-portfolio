# Technical Writing Portfolio - Setup Guide

This guide explains how to use this portfolio for job applications and how to host it on GitHub Pages.

## Quick Start

### Option 1: View Online (Recommended for Job Applications)

1. Create a GitHub repository:
   - Go to https://github.com/new
   - Create a public repository (e.g., `technical-writing-portfolio`)
   - Push this folder to that repository:
     ```bash
     git remote add origin https://github.com/YOUR-USERNAME/technical-writing-portfolio.git
     git branch -M main
     git push -u origin main
     ```

2. Enable GitHub Pages:
   - Go to your repository settings
   - Under "Code and automation" → "Pages"
   - Set "Source" to "Deploy from a branch"
   - Select "main" branch and "/root" folder
   - Click Save

3. Your portfolio will be live at: `https://YOUR-USERNAME.github.io/technical-writing-portfolio/`

### Option 2: View Locally

```bash
# Install Jekyll
gem install jekyll bundler

# Navigate to the portfolio directory
cd /path/to/Technical_Writing_Portfolio

# Build and serve
jekyll serve

# Visit http://localhost:4000 in your browser
```

### Option 3: Send Files for Applications

Include these files when sending applications:
- **README.md** - Overview of your portfolio
- **docs/index.html** - Your portfolio website (can be opened in any browser)
- **docs/featured.html** - Featured works page
- Individual documentation samples in the numbered folders (1_Instructional_Guides, etc.)

You can also create a single PDF by printing the HTML pages from your browser (File → Print → Save as PDF).

## Portfolio Structure

```
├── docs/                          # Website files
│   ├── index.html                # Main portfolio page
│   ├── featured.html             # Featured works showcase
│   └── styles.css                # Website styling
├── 1_Instructional_Guides/       # Step-by-step procedures
├── 2_Best_Practices/             # Scenario-based guidance
├── 3_Feature_Documentation/      # Complex feature explanations
├── 4_Reference_Material/         # Conceptual documentation
├── 5_Troubleshooting_and_Support/# Problem resolution guides
├── README.md                      # Portfolio overview
├── _config.yml                   # Jekyll configuration
└── .gitignore                    # Git ignore rules
```

## Content Recommendations for Job Applications

### Featured in Applications
- **Resolve Scheduling Errors** - Troubleshooting & problem resolution
- **Intraday Adherence** - Complex feature documentation
- **Integration Setup** - Technical configuration guidance

### When to Include Other Samples
- **Instructional Guides** - If applying for technical writer roles focused on procedures
- **Best Practices** - If applying for roles that need scenario-based guidance
- **Reference Material** - For roles requiring conceptual documentation

## Customization Tips

### Before Sending to Employers

1. **Update Contact Information**
   - Edit `docs/index.html` and add your email address
   - Update `_config.yml` with your actual email
   - Add LinkedIn/personal website links if desired

2. **Add Company Context (Optional)**
   - The portfolio is intentionally anonymized to respect NDAs
   - You can mention the application domain in interviews if asked
   - Consider adding notes about the technology stack used

3. **Create a PDF Version**
   - Open `docs/index.html` in a web browser
   - Use "Print" → "Save as PDF" to create a single-file version
   - Also create a PDF of featured.html for quick review

## Using with Job Applications

### Include in Applications As:
- A link to your hosted GitHub Pages site
- An attachment (ZIP of the docs/ folder)
- Individual sample documents from each category
- A PDF version for easier sharing

### In Your Cover Letter, Mention:
- The types of documentation you specialize in (procedures, feature docs, troubleshooting)
- The complexity level of systems you document (enterprise/workforce management)
- Your approach to making complex features accessible

## Troubleshooting

**GitHub Pages not showing?**
- Confirm the repository is public
- Check that "Deploy from a branch" is selected
- Wait 5 minutes for the site to build

**Local Jekyll not working?**
- Update Ruby: `ruby --version` (should be 2.7+)
- Install bundler: `gem install bundler`
- Install dependencies: `bundle install`

**Links broken in local version?**
- Use relative paths starting with ./
- Run with `jekyll serve` instead of opening HTML directly

## What's Included

✅ Sample documentation from multiple categories
✅ Professional website theme
✅ Mobile-responsive design
✅ Featured works showcase
✅ Easy-to-customize structure
✅ Ready for GitHub Pages deployment

## Next Steps

1. Set up GitHub Pages (see Option 1 above)
2. Customize contact information
3. Add your job application link to LinkedIn/resume
4. Send featured works samples with applications

---

For questions about specific documentation samples, see README.md
