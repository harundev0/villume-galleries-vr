# Villume Design System

## 1. Design Tokens

### Colors (OKLCH Color Space)
Villume menggunakan warna berbasis fungsi *oklch* untuk akurasi dan vibransi warna yang modern.

**Base & Neutrals:**
- `--v-neutral-0`: `oklch(1 0 0)` (White)
- `--v-neutral-950`: `oklch(.18 .01 270)` (Dark gray/Black)
- `--v-indigo-600`: `oklch(.511 .262 276.966)` (Villume Indigo - Brand Primary)

**Semantic Colors:**
- **Background**: `var(--v-neutral-0)` (White)
- **Foreground**: `var(--v-neutral-950)`
- **Primary**: `var(--v-indigo-600)`
- **Primary Foreground**: `oklch(.985 0 0)` (Off-white/light)
- **Muted**: `oklch(.97 .004 270)`
- **Muted Foreground**: `oklch(.52 .013 270)`
- **Accent**: `oklch(.965 .012 277)`
- **Accent Foreground**: `oklch(.3 .06 277)`
- **Destructive (Error)**: `oklch(.577 .245 27.325)`
- **Border**: `oklch(.922 .005 270)`

**UI Effects & Overlays:**
- **Surface Tint**: `oklch(.985 .006 277)`
- **Grid Line**: `oklch(.92 .006 277 / 0.7)` 
- **Shadow Color**: `270 30% 12%` *(Digunakan dengan HSL)*
- **Halo (Glow effect)**: `oklch(.511 .262 276.966 / 0.14)`

### Theme Support (Dark & Light Mode)
Theme handling is primarily inferred via CSS variable reassignment. Based on the semantic structure pattern of UI tokens (background, foreground, primary-foreground), mode switching is done by inverting the variables:

*Light Mode (Default Variables):*
- `--background`: `var(--v-neutral-0)` *(White - `oklch(1 0 0)`)*
- `--foreground`: `var(--v-neutral-950)` *(Dark - `oklch(.18 .01 270)`)*

*Dark Mode (Triggered by `.dark` class or UI Toggle):*
Untuk mendukung mode gelap (seperti fitur theme-toggle di header logo sun/moon), skema warnanya membalik variabel primer:
- Latar Belakang ditiadakan dari `#f5f5f5` / White menjadi tema dominan `#1d1d1d` atau warna gelap menyesuaikan `oklch`. 
- Scrollbar default memancarkan desain base yang lebih gelap: track `#1d1d1d` dan thumb color `#a1a1a1` dengan border `#313131`.
- Perubahan properti ini dibuat dengan transisi: `transition: background .4s ease, color .4s ease`.

### Spacing & Layout
- `--v-space-1`: `4px`
- `--v-space-2`: `8px`
- `--v-space-3`: `12px`
- `--v-space-4`: `16px`

### Border Radius
- `--v-radius-sm`: `4px`
- `--radius`: `0.7rem`
- **Buttons**: `30px` (Pill shape), `100px` (Large pill)

### Animation Durations
- `--v-duration-fast`: `120ms`
- `--v-duration-normal`: `160ms`

---

## 2. Typography

Villume menggunakan font **Geist** sebagai *sans-serif* utama dan **Geist Mono** untuk monospace. *Anti-aliasing* diaktifkan secara maksimal untuk mempertajam 
teks (*text-rendering: optimizeLegibility*).

- **Font Sans**: `"Geist", -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif`
- **Font Mono**: `"Geist Mono", ui-monospace, "SF Mono", monospace`
- **Base Body Font Size**: `20px`
- **Base Line Height**: `136.5%`
- **Base Letter Spacing**: `-0.01em`

### Headings
Semua heading memiliki properti `font-weight: 400`, margin bottom `15px`, serta `letter-spacing: -0.01em`.

| Level | Font Size | Line Height |
|-------|-----------|-------------|
| **H1**  | `48px`    | `52px`      |
| **H2**  | `36px`    | `48px`      |
| **H3**  | `30px`    | `36px`      |
| **H4**  | `24px`    | `30px`      |
| **H5**  | `18px`    | `24px`      |

---

## 3. Components

### Base Focus State
Komponen dinamis (link, button) mengikuti garis fokus standar:
- **Ring Width**: `2px`
- **Ring Offset**: `2px`
- **Focus Shadow (Halo)**: `0 0 0 3px var(--halo)` 

### Buttons (`.btn`)
Tombol dirancang menggunakan bentuk oval (*pill shape*) menggunakan transisi mulus pada border, warna, latar, bayangan, dan transformasi letak (`translateY / scale`).

**1. Default Button (`.btn`)**
- **Height**: `60px`
- **Padding**: `12px 27.5px 8px`
- **Radius**: `30px`
- **Font Size**: `22px`
- **Active State**: `transform: translateY(1px) scale(0.99)`

**2. Primary Button (`.btn-primary`)**
- **Background**: `var(--primary)`
- **Color**: `var(--primary-foreground)`
- **Shadow**: `0 1px 2px hsl(var(--shadow-color)/.12), 0 8px 24px var(--halo)`
- **Hover State**: `filter: brightness(1.06)` dan shadow halo melebar menjadi `32px`.

**3. Small Button (`.btn-sm`)**
- **Height**: `40px`
- **Padding**: `3px 15px 0`
- **Font Size**: `16px`

**4. Large Button (`.btn-lg`)**
- **Height**: `94px`
- **Padding**: `9px 50px 5px`
- **Radius**: `100px`

---

## 4. Global CSS Resets & Behaviors
- **Scroll Behavior**: `smooth` (Jika perangkat tidak mengaktifkan *reduced motion*).
- **Scrollbar**: Kustom dengan thumb color `#a1a1a1`, border `3px solid #313131`, track color `#1d1d1d`, dan radius `100px`.
- **Background Transitions**: Body dipadukan dengan transisi perubahan background & color selama `400ms ease`.