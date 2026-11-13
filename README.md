# Astral Nova Design `1.0.0`

Méta-package Composer : point d’entrée unique pour la stack UI **Nova Design**.

Il ne contient pas de code. Il `require` les trois artefacts alignés en `^1.0` :

| Package | Rôle |
|---------|------|
| `astral-php/astral-nova-css` | Design system CSS / JS (`@astral-php/nova-css`) |
| `astral-php/astral-nova-icons` | Sprite SVG + tailles |
| `astral-php/astral-template-nova` | Layouts et partials PHP |

## Installation (apps)

```bash
composer require astral-php/astral-nova-design:^1.1
```

Puis publier les builds vers le webroot, typiquement :

```text
public/assets/nova/   ← nova.css, JS, icons…
public/assets/app/    ← branding et CSS locaux
```

Voir le bac de référence `astral-starter-nova`.

## Développement local (path)

```json
"repositories": [
  { "type": "path", "url": "../components-astral/astral-nova-design", "options": { "symlink": true } },
  { "type": "path", "url": "../components-astral/astral-nova-css", "options": { "symlink": true } },
  { "type": "path", "url": "../components-astral/astral-nova-icons", "options": { "symlink": true } },
  { "type": "path", "url": "../components-astral/astral-template-nova", "options": { "symlink": true } }
]
```

## Hors périmètre

- Fusion du code des 3 packages (rejétée) — artefacts séparés maintenus.
- `astral-php/astral-template` (Tailwind) — lignée distincte, freeze / deprecate.

## Publication

Tags / Packagist : uniquement après go explicite (gate BOM + playbook `release-tag`).
