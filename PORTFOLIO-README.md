# Portfolio Site — Claude Code Handover

## File Structure

```
portfolio/
├── index.html        ← the template (don't touch unless changing design)
├── projects.json     ← ALL your content lives here (this is what you edit)
└── images/           ← drop screenshots here
    ├── investment-agent.png
    ├── health-tracker.png
    └── ...
```

## How It Works

`index.html` fetches `projects.json` at load time and renders everything from it. To update the site, you only ever edit `projects.json`. The HTML never needs to change unless you want a design tweak.

## Hosting

Drop both files (and the images folder) onto any static host:
- **Netlify**: drag the folder into netlify.com/drop
- **Render**: create a static site, point at a GitHub repo
- **GitHub Pages**: push to a repo, enable Pages in settings
- **Vercel**: `npx vercel` from the folder

No backend, no build step, no dependencies.

---

## Claude Code Prompts

### Adding a new project

```
Open projects.json. Add a new project to the projects array:
- name: "meal-planner"
- emoji: "🍽️"
- status: "active", statusLabel: "in progress"
- description: "Weekly meal plans based on dietary preferences, generates shopping lists, syncs with calendar"
- tags: ["python", "google calendar", "claude code"]
- effort: 2/5, tip: "a weekend project"
- value: 3/5, tip: "saves 30 mins a week"
- usage: 4/5, tip: "every sunday evening"
- image: "images/meal-planner.png" (or null if no screenshot yet)
- no link yet
```

### Updating an existing project

```
Open projects.json. Find the project "investment-agent" and:
- Change status to "live", statusLabel to "live trading"
- Update the description to mention it's now trading with real money
- Change value tip to "made its first real trade"
```

### Adding a screenshot

```
I've added a screenshot at images/health-tracker.png.
Open projects.json, find "health-tracker", and set
image to "images/health-tracker.png"
```

### Moving a backlog item to projects

```
Open projects.json. Move "Meeting prep agent" from the backlog
array into the projects array. Give it:
- status: "active", statusLabel: "in progress"
- effort 1/5 so far, value TBD, usage TBD
- emoji: "📋"
- tags: ["claude code", "mcp", "google calendar"]
Remove it from the backlog array.
```

### Adding a backlog idea

```
Open projects.json. Add to the backlog array:
- title: "Contract clause checker"
- description: "AI agent that reviews contracts against our standard terms and flags deviations"
- tag: "work"
```

### Removing a project

```
Open projects.json. Remove the project "agent-launcher"
from the projects array.
```

### Changing site info

```
Open projects.json. Update the site email to andy@andykeeley.com
and the updated date to "may 2026"
```

### Design changes (rare)

```
Open index.html. Change the card image area from 220px to 280px
to give screenshots more room.
```

---

## projects.json Schema Reference

```jsonc
{
  "site": {
    "title": "string",
    "tagline": "string",
    "name": "string",
    "role": "string",
    "email": "string",
    "github": "url",
    "updated": "string"           // e.g. "april 2026"
  },
  "intro": "string",              // the paragraph below the header
  "projects": [
    {
      "id": "string",             // unique slug
      "name": "string",           // display name (monospace)
      "emoji": "string",          // fallback when no image
      "status": "live|active|shipped",
      "statusLabel": "string",    // e.g. "live on Railway"
      "description": "string",
      "tags": ["string"],
      "effort": {
        "score": 1-5,             // 1-2 green, 3 amber, 4-5 red
        "tip": "string"           // hover tooltip
      },
      "value": {
        "score": 1-5,             // always green
        "tip": "string"
      },
      "usage": {
        "score": 1-5,             // always green
        "tip": "string"
      },
      "link": {                   // optional, null if none
        "label": "string",
        "url": "url"
      },
      "image": "string|null"      // path to screenshot, or null
    }
  ],
  "backlog": [
    {
      "title": "string",
      "description": "string",
      "tag": "work|personal"
    }
  ],
  "notes": [
    "string"                      // supports [text](url) markdown links
  ]
}
```

---

## Tips

- **Images**: Use 16:10 aspect ratio screenshots for best fit (e.g. 1600×1000px). PNG or JPG both work.
- **Order matters**: Projects display in the order they appear in the array. Put your best stuff first.
- **Meter tips**: These are the personality of the site. Keep them honest and wry — "half an afternoon", "genuinely can't work without it now", "served its purpose, archived".
- **Effort colour logic**: 1-2 blocks = green (quick wins), 3 = amber (decent effort), 4-5 = red (marathon). This is automatic based on the score.
