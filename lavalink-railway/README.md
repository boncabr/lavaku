# Lavalink v4 - Railway Deployment

Self-hosted Lavalink v4 server with YouTube plugin, LavaSrc, and LavaLyrics.

## Plugins Included
- **youtube-plugin** v1.11.4 — YouTube support (pengganti source bawaan)
- **lavasrc** v4.4.0 — Spotify, Apple Music, Deezer, Yandex Music
- **lavalyrics** v1.0.0 — Lyrics support

## Deploy ke Railway

1. Push repo ini ke GitHub
2. Buka [railway.app](https://railway.app) → New Project → Deploy from GitHub repo
3. Pilih repo ini
4. Railway otomatis deteksi `Dockerfile` dan build
5. Tambahkan variable berikut di tab **Variables**:

## Railway Variables

| Variable | Value | Keterangan |
|---|---|---|
| `_JAVA_OPTIONS` | `-Xmx512m` | **Wajib** — batasi RAM Java agar tidak crash |
| `LAVALINK_SERVER_PASSWORD` | `password_kamu` | Opsional — ganti password tanpa edit file |

> Jika pakai `LAVALINK_SERVER_PASSWORD`, ubah baris password di `application.yml` menjadi:
> ```yaml
> password: ${LAVALINK_SERVER_PASSWORD:youshallnotpass}
> ```

## Konfigurasi Koneksi Bot

| Setting | Value |
|---|---|
| Host | `your-app.railway.app` |
| Port | `443` |
| Password | `youshallnotpass` |
| Secure (SSL) | `true` |

> **Ganti password** di `application.yml` sebelum deploy!

## Ganti Password

Edit baris ini di `application.yml`:
```yaml
password: "password_kamu_disini"
```

## Sources yang Aktif

| Source | Status |
|---|---|
| YouTube | ✅ (via plugin) |
| SoundCloud | ✅ |
| Bandcamp | ✅ |
| Twitch | ✅ |
| Vimeo | ✅ |
| HTTP streams | ✅ |
| Spotify | ✅ (via LavaSrc, butuh credentials) |
