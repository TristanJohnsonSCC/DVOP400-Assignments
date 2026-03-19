# DVOP400-Assignments

## Final Project: Docker + GitHub Actions + AKS (Kubernetes)

### What is included in this repo

- Node/Express app serving static HTML pages from `public/`
- Docker image defined in `Dockerfile`
- GitHub Actions workflow to publish Docker image at `.github/workflows/main.yml`
- New AKS deployment workflow at `.github/workflows/aks-deploy.yml`
- Kubernetes manifest in `k8s/deployment.yaml` (Deployment + LoadBalancer Service)

### Required GitHub secrets for AKS deployment

- `DOCKER_USERNAME` (Docker Hub username)
- `DOCKER_PASSWORD` (Docker Hub token/password)
- `AZURE_CREDENTIALS` (service principal JSON)
- `AKS_RESOURCE_GROUP`
- `AKS_CLUSTER_NAME`

### Run locally

- `npm install`
- `node server.js`
- Open http://localhost:3000

### Kubernetes deployment steps (instructors)

1. Create AKS cluster in Azure and ensure it is in the resource group.
2. Create a service principal and set `AZURE_CREDENTIALS` in GitHub repository secrets.
3. Push to `main`; GitHub Action builds image, pushes to Docker Hub, then deploys to AKS.
4. Expose app via AKS LoadBalancer and visit the external IP.

### Assignment checklist

- [x] Home page with workflow links (in `public/index.html`)
- [x] Workflow pages link back to home
- [x] Docker image published from GitHub Actions
- [x] Kubernetes deployment path added and documented
