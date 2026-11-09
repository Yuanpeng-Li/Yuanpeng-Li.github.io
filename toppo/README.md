# toppo/ is a static build

This folder is the TOPPO project page as built HTML, CSS, JavaScript and
images. The source it was built from has been retired, so there is nothing to
regenerate it from: to change the page, edit `index.html` directly.

`assets/` holds the stylesheet, the script for the interactive gradient
figure, and each figure in several sizes and formats; the hashed file names
are referenced from `index.html`, so rename a file there too.

Jekyll copies `index.html` as it is (it has no front matter); this README is
listed under `exclude` in `_config.yml`, so it is not published.
