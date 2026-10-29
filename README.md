# devops-a2-012

Assignment 2 (Build, Containerize and Automate) for the DevOps for Cloud Computing lab.

**Name:** Muhammad Taha
**Roll number:** fa23-bai-012

## What this project is

A small personal portfolio page written in plain HTML and CSS. The page is
packaged in a Docker image (nginx) and a GitHub Actions workflow checks the
page and pushes the image to Docker Hub on every push to `main`.

## Files

| File | Purpose |
|------|---------|
| `index.html` | The web page |
| `style.css` | Styling for the page |
| `Dockerfile` | Builds the nginx image that serves the page |
| `.github/workflows/ci.yml` | CI workflow: check, build, push |
| `.gitignore` | Files Git should not track |

## Run it locally

```bash
docker build -t devops-a2 .
docker run -d -p 8080:80 --name page devops-a2
```

Then open http://localhost:8080 in a browser.

## Workflow

- Every push to `main` and every pull request runs the checks and builds the image.
- Only pushes to `main` push the image to Docker Hub with the `latest` tag.
