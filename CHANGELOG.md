# WALLNODE desktop

What changed, newest first. One section per released version, and the top
section is what `release.ps1` puts into the GitHub release and onto
[wallnode.cc/app](https://wallnode.cc/app). Written as things a person noticed,
not as commits.

## 1.0.1 (2026-08-23)

- History tiles find their cached thumbnail again. They were looked up under the
  filename the cache stopped using when thumbnails gained a version, so the view
  had only ever drawn wallpapers whose full-resolution file was still on disk.
- Clicking a history entry opens the real record: preview, resolution, credits
  and like state, instead of an empty preview and half a header.
- A history wallpaper with nothing cached anywhere now fetches its preview from
  the archive rather than showing nothing.
- The mark stops spinning when there is nothing left to wait for. A loader still
  turning under "NO PREVIEW AVAILABLE" was claiming something was still coming.
- A database outage on the server no longer produces an endless stack of error
  dialogs. `wallpapers.php` answers 200 with no wallpapers list when the
  database is down, and every rotation tick threw on it.

## 1.0.0 (2026-08-23)

First packaged release. Previously the app was a bare 81MB exe to put wherever
you liked.

- An installer: Start menu entry, an entry in Settings > Apps, and a defined
  home in `%LOCALAPPDATA%\Programs\Wallnode`. Per-user, so no admin prompt.
- Uninstalling never deletes the wallpaper currently on your desktop, and asks
  before removing settings and sign-in.
- Browse the archive, set a wallpaper at your screen's native resolution, rotate
  from a series, category, artist, your likes or a search.
