# Something™ website archive

A static rebuild of something.global, made from a full-site backup. No CMS, no build step: plain HTML, CSS and JavaScript.

## What's here

- `index.html`, `p2.html` to `p4.html`: projects grid (infinite scroll loads the extra pages)
- `info.html`: studio info
- `projects/`: case studies and category filter pages
- `policy/`: privacy and cookie policies
- `media/`: all images, one full-size copy each
- `cdn/`: the original site CSS, JavaScript and Lab Grotesque webfonts

## Changes from the live site

- Images served locally instead of from the AWS image handler
- Removed the cookie banner, Cloudflare analytics and the unused Formie form plugin
- Project cards whose pages weren't in the backup (several Johnnie Walker, Ketel One, Singleton, Zacapa and World Class List projects) are kept in the grid but no longer link anywhere
- Still images now show underneath the hover and autoplay videos as a fallback

## Videos

The backup didn't include the videos, and the CloudFront they streamed from is offline (the AWS account is suspended).
Pages now look for each video at `media/video/<folder>/<original filename>.mp4` (see `videos.txt` for the full list).
Any video that is missing is hidden automatically and its still image shows instead.
To restore them, drop the original files into those paths. No code changes needed.

## Viewing locally

```
python3 -m http.server
```
then open http://localhost:8000
