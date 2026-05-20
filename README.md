# AI Tip of the Day

A small, polished web page that fetches a random fact from a live API and displays it with smooth animations. Click "New Fact" and a fresh one appears every time.

**[Live Demo](https://yourusername.github.io/ai-tip-of-the-day)** — replace `yourusername` with your GitHub username once deployed.

![Built with HTML, CSS, and JavaScript](https://img.shields.io/badge/Built_with-HTML%20%7C%20CSS%20%7C%20JS-1a1a2e)

---

## What It Does

The page sends a request to a free public API called [Useless Facts](https://uselessfacts.jsph.pl/) and displays the response as a styled card. Every time you click the button, it fetches a brand new fact, fades out the old one, and fades in the new one. A counter at the bottom tracks how many facts you've explored.

If the API is unreachable (no internet, server down), the page shows a friendly error message instead of breaking silently.

## How to Run It

No install, no setup, no terminal commands needed.

1. Download `index.html` from this repo (click the file, then click the download button).
2. Double-click it. It opens in your browser.
3. That's it. The page is fully self-contained.

If you want to host it online so anyone can visit the link, see the "Deployment" section below.

## How It Works

The page is a single HTML file with three sections baked in:

**The structure (HTML)** defines what's on the page: a heading, a card to display the fact, a button, and a counter.

**The styling (CSS)** controls how everything looks: the fonts, colors, spacing, animations, and how the layout adjusts on smaller screens so it works on phones too.

**The logic (JavaScript)** is where the interesting part happens. When the page loads (and each time you press the button), a function called `fetchFact()` runs. It reaches out to the API over the internet, waits for a response, pulls the fact out of the data, and writes it into the card. The `async/await` pattern handles the waiting, and a `try/catch` block handles anything that goes wrong.

## Deployment

This project is hosted for free using GitHub Pages.

To deploy your own copy:

1. Fork or clone this repo.
2. Go to **Settings** > **Pages**.
3. Set the source to **Deploy from a branch**, pick **main**, and save.
4. Your page will be live within a minute at `https://yourusername.github.io/ai-tip-of-the-day`.

## What I Learned Building This

**Fetching data from an API.** This was my first time calling a real, live API from a web page. The pattern is straightforward: `fetch()` sends the request, `.json()` parses the response, and then you use the data however you want. This same pattern works for weather apps, stock tickers, search tools, or anything that pulls data from the internet.

**Error handling matters.** Without `try/catch`, the page would silently break if the API went down. Wrapping the fetch in error handling means the user sees a clear message instead of a blank screen. Small thing, big difference.

**Responsive design with media queries.** The page adjusts its layout for smaller screens using a `@media` rule. On phones, the card padding shrinks and the button stacks below the source label instead of sitting beside it.

**CSS can do a lot of heavy lifting.** The fade transitions, the button spin, the gradient bar at the top of the card, and the blurred background shapes are all pure CSS. No animation libraries needed.

## Tech Stack

- HTML5
- CSS3 (custom properties, flexbox, media queries, keyframe animations)
- Vanilla JavaScript (async/await, fetch API, DOM manipulation)
- [Useless Facts API](https://uselessfacts.jsph.pl/) (free, no API key required)

---

_This is a portfolio project. The facts come from a third-party API and I don't control their content or availability._
