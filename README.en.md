[中文](README.md) | **English**

# Wen Yifan Portfolio

Wen Yifan's visual design portfolio, focusing on branding, packaging, 3D imagery, and interactive experiences.

## Local development

```sh
npm install
npm run dev
```

Open `http://localhost:3000`. Both `/` and `/synthesis/` lead directly to the portfolio.

## Production build

```sh
npm run build
```

This project uses static export. The output directory is `out`; do not use `next start`. With Python installed, preview the export with:

```sh
python -m http.server 4173 --directory out
```

Then open `http://localhost:4173/synthesis/`.

The build generates responsive WebP assets and repairs preload filenames for Next 16.3.2 on Windows. Use `npm run build`, rather than calling `npx next build` directly, so image preprocessing and export repairs run.

For Cloudflare Pages, use build command `npm run build` and output directory `out`. For manual uploads, upload the complete `out` directory, including `_next`, `portfolio-assets`, and `portfolio-optimized`. Uploading only the source or HTML leaves assets missing.

See the [motion and performance verification notes](docs/motion-performance.md), currently in Chinese.

## Existing Netlify configuration

The repository already contains a `netlify.toml` with:

- Build command: `npm run build`
- Publish directory: `.next`
- Production branch: `main`

This is the earlier Next plugin configuration; the original documentation does not report verification of that Netlify deployment. The current `output: "export"` static build uses `out`. Do not use the `.next` publish setting for Cloudflare Pages.
