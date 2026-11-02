# picalite-modules

Moteurs optionnels de [PicaLite](https://github.com/syl-craft/picalite), visionneuse de photos pour Windows.
PicaLite les télécharge à la demande depuis les releases de ce dépôt, vérifie leur taille et leur SHA-256
d'après `manifest.json`, puis les installe dans le profil de l'utilisateur.

| Module | Rôle dans PicaLite | Version | Licence |
|---|---|---|---|
| `magick` | Images que Windows ne décode pas (HEIC, RAW…) | Magick.NET-Q8-x64 14.17.2 | licence ImageMagick (dérivée d'Apache 2.0) et celles des bibliothèques listées dans `Notice.txt`, dont libheif, libde265 et LibRaw sous LGPL |
| `ffmpeg` | Vignettes et informations des vidéos | FFmpeg, build BtbN LGPL shared du 2026-11-01 | LGPL 2.1 ou ultérieure |
| `vlc` | Lecture des vidéos | libvlc 3.0.21 (VideoLAN) | LGPL 2.1 ; greffons sous GPL et greffons inutiles à la lecture retirés |

## Contenu d'une release

- `manifest.json` : liste cumulative des modules (nom, version, adresse, taille, SHA-256, versions de PicaLite compatibles).
- `picalite-module-<nom>-<version>-x64.zip` : les fichiers du moteur et ses textes de licence.
- Les archives sources correspondantes, telles que publiées par leurs projets, avec leurs SHA-256 dans
  [`sources/sources.json`](sources/sources.json).

Les textes de licence sont dans [`LICENSES/`](LICENSES) et dans chaque archive de module.
Les binaires ne sont pas modifiés ; seuls des greffons de VLC sont écartés du module. Ils proviennent des paquets officiels indiqués dans `sources/sources.json`.
