# elusivebot-docs

## Requirements

Python3 and a modern JVM must be installed.

## Installation

- Create a Python virtual environment using `python3 -m venv venv`
- Activate the environment with `source venv/bin/activate`
- Install the dependencies `pip3 install -r requirements.txt`
- Install the pre-commit hook `pre-commit install`

## Usage

### Local

Run `./bin/serve` and view the results at
[http://localhost:8080/](http://localhost:8080/).  Changes will
auto-refresh.  Run `./bin/watch-diagrams` to auto-refresh the
PlantUML diagrams.

### Build

Run `./bin/build`, which will generate the diagrams and the static
HTML.  The full website will be available at `<REPOSITORY>/site/`.

## Appendex

- https://squidfunk.github.io/mkdocs-material/
- https://plantuml.com/
- https://github.com/tupadr3/plantuml-icon-font-sprites
- https://github.com/gorakhargosh/watchdog
