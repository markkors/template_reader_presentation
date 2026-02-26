# Jekyll Lokale Server Installatie

Dit project gebruikt Jekyll om pagina's lokaal te serveren. Hieronder staan de stappen om Jekyll op een nieuwe PC in te stellen.

---

## Windows

### 1. Installeer Ruby + Devkit

- Download van [rubyinstaller.org](https://rubyinstaller.org/downloads/) de versie **Ruby+Devkit** (aanbevolen: nieuwste stabiele versie, bijv. 3.3.x)
- Tijdens installatie: vink **"Add Ruby executables to your PATH"** aan
- Aan het einde van de installer: laat de MSYS2-installatie lopen (druk op Enter voor optie 1, daarna nogmaals voor optie 3)

### 2. Installeer Bundler

```bash
gem install bundler
```

### 3. Installeer de projectafhankelijkheden

Navigeer naar de projectmap en installeer de gems:

```bash
cd "pad\naar\Javascript"
bundle install
```

### 4. Start de lokale server

```bash
bundle exec jekyll serve --livereload
```

Of dubbelklik op `start_local_server.bat`.

---

## Linux (Ubuntu/Debian)

### 1. Installeer Ruby en build-tools

```bash
sudo apt update
sudo apt install ruby-full build-essential zlib1g-dev
```

### 2. Configureer het gem-pad (zonder sudo)

```bash
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

### 3. Installeer Bundler

```bash
gem install bundler
```

### 4. Installeer de projectafhankelijkheden

Navigeer naar de projectmap en installeer de gems:

```bash
cd /pad/naar/Javascript
bundle install
```

### 5. Start de lokale server

```bash
bundle exec jekyll serve --livereload
```

---

## De site bekijken

Na het starten is de site beschikbaar op:

**http://localhost:4000/Javascript_tutorial/**

> Let op: de `baseurl` is ingesteld op `/Javascript_tutorial`, dus de root `/` geeft een lege pagina. Open altijd het volledige pad hierboven.

---

## Overzicht vereisten

| Wat | Waarom |
|-----|--------|
| Ruby (3.x) | Taal waarop Jekyll draait |
| Devkit / build-essential | Compileert native gems (bijv. `wdm`, `nokogiri`) |
| Bundler | Beheert gem-versies via de `Gemfile` |
| `bundle install` | Installeert `github-pages`, `jekyll`, `webrick` etc. |
