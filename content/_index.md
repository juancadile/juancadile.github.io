---
# Leave the homepage title empty to use the site title
title: ''
date: 2024-11-18
type: landing

design:
  # Default section spacing
  spacing: '6rem'

sections:
  - block: resume-biography-3
    content:
      # Choose a user profile to display (a folder name within `content/authors/`)
      username: admin
      text: ''
      # Show a call-to-action button under your biography? (optional)
      button:
        text: Download CV
        url: uploads/resume.pdf
      headings:
        about: ''
        education: ''
        interests: ''
    design:
      # Apply a gradient background
      css_class: hbx-bg-gradient
      # Avatar customization
      avatar:
        size: large # Options: small (150px), medium (200px, default), large (320px), xl (400px), xxl (500px)
        shape: circle # Options: circle (default), square, rounded
  - block: markdown
    content:
      title: '🤖 My Research'
      subtitle: ''
      text: |-
        I am a doctoral student at the University of Rochester working at the intersection of philosophy, ethics, and artificial intelligence. My research explores how AI systems interact with fundamental questions in virtue ethics, political philosophy, and epistemology.

        I'm particularly interested in bridging philosophical theory with technical AI governance and alignment research. My current projects examine how algorithmic architectures and institutional norms shape the moral trajectories of AI systems, and how we can design socio-technical institutions that promote human flourishing without imposing comprehensive doctrines.

        I'm always eager to collaborate with researchers working on AI ethics, alignment, and the philosophy of technology. Feel free to reach out!
    design:
      columns: '1'
  - block: collection
    id: papers
    content:
      title: Featured Publications & Presentations
      filters:
        folders:
          - publications
        featured_only: true
    design:
      view: article-grid
      columns: 2
  - block: collection
    content:
      title: Recent Publications & Presentations
      text: ''
      filters:
        folders:
          - publications
        exclude_featured: false
    design:
      view: citation
  - block: collection
    id: talks
    content:
      title: Recent & Upcoming Talks
      filters:
        folders:
          - events
    design:
      view: card
  - block: collection
    id: projects
    content:
      title: Projects
      subtitle: ''
      text: ''
      filters:
        folders:
          - projects
    design:
      view: card
      columns: 3
  - block: collection
    id: blog
    content:
      title: Recent Writing
      subtitle: ''
      text: ''
      # Page type to display. E.g. post, talk, publication...
      page_type: blog
      # Choose how many pages you would like to display (0 = all pages)
      count: 5
      # Filter on criteria
      filters:
        author: ''
        category: ''
        tag: ''
        exclude_featured: false
        exclude_future: false
        exclude_past: false
        publication_type: ''
      # Choose how many pages you would like to offset by
      offset: 0
      # Page order: descending (desc) or ascending (asc) date.
      order: desc
    design:
      # Choose a layout view
      view: card
      # Reduce spacing
      spacing:
        padding: [0, 0, 0, 0]
---
