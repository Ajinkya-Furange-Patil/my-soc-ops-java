Goal:
Replace generic design behavior with scalable, maintainable, production-ready frontend standards used in real companies.

Include these sections in clean markdown format:

---
name: frontend-enterprise
description: Use this skill when building scalable, maintainable, accessible, and production-grade frontend UI for Python/Jinja2 applications.
---

# Frontend Engineering Standards

## 1. Architecture
- Prefer reusable components and partial templates
- Keep UI split into sections/components
- Use clear naming conventions
- Avoid duplicated HTML/CSS
- Use template inheritance for layouts

## 2. Design System
- Define CSS variables in :root for:
  colors, spacing, radius, shadows, typography
- Use consistent spacing scale
- Use standard button/input/card variants
- Keep visual consistency across all pages

## 3. Responsive Design
- Mobile first approach
- Support desktop, tablet, mobile
- Flexible grids and containers
- Avoid fixed widths unless necessary

## 4. Accessibility
- Semantic HTML
- aria-label where needed
- keyboard navigable UI
- proper contrast ratio
- visible focus states

## 5. Performance
- Minimal DOM complexity
- Reuse CSS utilities
- Avoid unnecessary animations
- Lazy load heavy assets
- Optimize images/fonts

## 6. Maintainability
- Keep CSS modular and readable
- Prefer utility classes + component classes
- Avoid inline styles
- Comment complex logic only
- Use predictable folder structure

## 7. UX Standards
- Clear loading states
- Error states
- Empty states
- Success feedback
- Smooth transitions with purpose only

## 8. Security Awareness
- Escape unsafe output in templates
- Never trust raw user HTML
- Sanitize dynamic content

## 9. AI Design Behavior
Avoid:
- random flashy gradients
- cluttered layouts
- inconsistent spacing
- oversized headings
- trendy but impractical UI

Prefer:
- clean SaaS style
- dashboard quality polish
- premium enterprise interfaces
- clear hierarchy
- practical elegance

## 10. Output Rules
Whenever generating UI:
- Explain component structure first
- Then generate production-ready code
- Keep code modular
- Match current project CSS system
- Think like senior frontend engineer

Also compare this new file against existing frontend-design.instructions.md and mention what improvements were added.

After creating the file, ask if I want to activate it for future Copilot tasks.