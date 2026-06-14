# clite — command line task engine

`clite` — CLI-клиент для AI-first таск-трекера [apitracker.ru](https://apitracker.ru).

Этот репозиторий используется для дистрибуции бинарей; исходный код CLI живёт в приватном monorepo [`gaev-tech/api-tracker`](https://github.com/gaev-tech/api-tracker).

Последний релиз — [GitHub Releases](https://github.com/gaev-tech/clite/releases/latest).

## Установка

### macOS (Apple Silicon)

```bash
curl -L https://github.com/gaev-tech/clite/releases/latest/download/clite-darwin-arm64 -o /usr/local/bin/clite
chmod +x /usr/local/bin/clite
clite --version
```

### macOS (Intel)

```bash
curl -L https://github.com/gaev-tech/clite/releases/latest/download/clite-darwin-amd64 -o /usr/local/bin/clite
chmod +x /usr/local/bin/clite
```

### Linux (amd64)

```bash
curl -L https://github.com/gaev-tech/clite/releases/latest/download/clite-linux-amd64 -o ~/.local/bin/clite
chmod +x ~/.local/bin/clite
```

### Windows (amd64)

```powershell
Invoke-WebRequest -Uri https://github.com/gaev-tech/clite/releases/latest/download/clite-windows-amd64.exe -OutFile clite.exe
```

## Дополнительные каналы установки (с M4)

- **PyPI**: `pipx install clite`
- **Homebrew**: `brew install gaev-tech/clite/clite`
- **APT**: см. [apt.apitracker.ru](https://apt.apitracker.ru)
- **npm**: `npm install -g @gaev-tech/clite` или `npx @gaev-tech/clite ...`

## Документация

- [apitracker.ru](https://apitracker.ru) — справка по CLI, RSQL, схеме данных, туториалы
- `clite --help` — справка прямо в CLI

## Быстрый старт

```bash
clite login                                       # вход по email + magic-code
clite task create --title "Моя первая задача"
clite task list --filter "status==open"
clite task list --filter 'assignee==me;labels=in=(bug)'
```

## Поддержка

Issues и feature requests — в этом репозитории.
Production-проблемы — на admin@apitracker.ru.

## Проверка артефакта

После установки сравните SHA256 артефакта с `.sha256` файлом из релиза:

```bash
shasum -a 256 clite-darwin-arm64
# должен совпасть с содержимым clite-darwin-arm64.sha256
```
