# Design Notes & Architecture

This document outlines the design decisions, color palette, typography choices, and dynamic integrations used in the **Akulbanxal** GitHub Profile README.

---

## 🎨 Design System

### Color Palette

| Component | Hex Code | Visual Sample | Usage & Rationale |
| :--- | :--- | :--- | :--- |
| **Primary (Obsidian)** | `#0B0F19` | `█` (Dark Slate) | Base color for generated SVGs and banners. Keeps a premium, dark-mode-first aesthetic. |
| **Accent (Cyber Green)** | `#00E676` | `█` (Bright Green) | Highlights key achievements, languages, and security firewalls. Symbolizes system health. |
| **Secondary (Electric Teal)** | `#00E5FF` | `█` (Teal/Cyan) | Symbolizes network nodes, database pathways, and modern Web2/Web3 technologies. |
| **Neutral Primary (Platinum)** | `#E2E8F0` | `█` (Off-White) | High-contrast text color for optimal readability in dark mode without glare. |
| **Neutral Muted (Slate)** | `#94A3B8` | `█` (Muted Slate) | Secondary text, borders, and sub-labels. |

*Note: The palette avoids pure black (`#000000`) and pure white (`#FFFFFF`) to ensure the profile renders beautifully on both GitHub Dark and GitHub Light themes.*

### Typography & Fonts
* **Primary Font**: `Inter` and `Outfit` via Google Fonts.
* **Secondary Font**: `Fira Code` (monospace) for technical stats and labels.
* **Rationale**: Sans-serif headings convey a clean, professional, and modern corporate aesthetic suitable for tech recruiters, while monospace elements underscore your focus on algorithmic precision and engineering.

### Visual Motif
* **Glassmorphic Cyber-Security Grid**: Semi-transparent card overlays, soft cyan/green glow effects, and modern grid lines representing problem-solving and structured systems.

---

## 📐 Section Layout & Skim Rationale

The average recruiter skims a GitHub profile in **6 seconds**. The content is optimized chronologically to answer three quick questions:
1. **Who is this? (0-2s)**: Hero Banner + dynamic titles + brief 3-line intro.
2. **What can they build? (2-4s)**: Categorized tech stack & 4 key featured projects with clear descriptions.
3. **What is their impact & activity? (4-6s)**: Side-by-side stats cards, top languages, and live contribution graphs.

---

## 🔗 Integrated Services

This README integrates several dynamic badge and stats services:
1. **Capsule Render** (Banner Generation) - [GitHub Repo](https://github.com/kyechan99/capsule-render)
2. **Readme Typing SVG** (Animated Headings) - [GitHub Repo](https://github.com/denvercoder1/readme-typing-svg)
3. **GitHub Readme Stats** (Stats & Top Languages) - [GitHub Repo](https://github.com/anuraghazra/github-readme-stats)
4. **GitHub Readme Streak Stats** (Contribution Streak) - [GitHub Repo](https://github.com/DenverCoder1/github-readme-streak-stats)
5. **Skill Icons** (Unified Stack Badges) - [GitHub Repo](https://github.com/tandpfun/skill-icons)
6. **Shields.io** (Social Badges & Technical Indicators) - [Official Site](https://shields.io)

> [!WARNING]
> **GitHub Readme Stats Rate Limiting**: Anurag Hazra's hosted service can occasionally encounter rate limits due to high traffic. If stats cards fail to load, we recommend self-hosting on Vercel. See the *Future Improvements* section.

---

## 🚀 Future Improvements (Next Steps)

To take this profile README to an elite level, consider implementing these 5 automation enhancements:

### 1. Self-Host GitHub Readme Stats on Vercel
Deploy your own instance of `github-readme-stats` to avoid public rate-limit issues.
* **Steps**: Fork [github-readme-stats](https://github.com/anuraghazra/github-readme-stats), click "Deploy to Vercel", add your personal GitHub Access Token (`PAT`), and update the image URLs in your README.

### 2. Auto-Generating Contribution Snake
Add an animated 3D snake eating your contribution graph.
* **Workflow**: Setup a GitHub Action using `Platane/snk` that outputs a snake animation SVG to a special branch (e.g. `github-pages` or `assets`), then embed it in your README.

### 3. Medium/Dev.to Blog Post Sync
Automatically fetch and display your latest technical articles.
* **Workflow**: Use the `gautamkrishnar/blog-post-workflow` in GitHub Actions. It runs on a cron schedule, fetches your RSS feed, and replaces a commented block (`<!-- BLOG-POST-LIST:START -->`) in the README.

### 4. Dynamic Spotify/Current Listen Integration
Show recruiters what you listen to while coding.
* **Steps**: Deploy `spotify-github-profile` on Vercel, connect it to your Spotify Developer account, and display a real-time "Currently Playing" badge.

### 5. Detailed WakaTime Coding Metrics
Include a breakdown of hours spent in VS Code/Cursor by language.
* **Steps**: Create a WakaTime account, add the extension to your IDE, and use a GitHub Action (like `athul/waka-readme`) to automatically commit your coding stats to your profile README weekly.
