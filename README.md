# epiops-site

Official site for **EpiOps™ Workshops & Training** — hands-on training in public health data modernization, offered by Sai Kurmana, MPH, MS, CPHIMS.

The whole site is one self-contained file: [`index.html`](index.html) (inline CSS, no JavaScript, no external fonts, no build step).

## Enable GitHub Pages (one step)

In this repository on GitHub go to **Settings → Pages → Build and deployment → Source** and choose **GitHub Actions**.

That's it. The workflow in [`.github/workflows/pages.yml`](.github/workflows/pages.yml) deploys automatically on every push to `main` (you can also run it by hand from the **Actions** tab → *Deploy to GitHub Pages* → *Run workflow*). The live URL appears on the Settings → Pages screen, normally `https://<your-username>.github.io/epiops-site/`.

> Note: the workflow deploys from `main`. Merge this branch into `main` first, or the first deploy won't run.

## Before using the page as a trademark specimen

- **Capture the specimen** from the live URL, with the URL and access date visible in the screenshot.

## Preview locally

Open `index.html` in a browser — nothing to install.
