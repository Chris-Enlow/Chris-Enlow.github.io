# Copilot Instructions for Christopher Enlow Portfolio

## Project Overview
A personal portfolio website showcasing professional background, skills, and projects. Static site with three pages (index, projects, contact) sharing consistent header/nav/footer structure.

## Architecture

### Page Structure
- **[index.html](../index.html)**: About me, skills, coursework sections
- **[projects.html](../projects.html)**: Detailed project showcase with images and links
- **[contact.html](../contact.html)**: Contact information with social links and Font Awesome icons

### Shared Components
- **Header**: Consistent `<header>` across all pages with fade-in animations (0s, 0.3s, 0.6s delays)
- **Navigation**: Three-link nav with hover effects (About, Projects, Contact)
- **Footer**: Copyright notice with dark background
- **Layout**: Centered main content max-width (1200-1400px) with 80% container width

## Style Conventions

### CSS Structure
- **Single consolidated stylesheet**: `styles.css` contains all page styles to eliminate duplication
- **Color scheme**: White text on dark headers, dark text on white main content, #333 dark gray accents
- **Responsive sizing**: Uses `clamp()` for fluid scaling (e.g., font-size: clamp(1.3rem, 2.5vw, 1.75rem))
- **Animations**: 
  - `fadeInLeft` keyframe: 0.8s ease-out animation with 30px translateX (used on header elements)
  - Hover transitions: 0.3s smooth color/background changes on nav links
- **Responsive breakpoints**: 768px (tablets), 480px (mobile)

### Layout Patterns
- **Background**: Full-bleed background image (images/background.jfif) on all pages
- **Main container**: White rounded background (border-radius: 30px)
- **Cards**: Projects use gradient backgrounds (135deg, #2c3e50, #34495e) with box-shadow hover lift effects
- **Responsive images**: Use float:right with vw units for viewport scaling

## Key Files & Their Purpose

| File | Purpose |
|------|---------|
| [styles.css](../styles.css) | Consolidated stylesheet with all shared and page-specific styles |
| [index.html](../index.html) | Bio, skills list, coursework timeline |
| [projects.html](../projects.html) | Portfolio showcase with project cards, images, GitHub links |
| [contact.html](../contact.html) | Email and social media links (LinkedIn, GitHub) |
| [images/](../images/) | Background image, portfolio screenshots, favicon |

## External Dependencies
- **Font Awesome 6.5.2**: CDN link in [contact.html](../contact.html#L7) for social icons (LinkedIn, GitHub, envelope)
- **System Fonts**: Garamond for headers, Arial for body

## Development Workflow

### Adding Content
1. Maintain header/nav/footer consistency across pages
2. Match animation delays: h1 (0s), subtitle (0.3s), nav (0.6s)
3. Use relative paths for internal links (e.g., `href="index.html"`)

### Adding Projects
- Insert new `.project` div in [projects.html](../projects.html) with `.project-content` wrapper
- Include `.project-header` with title, tech stack, and `.project-img`
- Add structured feature list with `<ul><li>` elements
- Include GitHub link with `target="_blank"`

### Styling Guidelines
- Dark text on light backgrounds, white text on dark backgrounds
- Use 0.3s transitions for interactive elements
- Mobile-first responsive approach with viewport meta tags
- Maintain border-radius: 5px for buttons, 15px for cards, 30px for main container

## Common Patterns to Replicate

### Navigation Links
```html
<nav class="fade-in-element" style="animation-delay: 0.6s;">
  <a href="index.html">About</a>
  <a href="projects.html">Projects</a>
  <a href="contact.html">Contact</a>
</nav>
```

### Project Card
```html
<div class="project">
  <div class="project-content">
    <div class="project-header">
      <div>
        <h3>Project Title</h3>
        <p style="font-size: 1rem; color: #95a5a6;">Tech Stack</p>
      </div>
      <img src="images/project.jpg" alt="Description">
    </div>
    <p>Description</p>
    <a href="https://github.com/..." target="_blank">View Project</a>
  </div>
</div>
```

## Notes for AI Agents
- Portfolio content is in English; maintain professional tone
- All images reference local files in `images/` directory (e.g., `images/DQN_picture.jpg`, `images/stock_market_image.jpg`, `images/restaurant_reward.png`, `images/minesweeper.png`, `images/background.jfif`, `images/self-portrait.jpg`, `images/favicon.png`)
- Resume PDF (`My Resume.pdf`) is in the root directory and linked for download
- External URLs use HTTPS (LinkedIn, GitHub, Font Awesome CDN)
- Test navigation on all pages after adding/removing sections
- Maintain consistent spacing: 20px header padding, 30-40px section padding
