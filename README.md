# Claude Mobile MVP Skills

A small Claude Code plugin marketplace with three practical skills for building mobile app MVPs:

1. **mobile-figma-designer** — create clean, editable mobile MVP interfaces in Figma using Figma MCP.
2. **swiftui-from-figma** — convert approved Figma mobile screens into SwiftUI code.
3. **appstore-mvp-review** — review MVP scope, differentiation, thin-wrapper risk, and App Store readiness.

The skills are designed for indie developers, iOS developers, and product builders who want to move from idea → Figma → SwiftUI → release faster.

---

## What this repository contains

```text
claude-mobile-mvp-skills/
├── .claude-plugin/
│   └── marketplace.json
├── plugins/
│   └── mobile-mvp-product/
│       ├── .claude-plugin/
│       │   └── plugin.json
│       └── skills/
│           ├── mobile-figma-designer/
│           │   ├── SKILL.md
│           │   └── references/
│           ├── swiftui-from-figma/
│           │   ├── SKILL.md
│           │   └── references/
│           └── appstore-mvp-review/
│               ├── SKILL.md
│               └── references/
├── examples/
├── LICENSE
└── README.md
```

This repo is both:

- a **Claude Code plugin marketplace** via `.claude-plugin/marketplace.json`
- a **plugin package** via `plugins/mobile-mvp-product/`

---

## Requirements

- Claude Code installed and authenticated
- Figma MCP configured if you want Claude to read/write Figma files
- An iOS project if you want to use the SwiftUI implementation skill

---

## Install locally for testing

Clone the repository:

```bash
git clone https://github.com/klionskiy/claude-mobile-mvp-skills.git
cd claude-mobile-mvp-skills
```

Open Claude Code from any project and add the local marketplace:

```text
/plugin marketplace add /absolute/path/to/claude-mobile-mvp-skills
```

Install the plugin:

```text
/plugin install mobile-mvp-product@mobile-mvp-skills
```

Reload plugins if needed:

```text
/reload-plugins
```

Use the skills:

```text
/mobile-mvp-product:mobile-figma-designer
/mobile-mvp-product:swiftui-from-figma
/mobile-mvp-product:appstore-mvp-review
```

---

## Install from GitHub

After this repo is public, users can add the marketplace directly from GitHub:

```text
/plugin marketplace add klionskiy/claude-mobile-mvp-skills
```

Then install the plugin:

```text
/plugin install mobile-mvp-product@mobile-mvp-skills
```

Use it:

```text
/mobile-mvp-product:mobile-figma-designer
```

---

## Skill 1: mobile-figma-designer

Use this when you want Claude to create or improve mobile app screens in Figma.

Example:

```text
/mobile-mvp-product:mobile-figma-designer

Using this Figma file: <FIGMA_FILE_URL>
Create iOS MVP screens for an AI Plant Care app.
Include onboarding, home, add plant, AI result, care plan, paywall, settings, and edge states.
Use auto layout, reusable components, and clear layer names.
```

Best for:

- MVP wireframes
- clean first visual direction
- onboarding flows
- paywalls
- empty/error/loading states
- design systems for small apps
- competitor-inspired but non-clone UI

---

## Skill 2: swiftui-from-figma

Use this after a Figma screen is approved and you want Claude to implement it in SwiftUI.

Example:

```text
/mobile-mvp-product:swiftui-from-figma

Using this Figma frame: <FIGMA_FRAME_URL>
Implement the Home screen in SwiftUI.
Follow the existing project architecture, reuse existing colors/components, add previews, and include loading, empty, and error states.
```

Best for:

- SwiftUI screen implementation
- mapping Figma components to SwiftUI views
- creating previews with mock data
- keeping design and code aligned
- preserving your existing architecture

---

## Skill 3: appstore-mvp-review

Use this before building too much or submitting to App Store review.

Example:

```text
/mobile-mvp-product:appstore-mvp-review

Review this MVP for App Store readiness and thin-wrapper risk.
App: AI Plant Care
Features: scan plant, identify plant, create care plan, reminders, diagnose issues, recovery timeline, paywall after first plan.
Competitors: Planta, PictureThis, PlantIn.
Goal: release a credible MVP without overbuilding.
```

Best for:

- MVP scope review
- differentiation ideas
- App Store 4.3-style clone/thin app risk review
- paywall placement review
- deciding what must ship vs what can wait

---

## Figma MCP setup note

This plugin does not install Figma MCP by itself. It only gives Claude better behavior when Figma MCP is available.

A typical Claude Code setup uses Figma's MCP server/plugin connection, then you pass a Figma file or frame URL to Claude. Once connected, the `mobile-figma-designer` skill tells Claude how to inspect and write useful mobile UI structure instead of producing generic design descriptions.

---

## How to make this repository public and nice to use

### 1. Create the GitHub repo

Create a new public GitHub repository named:

```text
claude-mobile-mvp-skills
```

Recommended visibility: **Public**

Recommended topics:

```text
claude-code, claude-skills, figma, figma-mcp, swiftui, ios, mobile-app, app-store, mvp, product-design
```

### 2. Push the files

From the repository folder:

```bash
git init
git add .
git commit -m "Initial mobile MVP Claude Code skills"
git branch -M main
git remote add origin https://github.com/klionskiy/claude-mobile-mvp-skills.git
git push -u origin main
```

### 3. Create a release

In GitHub:

1. Go to **Releases**
2. Click **Draft a new release**
3. Tag: `v1.0.0`
4. Title: `v1.0.0 — Initial release`
5. Notes:

```md
Initial release with three Claude Code skills:
- mobile-figma-designer
- swiftui-from-figma
- appstore-mvp-review
```

### 4. Improve trust

Add to the repo description:

```text
Claude Code skills for designing mobile MVPs in Figma, implementing SwiftUI screens, and reviewing App Store readiness.
```

Pin the repo on your GitHub profile if you want people to discover it.

### 5. Keep versions clean

When you edit skills later:

1. Update the skill text
2. Bump `version` in:
   - `.claude-plugin/marketplace.json`
   - `plugins/mobile-mvp-product/.claude-plugin/plugin.json`
3. Commit with a clear message
4. Create a new GitHub release, for example `v1.1.0`

---

## Suggested workflow

```text
Idea / reference apps
        ↓
/mobile-mvp-product:appstore-mvp-review
        ↓
/mobile-mvp-product:mobile-figma-designer
        ↓
Manual Figma review / polish
        ↓
/mobile-mvp-product:swiftui-from-figma
        ↓
Build, test, submit
```

---

## Contributing

Pull requests are welcome.

Good contributions:

- better trigger descriptions
- more mobile design patterns
- SwiftUI architecture mapping examples
- App Store review checklist improvements
- example prompts for real MVP categories

Avoid adding executable scripts unless they are clearly necessary and safe.

---

## License

MIT
