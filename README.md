# Resume — Huzaifa Khan

My resume as a web page, live at [huzaifa-resume-self.vercel.app](https://huzaifa-resume-self.vercel.app/).

It's plain HTML, CSS and a few lines of JavaScript. No framework and no build step.

## Files

```
├── index.html                  the resume content
├── style.css                   layout, colours, print styles
├── script.js                   fade-in animation on load
├── favicon.ico                 tab icon
└── Huzaifa-Khan-Resume.pdf     downloadable copy (linked from the top bar)
```

## Running it locally

Open `index.html` in your browser. That's it.

If you'd rather run it on a local server (closer to how Vercel serves it), run this from the project folder:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Editing

**Content.** Everything is in `index.html`, split into sections: Summary, Experience, Skills and Certifications. Each job is a `.entry` block, so the easiest way to add one is to copy an existing block and change the text.

**Skill tags.** The colour of a tag comes from its class:

| Class     | Used for                      |
|-----------|-------------------------------|
| `accent`  | Main languages and frameworks |
| `outline` | Things I'm still learning     |
| `neutral` | Tools                         |
| `sage`    | Practices and other skills    |

**Colours and fonts.** They're all CSS variables at the top of `style.css` (`:root`). Change them there and the whole page updates. Headings use Caprasimo and body text uses Figtree, both from Google Fonts.

**Cache busting.** CSS, JS and the PDF are linked with a version query, for example `style.css?v=4`. After editing a file, bump its number in `index.html` so browsers don't keep the old copy.

## Updating the PDF

The page has print styles that lay it out on a single A4 sheet and hide the top bar. To make a new PDF:

1. Open the page in Chrome or Edge.
2. Press `Ctrl + P` (`Cmd + P` on Mac).
3. Set the destination to **Save as PDF**.
4. Set margins to **None**. The page handles its own margins.
5. Turn on **Background graphics**, otherwise the skill tags lose their colours.
6. Save it as `Huzaifa-Khan-Resume.pdf` in the project folder, replacing the old one.
7. Bump the `?v=` number on the Download PDF link in `index.html`.

## Deploying

The site is hosted on [Vercel](https://vercel.com) and connected to this repo. Every push to the main branch redeploys it automatically.

## Notes

- The layout is responsive and switches to a tighter layout on screens under 640px.
- If JavaScript is turned off, the content still shows. It just doesn't fade in.
- External links open in a new tab with `rel="noopener noreferrer"`.
