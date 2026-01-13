# Valhalla-docs
Avledet dedicated server documentation

## Windows

super simple install via pip

## Linux

Create pip venv `python3 -m venv mkdocs-venv`

Use as source for terminal `source mkdocs-venv/bin/activate`

Clone Avledet to ~ `git clone https://github.com/ricosolana/Valhalla-docs`

Start mkdocs server `cd Valhalla-docs $$ mkdocs serve --livereload`

*Note* `--livereload`: https://github.com/nautobot/nautobot/pull/8115

View server in browser `http://127.0.0.1:8000/` or whatever serve displays
