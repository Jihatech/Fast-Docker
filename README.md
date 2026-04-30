# Fast-Docker

> Fork de [omerbsezer/Fast-Docker](https://github.com/omerbsezer/Fast-Docker) — Guide d'apprentissage Docker en 12 laboratoires pratiques, enrichi d'un guide HTML illustré.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)](https://www.docker.com/)
[![Compose v2](https://img.shields.io/badge/Compose-v2-blue)](https://docs.docker.com/compose/)

---

## 📘 Guide d'apprentissage interactif

> **Nouveau** : un guide HTML illustré accompagne ce repository pour faciliter la prise en main, avec schémas SVG, parcours progressifs et cheatsheet.

🌐 **[Consulter le guide en ligne →](https://jihatech.github.io/Fast-Docker/)**

📥 [Version HTML autonome](./docs/index.html) — fonctionne hors-ligne

### Ce que le guide apporte

- ✅ **Théorie illustrée** — 8 schémas SVG (architecture, cycle de vie, couches, réseaux, volumes, multi-stage, sécurité)
- ✅ **3 parcours d'apprentissage** selon votre niveau (débutant complet, express, préparation Kubernetes)
- ✅ **12 laboratoires détaillés** avec objectifs, durées, pièges classiques et critères de validation
- ✅ **Cheatsheet complète** des commandes Docker à connaître
- ✅ **Pont vers Kubernetes** — table de correspondance des concepts Docker → K8s
- ✅ **Responsive et imprimable** — utilisable sur tous supports

---

## 🧪 Les douze laboratoires

### Concepts fondamentaux

| # | Laboratoire | Sujet | Durée | Niveau |
|---|---|---|---|---|
| 01 | [Premier conteneur](./LAB01-FirstImageFirstContainer.md) | Image, build, run, exec | 45 min | Débutant |
| 02 | [Volumes et bind mounts](./LAB02-DockerVolume.md) | Persistance des données | 45 min | Débutant |
| 03 | [Docker Compose v2](./LAB03-DockerCompose.md) | Multi-services (WordPress + MySQL) | 1 h | Débutant |
| 06 | [Transferts host ↔ container](./LAB06-DockerTransferringContent.md) | `docker cp` et débogage | 20 min | Débutant |

### Fonctionnalités avancées (2024+)

| # | Laboratoire | Sujet | Durée | Niveau |
|---|---|---|---|---|
| 10 | [Multi-platform builds](./LAB10-MultiPlatformBuilds.md) | ARM64 + AMD64 avec BuildKit | 45 min | Intermédiaire |
| 11 | [Sécurité](./LAB11-SecurityBestPractices.md) | Distroless, non-root, scan Trivy | 1 h | Intermédiaire |
| 12 | [Healthchecks et .dockerignore](./LAB12-HealthchecksDockerignore.md) | Bonnes pratiques production | 30 min | Débutant |

### Registry et configuration

| # | Laboratoire | Sujet | Durée | Niveau |
|---|---|---|---|---|
| 05 | [Registry local](./LAB05-DockerLocalRegistry.md) | Publier ses propres images | 45 min | Intermédiaire |
| 09 | [Configuration du daemon](./LAB09-DockerConfiguration.md) | Proxy, registries, logs | 30 min | Intermédiaire |

### Builds spécifiques

| # | Laboratoire | Sujet | Durée | Niveau |
|---|---|---|---|---|
| 07 | [Build C++ Linux](./LAB07-DockerfileForLinuxC++Build.md) | Multi-stage en pratique | 45 min | Intermédiaire |
| 08 | [Build C++ Windows](./LAB08-DockerfileForWindowsC++Build.md) | Conteneurs Windows | 30 min | Avancé |

### Orchestration legacy

| # | Laboratoire | Sujet | Durée | Niveau |
|---|---|---|---|---|
| 04 | [Docker Swarm](./LAB04-DockerStackService.md) ⚠️ legacy | Stack et services | 30 min | Intermédiaire |

---

## 🚀 Démarrage rapide

### 1. Prérequis

```bash
docker version            # >= 24.x
docker compose version    # v2.x (avec espace, pas de tiret)
docker buildx version     # buildx présent par défaut
```

Si vous n'avez pas Docker, voir la [section installation du guide](https://jihatech.github.io/Fast-Docker/#prerequis).

### 2. Cloner le repository

```bash
git clone https://github.com/Jihatech/Fast-Docker.git
cd Fast-Docker
```

### 3. Ouvrir le guide en local

```bash
# macOS
open docs/index.html

# Linux
xdg-open docs/index.html

# Windows
start docs/index.html
```

### 4. Premier lab

```bash
cat LAB01-FirstImageFirstContainer.md
```

---

## 🎯 Parcours recommandés

### Parcours A — Découverte complète (~ 8-12 h, 2-3 semaines)

```
LAB01 → LAB06 → LAB02 → LAB12 → LAB03 → LAB09 →
LAB05 → LAB07 → LAB11 → LAB10 → LAB04 → LAB08
```

### Parcours B — Express (~ 4 h, l'essentiel)

```
LAB01 → LAB02 → LAB03 → LAB11 → LAB12
```

### Parcours C — Préparation Kubernetes / CKA

```
LAB01 → LAB02 → LAB11 → LAB12 → § Pont K8s
```

Détails et justifications dans le [guide HTML, section Méthode](https://jihatech.github.io/Fast-Docker/#parcours).

---

## 🛠️ Outils complémentaires recommandés

| Outil | Rôle | Installation |
|---|---|---|
| [`dive`](https://github.com/wagoodman/dive) | Inspecter les couches d'image | `brew install dive` |
| [`trivy`](https://github.com/aquasecurity/trivy) | Scanner les vulnérabilités | `brew install trivy` |
| [`hadolint`](https://github.com/hadolint/hadolint) | Linter Dockerfile | `brew install hadolint` |
| [`ctop`](https://github.com/bcicen/ctop) | top-like pour conteneurs | `brew install ctop` |
| [`lazydocker`](https://github.com/jesseduffield/lazydocker) | Interface terminal Docker | `brew install lazydocker` |

---

## 📚 Référence rapide

- [Cheatsheet des commandes Docker](./DockerCommandCheatSheet.md)
- [Projets exemples](./hands-on-sample-projects/)
- [Labs avancés](./labs/)
- [Guide HTML complet](./docs/index.html)

---

## 🌍 Sujets abordés

**Concepts** : Containerisation · Architecture client/daemon · Union File System · Cycle de vie · Isolation namespaces et cgroups

**Construction** : Dockerfile · Multi-stage builds · BuildKit · Cache · Build secrets · Multi-platform (ARM/AMD64)

**Orchestration** : Docker Compose v2 · Healthchecks · Dépendances `service_healthy` · Networks (bridge, host, overlay)

**Persistance** : Volumes nommés · Bind mounts · tmpfs · Backup et migration

**Sécurité** : Distroless · Non-root · Scan de vulnérabilités (Trivy, Docker Scout) · `.dockerignore` · Bonnes pratiques OWASP

**Production** : Registry (local, Harbor, ECR, ACR) · Configuration daemon · Proxy d'entreprise · Limitation des logs

---

## 🏗️ À propos de ce fork

Ce repository est un fork de [omerbsezer/Fast-Docker](https://github.com/omerbsezer/Fast-Docker), maintenu par [Jihatech](https://github.com/Jihatech).

### Apports du fork

- 📘 **Guide HTML illustré** (`docs/index.html`) — accompagnement pas-à-pas en français
- 🎨 **Schémas SVG** intégrés pour visualiser les concepts abstraits
- 🗺️ **Parcours d'apprentissage** structurés selon le profil du lecteur
- 🌐 **Publication GitHub Pages** pour un accès web direct

### Synchronisation avec l'upstream

Pour récupérer les mises à jour du repository d'origine :

```bash
git remote add upstream https://github.com/omerbsezer/Fast-Docker.git
git fetch upstream
git merge upstream/main
git push origin main
```

### Contribuer

Les pull requests sont les bienvenues, en particulier pour :

- Ajouter des laboratoires supplémentaires (intégration cloud, CI/CD, supply chain)
- Corriger ou enrichir le guide HTML
- Traduire la documentation
- Améliorer les schémas SVG existants

Ouvrir une [issue](https://github.com/Jihatech/Fast-Docker/issues) pour proposer un changement majeur avant d'attaquer.

---

## 📖 Ressources externes

### Documentation officielle

- [docs.docker.com](https://docs.docker.com/)
- [BuildKit](https://docs.docker.com/build/buildkit/)
- [Docker Compose v2](https://docs.docker.com/compose/)
- [Kubernetes](https://kubernetes.io/docs/)

### Sécurité

- [OWASP Docker Security Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Docker_Security_Cheat_Sheet.html)
- [CIS Docker Benchmark](https://www.cisecurity.org/benchmark/docker)
- [Distroless Images](https://github.com/GoogleContainerTools/distroless)

### Pratique en ligne

- [Play with Docker](https://labs.play-with-docker.com/) — sandbox sans installation
- [Killercoda Docker](https://killercoda.com/playgrounds/scenario/docker)

---

## 📄 Licence

Distribué sous licence MIT — voir [LICENSE](./LICENSE).

Le contenu original est l'œuvre de [omerbsezer](https://github.com/omerbsezer). Le guide HTML et les ajouts de ce fork sont de [Jihatech](https://github.com/Jihatech).

---

<p align="center">
  <strong>📘 <a href="https://jihatech.github.io/Fast-Docker/">Accéder au guide complet</a> · 🐳 Bon apprentissage Docker !</strong>
</p>
