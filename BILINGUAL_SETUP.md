# Configuración Bilingüe del Blog / Bilingual Blog Setup

## Resumen / Overview

Este blog ahora soporta contenido bilingüe (inglés y español) usando el plugin **jekyll-polyglot**.

This blog now supports bilingual content (English and Spanish) using the **jekyll-polyglot** plugin.

## Estructura / Structure

```
_posts/
  ├── en/          # English posts
  │   └── 2025-01-22-post-title.md
  └── es/          # Spanish posts
      └── 2025-01-22-post-title.md
```

## Configuración Completada / Completed Configuration

1. ✅ Plugin jekyll-polyglot agregado al Gemfile
2. ✅ Configuración de idiomas en _config.yml
3. ✅ Estructura de carpetas creada (_posts/en/ y _posts/es/)
4. ✅ Selector de idioma agregado al header
5. ✅ Estilos CSS para el selector de idioma
6. ✅ Posts existentes movidos a _posts/en/
7. ✅ Campo `lang:` agregado a todos los posts
8. ✅ Ejemplo de post traducido creado

## Próximos Pasos / Next Steps

### 1. Instalar Dependencias / Install Dependencies

```bash
bundle install
```

### 2. Probar el Sitio Localmente / Test the Site Locally

```bash
bundle exec jekyll serve
```

Visita / Visit: `http://localhost:4000`

### 3. Crear Traducciones / Create Translations

Para cada post en `_posts/en/`, crea su versión en español en `_posts/es/` con:
- Mismo nombre de archivo
- Campo `lang: es` en el frontmatter
- Contenido traducido

For each post in `_posts/en/`, create its Spanish version in `_posts/es/` with:
- Same filename
- `lang: es` field in frontmatter
- Translated content

### 4. URLs Generadas / Generated URLs

El plugin generará automáticamente:
- Inglés (default): `https://tudominio.com/post-title/`
- Español: `https://tudominio.com/es/post-title/`

The plugin will automatically generate:
- English (default): `https://yourdomain.com/post-title/`
- Spanish: `https://yourdomain.com/es/post-title/`

## Frontmatter Requerido / Required Frontmatter

```yaml
---
layout: post
title: "Your Title / Tu Título"
lang: en  # or 'es' for Spanish
categories: programming
author:
  - Carlos A. Planchón
---
```

## Selector de Idioma / Language Selector

El selector de idioma aparece automáticamente en el header y cambia entre versiones del mismo post.

The language selector appears automatically in the header and switches between versions of the same post.

## Recursos / Resources

- [jekyll-polyglot documentation](https://github.com/untra/polyglot)
- [Jekyll documentation](https://jekyllrb.com/docs/)

## Notas / Notes

- Los posts sin traducción solo aparecerán en su idioma original
- Las imágenes en `/media/` son compartidas entre idiomas
- El idioma por defecto es inglés (configurable en _config.yml)

- Posts without translation will only appear in their original language
- Images in `/media/` are shared between languages
- Default language is English (configurable in _config.yml)
