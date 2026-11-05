# epiops-site

Official site for **EpiOps™ Workshops & Training** — hands-on training in public health data modernization, offered by Sai Kurmana, MPH, MS, CPHIMS.

The whole site is one self-contained file: [`index.html`](index.html) (inline CSS, no JavaScript, no external fonts, no build step).

## Enable GitHub Pages (one step)

In this repository on GitHub go to **Settings → Pages → Build and deployment → Source** and choose **GitHub Actions**.

That's it. The workflow in [`.github/workflows/pages.yml`](.github/workflows/pages.yml) deploys automatically on every push to `main` (you can also run it by hand from the **Actions** tab → *Deploy to GitHub Pages* → *Run workflow*). The live URL appears on the Settings → Pages screen, normally `https://<your-username>.github.io/epiops-site/`.

> Note: the workflow deploys from `main`. Merge this branch into `main` first, or the first deploy won't run.

## Before using the page as a trademark specimen

- **Capture the specimen** from the live URL, with the URL and access date visible in the screenshot.

## Custom domain (later)

Once you've bought a domain (the examples below use `epiops.io`), you can point it at this site in four steps. Once the domain is live, the site is served at the domain's root (`https://epiops.io/`) instead of `/epiops-site/`. All links on the page are relative, so nothing in `index.html` needs to change.

**1. Verify the domain with GitHub (recommended).**
Go to GitHub **profile picture → Settings → Pages → Add a domain** and follow the prompt to add a TXT record at your registrar. Verifying the domain stops anyone else from claiming it for their own Pages site.

**2. Create the DNS records at your registrar.**

For the root domain (`epiops.io`), add all four `A` records and, optionally, the four `AAAA` (IPv6) records:

| Type | Host / Name | Value |
|------|-------------|-------|
| A    | `@` | `185.199.108.153` |
| A    | `@` | `185.199.109.153` |
| A    | `@` | `185.199.110.153` |
| A    | `@` | `185.199.111.153` |
| AAAA | `@` | `2606:50c0:8000::153` |
| AAAA | `@` | `2606:50c0:8001::153` |
| AAAA | `@` | `2606:50c0:8002::153` |
| AAAA | `@` | `2606:50c0:8003::153` |

For `www.epiops.io`, add:

| Type  | Host / Name | Value |
|-------|-------------|-------|
| CNAME | `www` | `saikurmana.github.io` |

Delete any default "parking" `A`/`CNAME` records the registrar created for `@` or `www`. Never use wildcard records (`*.epiops.io`). DNS changes can take anywhere from a few minutes to 24 hours to propagate.

**3. Tell GitHub Pages about the domain.**
In this repo go to **Settings → Pages → Custom domain**, enter `epiops.io`, and click **Save**. GitHub runs a DNS check. Because `www` is also configured, `www.epiops.io` will automatically redirect to `epiops.io`.

*About the `CNAME` file:* sites deployed from a branch store the domain in a file named `CNAME` at the site root, containing one line: `epiops.io`. This repo deploys with a **GitHub Actions workflow**, and for workflow deploys GitHub ignores any `CNAME` file. The **Settings → Pages → Custom domain** field from this step is what actually takes effect. You can still commit a `CNAME` file to the repo root as a record of the domain if you like, but it isn't required and isn't what makes the domain work.

**4. Turn on HTTPS.**
Once the DNS check passes, GitHub issues a free certificate. This usually takes minutes, but can take up to an hour. When it's ready, tick **Enforce HTTPS** on the same Settings → Pages screen. If the checkbox stays greyed out, wait a bit longer. If it still doesn't enable, remove the custom domain, save, then re-add it.

> Trademark-specimen tip: if you switch to a custom domain, recapture the specimen screenshot from the new URL.

## Preview locally

Open `index.html` in a browser — nothing to install.
