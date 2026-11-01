# QR Image Server (Nuxt 3)

A minimal Nuxt 3 project that serves image files directly by URL.

## Add your images

Copy your image files into the `public/` folder. For example:

- `public/qrcode1.png`
- `public/qrcode2.png`

## Run locally

```bash
npm install
npm run dev
```

Open the local URL printed by Nuxt. If it starts on port 3000:

- `http://localhost:3000/qrcode1.png`
- `http://localhost:3000/qrcode2.png`

If port 3000 is already in use, Nuxt may choose another port (such as 3001). Use the port shown in your terminal.

## Important

This project uses Nuxt 3, so static public files belong in `public/` (not Nuxt 2's `static/` folder). No Vue page or route is needed for each image.
