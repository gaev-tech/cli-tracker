# apit — api-tracker CLI

`apit` — CLI-клиент для AI-first таск-трекера [apitracker.ru](https://apitracker.ru).

Этот репозиторий используется для distribution бинарей; исходный код CLI живёт в приватном monorepo [`gaev-tech/api-tracker`](https://github.com/gaev-tech/api-tracker).

## Установка

### macOS (Apple Silicon)

```bash
curl -L https://github.com/gaev-tech/cli-tracker/releases/latest/download/apit-darwin-arm64 -o /usr/local/bin/apit
chmod +x /usr/local/bin/apit
apit --version
```

### macOS (Intel) — с M2

```bash
curl -L https://github.com/gaev-tech/cli-tracker/releases/latest/download/apit-darwin-amd64 -o /usr/local/bin/apit
chmod +x /usr/local/bin/apit
```

### Linux (amd64) — с M2

```bash
curl -L https://github.com/gaev-tech/cli-tracker/releases/latest/download/apit-linux-amd64 -o ~/.local/bin/apit
chmod +x ~/.local/bin/apit
```

### Windows (amd64) — с M2

```powershell
Invoke-WebRequest -Uri https://github.com/gaev-tech/cli-tracker/releases/latest/download/apit-windows-amd64.exe -OutFile apit.exe
```

## Дополнительные каналы установки (с M4)

- **PyPI**: `pipx install apit`
- **Homebrew**: `brew install gaev-tech/cli-tracker/apit`
- **APT**: см. [apt.apitracker.ru](https://apt.apitracker.ru)
- **npm**: `npm install -g @gaev-tech/cli-tracker` или `npx @gaev-tech/cli-tracker ...`

## Документация

- [apitracker.ru](https://apitracker.ru) — справка по CLI, RSQL, схеме данных, туториалы
- [`apit --help`](https://apitracker.ru/cli) — справка прямо в CLI

## Быстрый старт

```bash
apit login                  # с M2; в M0/M1 авторизация выключена
apit task create --title "Моя первая задача"
apit task list --filter "status==open"
apit task list --filter 'assignee==me;labels=in=(bug)'
```

## Поддержка

Issues и feature requests — в этом репозитории.
Production-проблемы — на admin@apitracker.ru.

## Verification

После установки сравните SHA256 артефакта с `.sha256` файлом из релиза:

```bash
shasum -a 256 apit-darwin-arm64
# должен совпасть с apit-darwin-arm64.sha256
```

