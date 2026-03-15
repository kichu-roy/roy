# Kishore B - DevOps Engineer Resume Website

A modern, responsive, single-page resume website built with HTML and CSS, deployed using GitHub Pages with GitHub Actions CI/CD automation.

## 🌐 Live Website

Your resume is live at: **[https://kichu-roy.github.io/roy/](https://kichu-roy.github.io/roy/)**

## 📋 Features

- **Responsive Design**: Works seamlessly on desktop, tablet, and mobile devices
- **Modern Styling**: Professional gradient backgrounds, smooth animations, and clean typography
- **Visual Elements**: Icons, color-coded sections, and hover effects for better UX
- **GitHub Integration**: Direct links to GitHub repository and profile
- **Print-Friendly**: Can be printed or saved as PDF from the browser
- **Dark Mode Compatible**: Adapts to system preferences
- **Fast Loading**: Pure HTML/CSS, no external dependencies
- **SEO Optimized**: Meta tags for better search engine visibility
- **GitHub Pages**: Free hosting directly from your repository
- **Automated Deployment**: GitHub Actions automatically deploys changes

## 📁 Project Structure

```
roy/
├── index.html                      # Main resume website (HTML + CSS)
├── Kishore_Devops_Resume.html      # Original resume file (backup)
├── README.md                       # This file
├── .github/
│   └── workflows/
│       └── deploy.yml              # GitHub Actions workflow
└── Kishore_Devops_Resume_files/    # Supporting files directory
```

## 🚀 Quick Start

### 1. **Clone or Download the Repository**

```bash
git clone https://github.com/kichu-roy/roy.git
cd roy
```

### 2. **View Locally**

Simply open `index.html` in your web browser:

- Right-click on `index.html` → Open with → Browser
- Or use a local server:

  ```bash
  # Python 3
  python -m http.server 8000

  # Python 2
  python -m SimpleHTTPServer 8000

  # Node.js (with http-server)
  npx http-server
  ```

Then visit `http://localhost:8000` in your browser.

### 3. **View on GitHub Pages**

Your site is automatically deployed at: `https://kichu-roy.github.io/roy/`

## 🔧 Customization Guide

### Edit Your Information

Open `index.html` and update these sections:

#### Header Section

```html
<h1>Your Name</h1>
<p class="title">Your Title</p>
<div class="contact-info">
  <!-- Update phone, email, location, LinkedIn -->
</div>
```

#### Profile Summary

```html
<div class="profile-summary">
  <p>Your professional summary here...</p>
</div>
```

#### Experience

```html
<div class="job">
  <div class="job-header">
    <div>
      <div class="company">Company Name</div>
      <div class="job-title">Your Job Title</div>
      <div class="job-location">Location</div>
    </div>
    <div class="job-date">Start – End</div>
  </div>
  <div class="job-description">
    <ul>
      <li>Your achievement here</li>
    </ul>
  </div>
</div>
```

#### Skills

```html
<div class="skill-category">
  <h3>Category Name</h3>
  <div class="skills-list">
    <span class="skill-tag">Skill 1</span>
    <span class="skill-tag">Skill 2</span>
  </div>
</div>
```

#### Education

```html
<div class="education-item">
  <div class="degree">Your Degree</div>
  <div class="institution">Institution Name</div>
  <div class="education-details">Year – Year | CGPA: X.X</div>
</div>
```

### Customize Colors

Edit the color variables at the top of the CSS in `<style>`:

```css
:root {
  --primary-color: #2c3e50; /* Main color */
  --secondary-color: #3498db; /* Accent color */
  --accent-color: #e74c3c; /* Highlight color */
  --light-bg: #ecf0f1; /* Background color */
  --text-color: #2c3e50; /* Text color */
}
```

### Change Fonts

Modify the font-family in the `body` CSS:

```css
body {
  font-family: "Your Font", sans-serif;
}
```

## 🔄 GitHub Actions Workflow

The `.github/workflows/deploy.yml` file automatically:

1. **Triggers on**: Push to `main` or `resume` branch
2. **Checks out**: Your repository code
3. **Configures**: GitHub Pages environment
4. **Uploads**: All files as deployment artifact
5. **Deploys**: To your GitHub Pages site

### How It Works

```
You push changes to GitHub
    ↓
GitHub Actions workflow triggers automatically
    ↓
Builds and validates your site
    ↓
Deploys to GitHub Pages
    ↓
Changes go live in seconds!
```

## 📝 Making Changes

1. **Edit `index.html`** with your information
2. **Save the file**
3. **Commit and push** to GitHub:
   ```bash
   git add index.html
   git commit -m "Update resume information"
   git push origin main
   ```
4. **Automatic deployment** happens in seconds!
5. **View your changes** at: `https://kichu-roy.github.io/roy/`

## 🎨 Styling Features

### Responsive Breakpoints

- Desktop: Full layout
- Tablet (≤768px): Adjusted spacing
- Mobile (≤480px): Single column layout

### Interactive Elements

- Hover effects on skill tags
- Smooth color transitions
- Animated section appearance
- Print-friendly styles

### Dark Mode

The design uses relative colors that adapt to system dark mode preferences.

## 📱 Mobile Optimization

The site is fully responsive with:

- Flexible grid layouts
- Mobile-friendly font sizes
- Touch-friendly interactive elements
- Optimized spacing for small screens

## 🖨️ Print to PDF

1. Open the website in your browser
2. Press `Ctrl+P` (Windows) or `Cmd+P` (Mac)
3. Select "Save as PDF"
4. Choose format and download

## 🔐 GitHub Pages Settings

Your repository should have GitHub Pages enabled:

1. Go to **Settings** → **Pages**
2. Select **Deploy from a branch**
3. Choose branch: **main** (or your deployment branch)
4. Choose folder: **/ (root)**
5. Click **Save**

Your site will be live at: `https://username.github.io/repo-name/`

## 🐛 Troubleshooting

### Site Not Updating

- Clear browser cache (Ctrl+Shift+Delete)
- Wait 1-2 minutes for deployment
- Check GitHub Actions tab for errors

### GitHub Actions Failing

- Go to **Actions** tab in your repository
- Click on the failed workflow
- Check the build logs for errors
- Common issues: HTML syntax errors, missing files

### Site Not Loading

- Check repository visibility is **Public**
- Verify GitHub Pages is enabled in Settings
- Check that `index.html` exists in repository root

## 📚 Additional Resources

- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [HTML & CSS Learning](https://developer.mozilla.org/en-US/docs/Web/HTML)
- [GitHub Markdown Guide](https://guides.github.com/features/mastering-markdown/)

## 🎯 Best Practices

1. **Keep it Updated**: Update your resume regularly
2. **Test Locally**: Preview changes before pushing
3. **Commit Messages**: Use clear, descriptive commit messages
4. **Backup**: Keep a copy of your original resume
5. **Mobile First**: Always test on mobile devices

## 📊 Statistics

- **Load Time**: < 1 second
- **Page Size**: ~35 KB
- **Dependencies**: None (pure HTML/CSS)
- **Browser Support**: All modern browsers
- **Accessibility**: WCAG 2.1 compatible

## 📧 Contact Information

- **Email**: [rkishore480@gmail.com](mailto:rkishore480@gmail.com)
- **Phone**: +91-9966373654
- **Location**: Andhra Pradesh, India
- **LinkedIn**: [Kishore Roy](https://www.linkedin.com/in/rajaputrakishore/)
- **GitHub**: [@kichu-roy](https://github.com/kichu-roy)

## 📄 License

This project is free to use and customize. You can modify and distribute it as needed.

---

**Last Updated**: March 2026
**Built with**: HTML5, CSS3, GitHub Pages, GitHub Actions
