# Claude Mobile MVP Skills

Claude Code skills for designing mobile MVPs in Figma, generating SwiftUI from Figma, and reviewing App Store readiness.

This plugin is useful when you want to move from an app idea to a practical MVP structure faster:

* create mobile app screens in Figma
* turn approved Figma screens into SwiftUI
* review MVP scope, differentiation, paywall placement, and App Store review risks

The skills are intentionally focused on **small, shippable mobile products**, not large design systems or enterprise apps.

---

## Included skills

### 1. `mobile-figma-designer`

Use this skill to create or improve mobile app interfaces in Figma.

Best for:

* onboarding
* home screens
* core feature flows
* empty states
* loading states
* error states
* paywalls
* settings
* lightweight design systems
* implementation-friendly mobile layouts

Example:

```text
/mobile-mvp-product:mobile-figma-designer

Create a mobile MVP design for an iOS app called HobbyLoop.

Core idea:
- User tracks hobbies and small personal projects
- User can set simple weekly goals
- User can log sessions, notes, photos, and progress milestones
- App sends lightweight reminders without feeling like a strict productivity tool

Create:
- onboarding
- home
- hobby detail
- session log
- progress screen
- reminders screen
- paywall
- settings
- empty/loading/error states

Use clean iOS-style UI, Auto Layout, reusable components, and clear layer names.
```

---

### 2. `swiftui-from-figma`

Use this skill after the Figma design is approved.

Best for:

* translating Figma frames into SwiftUI
* creating reusable SwiftUI components
* preserving spacing and hierarchy
* mapping design tokens to code
* building screens that are realistic to implement
* avoiding over-engineered UI code

Example:

```text
/mobile-mvp-product:swiftui-from-figma

Read the selected Figma frames and generate SwiftUI implementation for this MVP.

Use:
- SwiftUI
- iOS 16+
- reusable components
- MVVM-friendly structure
- clear file names
- preview data
- no unnecessary dependencies

Start with the home screen, hobby detail screen, and session log screen.
```

---

### 3. `appstore-mvp-review`

Use this skill before building too much or before submitting a mobile MVP.

Best for:

* MVP scope review
* differentiation ideas
* App Store review risk review
* clone / thin-app risk review
* paywall placement review
* deciding what must ship vs what can wait
* making the product feel more complete without overbuilding

Example:

```text
/mobile-mvp-product:appstore-mvp-review

Review this MVP for App Store readiness and product risk.

App: HobbyLoop

Features:
- create hobby profile
- set weekly goals
- log sessions
- add notes/photos
- track progress
- set reminders
- paywall after first hobby profile

Competitors:
- generic habit trackers
- reminder apps
- simple journaling apps

Goal:
Release a credible MVP without overbuilding.
```

---

## Installation

Add the plugin marketplace:

```text
/plugin marketplace add klionskiy/claude-mobile-mvp-skills
```

Install the plugin:

```text
/plugin install mobile-mvp-product@mobile-mvp-skills
```

Then use the skills from Claude Code:

```text
/mobile-mvp-product:mobile-figma-designer
/mobile-mvp-product:swiftui-from-figma
/mobile-mvp-product:appstore-mvp-review
```

---

## Requirements

For Figma-related workflows, configure Figma MCP in Claude Code first.

The skills are most useful when Claude Code can access:

* your Figma file or selected frame
* your product description
* your target platform
* your preferred architecture
* your visual references
* your implementation constraints

---

## Recommended workflow

### Step 1: Plan the MVP

Use `appstore-mvp-review` first if the product is still early.

It helps answer:

* is the MVP too small?
* is the idea differentiated enough?
* does it feel like a real app?
* is the paywall too aggressive?
* what should be built first?
* what can wait?

---

### Step 2: Create the Figma structure

Use `mobile-figma-designer` to create the first version of the design.

Recommended input:

```text
/mobile-mvp-product:mobile-figma-designer

Create a mobile MVP design for [app name].

Target platform: iOS
Audience: [target audience]
Core job: [what the app helps users do]

Main screens:
1. [screen]
2. [screen]
3. [screen]

Important constraints:
- [constraint]
- [constraint]

Use clean mobile UI, reusable components, Auto Layout, and implementation-friendly structure.
```

---

### Step 3: Review the design

Before writing code, ask Claude to review the Figma structure:

```text
/mobile-mvp-product:appstore-mvp-review

Review the current Figma MVP structure.

Focus on:
- missing core screens
- weak differentiation
- confusing UX
- paywall placement
- thin-app risk
- what should be simplified before development
```

---

### Step 4: Generate SwiftUI

After the design is approved, use `swiftui-from-figma`:

```text
/mobile-mvp-product:swiftui-from-figma

Generate SwiftUI code from the selected Figma frames.

Use:
- iOS 16+
- SwiftUI
- reusable components
- MVVM-friendly structure
- clear previews
- no unnecessary packages
```

---

## What this plugin is not

This plugin is not a replacement for a professional designer.

It is best for:

* founders
* indie developers
* mobile engineers
* early MVPs
* quick product validation
* design-to-code workflows

It helps create a practical first version that can be reviewed, improved, and implemented.

---

## Repository structure

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
│           │   └── SKILL.md
│           ├── swiftui-from-figma/
│           │   └── SKILL.md
│           └── appstore-mvp-review/
│               └── SKILL.md
├── examples/
├── LICENSE
└── README.md
```

---

## License

MIT
