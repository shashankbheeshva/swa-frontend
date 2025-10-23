# React basic
# 10/23/2025 editing to avoid expiry 
[Azure Static Web Apps](https://docs.microsoft.com/azure/static-web-apps/overview) allows you to easily build [React](https://reactjs.org/) apps in minutes. Use this repo with the [React quickstart](https://docs.microsoft.com/azure/static-web-apps/getting-started?tabs=react) to build and customize a new static site.

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Branching Strategy (Main + Develop)

- Default branch: `develop`
- Work from short-lived branches off `develop`:
  - feat/<topic>   # new feature
  - fix/<topic>    # bug fix
  - chore/<topic>  # tooling/infra
  - hotfix/<topic> # urgent prod fix (branch from main)

### Daily flow (developers)
git checkout develop
git pull origin develop
git checkout -b feat/<topic>
# ...code...
git commit -m "feat: short message"
git push -u origin feat/<topic>
# Open PR: base=develop, compare=feat/<topic>

### Release (owner)
# Open PR: base=main, compare=develop
# After merge:
git fetch --tags
git tag vX.Y.Z
git push origin vX.Y.Z

### Hotfix
# branch from main
git checkout -b hotfix/<issue> main
# PR1: hotfix -> main (owner merges)
# PR2: hotfix -> develop (back-merge)

