# Virtual Physics Lab

Spanish version: [README.md](README.md)

Educational Physics simulator platform built to be published as a static GitHub Pages site. The project works as a scalable catalog: each simulator lives in its own folder, has a direct URL, and is registered through `data/simulators.json`.

## Credits

Simulators developed by Yandri Macías  
Web Design Washington Indacochea  
for the students of Unidad Educativa 30 de Septiembre.

## Included Simulators

- Hooke's Law: virtual dynamometer for analyzing mass, gravity, force, spring constant `k`, elongation, and the relationship `F = kx`.
- Projectile Motion: launch laboratory with initial velocity, angle, gravity, trajectory, graphs, maximum height, range, and flight time.

## Screenshots

Space reserved for the catalog and simulator screenshots:

- `assets/images/catalogo.png`

### Hooke's Law

![](assets/images/LeydeHooke-ezgif.com.gif)

### Projectile Motion

![](assets/images/MovimientoParablico-ezgif.com.gif)

## ROADMAP

- [x] Reorganized the project as a modular simulator platform.
- [x] Main catalog generated from `data/simulators.json`.
- [x] Working deployment on GitHub Pages.
- [x] Initial bilingual support in Spanish and English.
- [x] Independent pages for Hooke's Law and Projectile Motion.
- [x] Visible credits on the landing page and in each simulator.
- [x] Full favicon package integrated (`.svg`, `.ico`, `.png`, `apple-touch-icon`).
- [x] Custom `404.html` page.
- [x] `.nojekyll` file for GitHub Pages compatibility.
- [x] Social sharing image configured for WhatsApp and Facebook.
- [x] GitHub repository invitation block with fork call to action.
- [ ] Add more simulations when Professor Yandri Macías sends them.

## Structure

```text
/
├── index.html
├── simulators/
│   ├── hooke/
│   │   ├── index.html
│   │   ├── script.js
│   │   ├── style.css
│   │   └── thumbnail.webp
│   ├── movimiento-parabolico/
│   │   ├── index.html
│   │   ├── script.js
│   │   ├── style.css
│   │   └── thumbnail.webp
│   └── futuros-simuladores/
├── assets/
│   ├── css/
│   ├── js/
│   ├── icons/
│   └── images/
├── data/
│   └── simulators.json
├── i18n/
│   ├── es.json
│   └── en.json
├── README.md
└── README_EN.md
```

## Run Locally

Because the catalog and translations are loaded with `fetch`, use a local server:

```bash
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000/
```

## Deploy to GitHub Pages

1. Push your changes to the `wachin/yandri-macias-simulators` repository.
2. In GitHub, go to `Settings > Pages`.
3. Under `Build and deployment`, choose `Deploy from a branch`.
4. Select the main branch and the `/root` folder.
5. Save the configuration.

The public URL will look like this:

```text
https://wachin.github.io/yandri-macias-simulators/
```

## Add a New Simulator

1. Create a folder inside `simulators/`, for example `simulators/simple-pendulum/`.
2. Add its `index.html`, `script.js`, `style.css`, and `thumbnail.webp` files.
3. Register the simulator in `data/simulators.json`:

```json
{
  "id": "simple-pendulum",
  "slug": "simple-pendulum",
  "url": "simulators/simple-pendulum/",
  "thumbnail": "simulators/simple-pendulum/thumbnail.webp",
  "status": "available",
  "level": "High School",
  "topics": ["oscillations", "gravity"]
}
```

4. Add its translated texts in `i18n/es.json` and `i18n/en.json`, inside `simulators`.
5. There is no need to modify the main catalog JavaScript.

## Add a New Language

1. Create a file in `i18n/`, for example `fr.json`.
2. Copy the key structure from `es.json`.
3. Add the language in `assets/js/i18n.js`, inside `supportedLanguages`.
4. Add an option in the language selectors of `index.html` and each simulator page.

## Technologies

- HTML5
- Responsive modern CSS
- Modular JavaScript for static sites
- Canvas 2D for the simulations
- WebP for lightweight thumbnails

## License

License still to be defined by the project authors.
