# Portfolio Site

A JSON-driven showcase of my Claude Code projects. Single-page static site, no build step, no backend.

## How it works

- All content lives in `projects.json` — this is the only file to edit for content changes
- `index.html` is the template — only edit for design changes
- Screenshots go in `images/` — use 16:10 aspect ratio (1600×1000px), PNG or JPG

## Quick reference

- Read `PORTFOLIO-README.md` for the full JSON schema, example prompts, and hosting instructions
- Projects display in array order — best stuff first
- Effort scores 1-2 render green, 3 amber, 4-5 red (automatic)
- Value and usage scores always render green
- Meter tooltips are where the personality lives — keep them honest and wry

## Common tasks

- **Add a project**: add an object to the `projects` array in `projects.json`
- **Add a backlog idea**: add an object to the `backlog` array
- **Add a screenshot**: drop the image in `images/`, set the project's `image` field to the path
- **Move backlog → project**: remove from `backlog` array, add to `projects` array with full fields
- **Update site info**: edit the `site` object (email, updated date, etc.)

## Hosting

Static files only. Deploy to Netlify, Render, Vercel, or GitHub Pages. No build step needed.
