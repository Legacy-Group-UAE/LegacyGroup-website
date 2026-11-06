# Legacy Group Website

The marketing website for Legacy Group, a Dubai-based investment and advisory group.

The site is a single static page. All of its HTML and CSS live in `index.html`, and there is no build step or package install. Fonts (EB Garamond, Archivo and Space Grotesk) load from Google Fonts.

## Project structure

```text
.
├── index.html                    # The whole website
├── README.md
└── .github/workflows/deploy.yml  # Deployment to SiteGround
```

## Local development

Open `index.html` in a browser, or serve the folder locally:

```bash
python -m http.server 8000
```

Then go to <http://localhost:8000>.

## Deployment

Every push to `main` deploys the site to SiteGround over FTPS using GitHub Actions. To deploy without a new commit, run the **Deploy to SiteGround** workflow manually from the **Actions** tab.

The workflow reads its connection details from these GitHub Actions secrets:

| Secret         | Purpose                         |
| -------------- | ------------------------------- |
| `FTP_SERVER`   | FTP server hostname             |
| `FTP_USERNAME` | FTP account username            |
| `FTP_PASSWORD` | FTP account password            |
| `FTP_DIR`      | Target directory on the server  |

Test changes on a separate branch first, because anything merged into `main` goes live.
