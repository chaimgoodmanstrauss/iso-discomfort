# Iso-Discomfort Surfaces

Single-file WebGL-free canvas app: iso-discomfort ("feels like") surfaces over
NYC summer temperature × relative humidity, with a running-pace exertion offset.
No external libraries — everything is computed and drawn locally.

## Files

- `iso_discomfort.html` — the app. Deployed to
  `https://chaimgoodmanstrauss.com/iso_discomfort.html`.
- `myindex.html` — hand-rolled index of all homegrown apps on
  chaimgoodmanstrauss.com. Deployed to
  `https://chaimgoodmanstrauss.com/myindex.html`.

## "Now" dot

`iso_discomfort.html` fetches current NYC conditions once on load from
Open-Meteo (`api.open-meteo.com`, no API key, CORS-open) and plots a labelled
"now" marker on the chart at the observed (temp, RH). If the observation falls
outside the chart box it's clamped to the nearest edge and a note says so. If
the fetch fails the app still works; the dot is just omitted.

## Deploy

SFTP only (shared cPanel host). Credentials in `~/.symmetrystroller_deploy.env`
(outside any repo). Both files sit at the domain web root, `public_html/`:

    sftp -> put iso_discomfort.html public_html/iso_discomfort.html
    sftp -> put myindex.html       public_html/myindex.html
