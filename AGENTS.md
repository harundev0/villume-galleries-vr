# Project Instructions: Villume Galleries VR

## Tool Rules
- **Tool `write`**: WAJIB selalu menyertakan `path` dan `content`.
- **Tool `edit`**: WAJIB menyertakan `path`, `oldString`, dan `newString`.

## Directory Structure
- `index.html`: Entry point portal Villume Galleries VR (Auto-redirect).
- `galleries.html`: Halaman utama gallery VR bergaya window list dengan spatial dock layout Apple Vision Pro.
- `artists.html`: Halaman direktori VR artists dengan grid aesthetics, side dock navigasi Apple Vision Pro fashion.
- `artist-detail.html`: Halaman detail specific seniman yang menonjolkan profil & list artworks. 
- `prototype.html`: Implementasi full immersion view untuk VR showcase control dengan minimal HUD di bawah.
- `assets/css/`: File stylesheet utama (`global.css`) yang memuat seluruh var theme dark glassmorphism.
- `assets/images/`: Ekstraksi gambar background envionment VR.

## Catatan Build UI UX
- Desain menggunakan referensi *spatial computing* ala Apple Vision Pro.
- Mode Gelap (Dark Mode) Glassmorphism dengan refraksi dan backdrop blur di set via `assets/css/global.css`.
- Floating dock & standalone window panel diterapkan di struktur flex center.
- Phosphor icon dan GSAP animasi smooth diterapkan untuk pergerakan spatial.