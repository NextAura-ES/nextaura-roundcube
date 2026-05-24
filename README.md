<div align="center">

<img src="images/logo-dark.png" alt="NextAura Logo" height="80" />

# NextAura Mail — Roundcube Skin

**Skin oficial de NextAura para Roundcube Webmail.**  
Diseño moderno, modo oscuro nativo, paleta de marca y experiencia pulida lista para producción.

[![License: CC BY-SA 3.0](https://img.shields.io/badge/License-CC%20BY--SA%203.0-a27aff?style=flat-square)](http://creativecommons.org/licenses/by-sa/3.0/)
[![Roundcube](https://img.shields.io/badge/Roundcube-1.6%2B-7c3aed?style=flat-square)](https://roundcube.net/)
[![Dark Mode](https://img.shields.io/badge/Dark%20Mode-Native-0f0f12?style=flat-square&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHBhdGggZmlsbD0iI2ZmZiIgZD0iTTEyIDNhNiA2IDAgMCAwIDkgOSA5IDkgMCAxIDEtOSA5eiIvPjwvc3ZnPg==)](https://github.com/nextaura/nextaura-roundcube)
[![Based on Elastic](https://img.shields.io/badge/Based%20on-Elastic%20Skin-6d28d9?style=flat-square)](https://github.com/roundcube/roundcubemail/tree/master/skins/elastic)

</div>

---

## Capturas de pantalla

<table>
  <tr>
    <td align="center"><strong>Login — Modo oscuro</strong></td>
    <td align="center"><strong>Redactar — Modo oscuro</strong></td>
  </tr>
  <tr>
    <td><img src=".github/screenshots/dark-login.png" alt="Login dark mode" width="480"/></td>
    <td><img src=".github/screenshots/dark-compose.png" alt="Compose dark mode" width="480"/></td>
  </tr>
  <tr>
    <td colspan="2" align="center"><strong>Redactar — Modo claro</strong></td>
  </tr>
  <tr>
    <td colspan="2" align="center"><img src=".github/screenshots/light-compose.png" alt="Compose light mode" width="480"/></td>
  </tr>
</table>

---

## Características

- **Modo oscuro nativo** — soporte completo con `dark_mode_support: true`, logos separados y colores adaptados
- **Paleta de marca NextAura** — morado vibrante `#a27aff`, fondos profundos `#0f0f12`, tipografía Roboto
- **Sin gradientes** — diseño plano y limpio, sin ruido visual
- **Logos por modo** — logo claro/oscuro y versión reducida para cada modo
- **Scrollbars personalizadas** — thumb y track con los colores de marca en ambos modos
- **Responsive** — layouts para desktop, tablet y móvil (widescreen)
- **Construido sobre Elastic** — hereda la solidez del skin oficial de Roundcube

---

## Identidad de marca

| Rol              | Color       | Vista |
|------------------|-------------|-------|
| Primario         | `#a27aff`   | ![](https://placehold.co/14x14/a27aff/a27aff.png) |
| Primario hover   | `#b89aff`   | ![](https://placehold.co/14x14/b89aff/b89aff.png) |
| Primario active  | `#7c3aed`   | ![](https://placehold.co/14x14/7c3aed/7c3aed.png) |
| Primario deep    | `#6d28d9`   | ![](https://placehold.co/14x14/6d28d9/6d28d9.png) |
| Acento suave     | `#ede9fe`   | ![](https://placehold.co/14x14/ede9fe/ede9fe.png) |
| Fondo oscuro     | `#0f0f12`   | ![](https://placehold.co/14x14/0f0f12/0f0f12.png) |
| Superficie dark  | `#161620`   | ![](https://placehold.co/14x14/161620/161620.png) |
| Dark menu        | `#0a0a0a`   | ![](https://placehold.co/14x14/0a0a0a/0a0a0a.png) |

---

## Estructura

```
nextaura-roundcube/
├── images/               # Logos y assets gráficos
│   ├── logo.png          # Logo principal (modo claro)
│   ├── logo-dark.png     # Logo para modo oscuro
│   ├── logo-small.png    # Logo reducido (modo claro)
│   └── logo-small-dark.png
├── styles/
│   ├── _styles.less      # ★ Overrides de marca NextAura
│   ├── _variables.less   # Variables del tema base
│   ├── colors.less       # Paleta de colores
│   ├── dark.less         # Reglas de modo oscuro
│   ├── styles.less       # Punto de entrada principal
│   └── styles.min.css    # CSS compilado y minificado
├── templates/            # Plantillas HTML de Roundcube
├── fonts/                # Roboto + FontAwesome 5
├── deps/                 # Bootstrap 4 bundle
└── meta.json             # Metadatos del skin
```

> Para personalizar la marca edita `styles/_styles.less` y `styles/_variables.less`.  
> Los logos viven en `images/` — sustitúyelos manteniendo los mismos nombres.

---

## Instalación

### 1. Copiar el skin

```bash
cp -r nextaura-roundcube /var/www/roundcube/skins/nextaura
```

### 2. Activar en Roundcube

```php
// config/config.inc.php
$config['skin'] = 'nextaura';
```

### 3. Limpiar caché de assets (opcional)

```bash
cd /var/www/roundcube
bin/updatecss.sh --dir skins/nextaura
```

---

## Compilar estilos

Los estilos están escritos en **LESS**. Para recompilar tras modificar `_styles.less` o `_variables.less`:

**Requisitos:**
```bash
npm install -g less less-plugin-clean-css
```

**Compilar:**
```bash
lessc --clean-css="--s1 --advanced" styles/styles.less > styles/styles.min.css
lessc --clean-css="--s1 --advanced" styles/print.less  > styles/print.min.css
lessc --clean-css="--s1 --advanced" styles/embed.less  > styles/embed.min.css
```

> `lessc` >= 2.5.2 requerido.

---

## Logos recomendados

| Archivo                  | Uso                         | Tamaño recomendado |
|--------------------------|-----------------------------|--------------------|
| `images/logo.png`        | Login y cabecera modo claro | 500×200 px, PNG    |
| `images/logo-dark.png`   | Login y cabecera modo oscuro| 500×200 px, PNG    |
| `images/logo-small.png`  | Menú lateral modo claro     | 64×64 px, PNG      |
| `images/logo-small-dark.png` | Menú lateral modo oscuro| 64×64 px, PNG      |
| `images/favicon.ico`     | Favicon del navegador       | 32×32 px, ICO      |

Todos deben tener **fondo transparente**.

---

## Créditos

Este skin está construido sobre el excelente tema **Elastic** del equipo de Roundcube.

- Tema base: [Elastic Skin](https://github.com/roundcube/roundcubemail/tree/master/skins/elastic) — Aleksander Machniak
- Personalización de marca: [NextAura](https://nextaura.es)

Librerías incluidas:

| Librería         | Licencia  |
|------------------|-----------|
| Bootstrap 4      | MIT       |
| FontAwesome 5    | CC BY 4.0 |
| Roboto (Google)  | Apache 2.0|

---

## Licencia

Distribuido bajo **Creative Commons Attribution-ShareAlike 3.0**, heredada del skin Elastic.  
Puedes copiar, distribuir, modificar y adaptar este trabajo siempre que mantengas los créditos al autor original (**Aleksander Machniak**) en este `README.md`.

[Ver licencia completa](http://creativecommons.org/licenses/by-sa/3.0/)

---

<div align="center">
  <sub>Hecho con ☕ por <a href="https://nextaura.es">NextAura</a></sub>
</div>



