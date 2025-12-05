# DayZ Server Settings With Bots

[![DayZ](https://img.shields.io/badge/DayZ-Server%20Config-blue.svg)](https://github.com/AristarhUcolov/DayZ-Server-Settings-With-Bots)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

🇬🇧 **English** | [🇷🇺 Русский](#русская-версия)

---

## 📋 Table of Contents

- [About](#about)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
  - [Server Configuration (serverDZ.cfg)](#server-configuration-serverdzcfg)
  - [Batch File (start.bat)](#batch-file-startbat)
- [Usage](#usage)
- [Video Tutorials](#video-tutorials)
- [Troubleshooting](#troubleshooting)
- [Additional Resources](#additional-resources)
- [License](#license)
- [Author](#author)

---

## 🎮 About

This repository contains pre-configured server settings and batch files for hosting a DayZ server with AI bots. Perfect for players who want to quickly set up a local or dedicated DayZ server with bot support.

The configuration includes:
- **serverDZ.cfg** - Main server configuration file
- **start.bat** - Automated server startup batch script
- Pre-configured mod support including AI expansion and community tools

---

## ✨ Features

- ✅ Pre-configured server settings optimized for bot gameplay
- ✅ Automated server restart script with crash recovery
- ✅ Support for popular mods:
  - CF (Community Framework)
  - Dabs Framework
  - DayZ-Expansion-AI
  - DayZ-Expansion-Core
  - Community-Online-Tools
- ✅ Configurable time acceleration
- ✅ BattlEye integration
- ✅ Detailed logging options
- ✅ Easy customization options

---

## 📦 Prerequisites

Before you begin, ensure you have:

1. **DayZ Server Files** - Install via Steam:
   - Open Steam Library
   - Go to "Tools" section
   - Search for "DayZ Server"
   - Download and install

2. **Required Mods** (if using):
   - CF (Community Framework)
   - Dabs Framework
   - DayZ-Expansion-AI
   - DayZ-Expansion-Core
   - Community-Online-Tools

3. **Windows OS** - The batch file is designed for Windows systems

---

## 🚀 Installation

1. **Clone or download this repository:**
   ```bash
   git clone https://github.com/AristarhUcolov/DayZ-Server-Settings-With-Bots.git
   ```

2. **Copy files to your DayZ Server directory:**
   - Copy `serverDZ.cfg` to your DayZ Server root folder
   - Copy `start.bat` to your DayZ Server root folder

3. **Download and install required mods** to your DayZ Server folder

4. **Configure the files** according to your setup (see Configuration section)

---

## ⚙️ Configuration

### Server Configuration (serverDZ.cfg)

Edit `serverDZ.cfg` to customize your server:

```cfg
hostname = "DayZ Local Server";  // Change to your server name
password = "";                    // Set password for players
passwordAdmin = "";               // Set admin password
maxPlayers = 1;                   // Maximum number of players
```

**Key Settings:**

| Setting | Description | Default Value |
|---------|-------------|---------------|
| `hostname` | Server name displayed in browser | "DayZ Local Server" |
| `maxPlayers` | Maximum concurrent players | 1 |
| `serverTimeAcceleration` | Time multiplier (0-24) | 12 |
| `disable3rdPerson` | Disable third-person view | 0 (enabled) |
| `disableCrosshair` | Disable crosshair | 0 (enabled) |

### Batch File (start.bat)

Edit `start.bat` to match your system:

```batch
set serverName=DayZ Local Server
set serverLocation="F:\SteamLibrary\steamapps\common\DayZServer"
set serverPort=2302
set serverConfig=serverDZ.cfg
set serverCPU=4
```

**Important Variables:**

| Variable | Description | Example |
|----------|-------------|---------|
| `serverLocation` | Path to DayZ Server installation | "F:\SteamLibrary\steamapps\common\DayZServer" |
| `serverPort` | Server port | 2302 |
| `serverCPU` | CPU cores to use | 4 |
| `timeout 14390` | Server restart timer (seconds) | 14390 (≈4 hours) |

**Mod Configuration:**

Modify the `-mod=` parameter to include your mods:
```batch
"-mod=@CF;@Dabs Framework;@DayZ-Expansion-AI;@DayZ-Expansion-Core;@Community-Online-Tools"
```

---

## 🎯 Usage

1. **Edit the configuration files** with your preferred settings
2. **Run `start.bat`** as Administrator
3. The server will:
   - Start automatically
   - Run for the configured time period (default: 4 hours)
   - Automatically restart to prevent crashes and memory leaks
4. **Connect to your server** using the IP `127.0.0.1:2302` (for local) or your public IP

### Stopping the Server

- Close the batch file window to stop the automatic restart cycle
- Or use Task Manager to end the `DayZServer_x64.exe` process

---

## 🎥 Video Tutorials

### Part 1: Basic Setup
[![Video Tutorial Part 1](https://github.com/user-attachments/assets/9df411d2-f197-4d2e-9754-ed6e4ea11220)](https://www.youtube.com/watch?v=9LN1nIzReow)

**Watch Tutorial:** [https://www.youtube.com/watch?v=9LN1nIzReow](https://www.youtube.com/watch?v=9LN1nIzReow)

### Part 2: Advanced Configuration
[![Video Tutorial Part 2](https://github.com/user-attachments/assets/dc1b3ad7-4937-444c-85ae-8694b3e32df5)](https://github.com/AristarhUcolov/DayZ-Server-Settings-With-Bots-2)

**GitHub Repository:** [DayZ-Server-Settings-With-Bots-2](https://github.com/AristarhUcolov/DayZ-Server-Settings-With-Bots-2)

---

## 🔧 Troubleshooting

### Server Won't Start

- **Check file paths** - Ensure `serverLocation` in `start.bat` points to correct directory
- **Verify mods** - Make sure all mods are properly installed
- **Check ports** - Ensure port 2302 (or your custom port) is not in use
- **Run as Administrator** - Right-click `start.bat` and select "Run as Administrator"

### Connection Issues

- **Firewall** - Add DayZ Server to Windows Firewall exceptions
- **Port Forwarding** - Forward port 2302 (UDP) on your router for external connections
- **BattlEye Path** - Verify BattlEye path in `start.bat` is correct

### Performance Issues

- **Reduce `serverCPU`** - Lower the CPU core count if experiencing issues
- **Disable unnecessary mods** - Remove mods you don't need
- **Increase restart timer** - Adjust `timeout` value in `start.bat`

### Mod Compatibility

- **Check mod versions** - Ensure all mods are up to date and compatible
- **Load order** - Order of mods in `-mod=` parameter can matter
- **Check logs** - Review server logs in the profiles folder for errors

---

## 📚 Additional Resources

### Spawn Location Values
The repository includes `value+usage - места для спавнов.txt` with spawn location values:
- Military, Police, Office
- Tier1, Tier2, Tier3, Tier4
- Industrial, Town, Village
- Medic, Firefighter, School

### License Information
The repository includes `Для тех у кого нету лицензий.txt` with information about running DayZ server with or without Steam license.

---

## 📄 License

This project is available for use under the MIT License. Feel free to use, modify, and distribute as needed.

---

## 👤 Author

**Aristarh Ucolov (Аристарх Уколов)**

- GitHub: [@AristarhUcolov](https://github.com/AristarhUcolov)
- Part 2 Repository: [DayZ-Server-Settings-With-Bots-2](https://github.com/AristarhUcolov/DayZ-Server-Settings-With-Bots-2)

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://github.com/AristarhUcolov/DayZ-Server-Settings-With-Bots/issues).

---

## ⭐ Support

If you found this helpful, please give it a ⭐ on GitHub!

---

<div id="русская-версия"></div>

# 🇷🇺 Русская Версия

## 📋 О Проекте

Этот репозиторий содержит предварительно настроенные файлы конфигурации сервера и батник для запуска DayZ сервера с ботами. Идеально подходит для игроков, которые хотят быстро настроить локальный или выделенный сервер DayZ с поддержкой ботов.

## ✨ Возможности

- ✅ Предварительно настроенные параметры сервера, оптимизированные для игры с ботами
- ✅ Автоматический скрипт перезапуска сервера с восстановлением после сбоев
- ✅ Поддержка популярных модов (CF, Dabs Framework, DayZ-Expansion-AI и др.)
- ✅ Настраиваемое ускорение времени
- ✅ Интеграция BattlEye
- ✅ Подробные параметры логирования

## 📦 Требования

1. **DayZ Server** - Установите через Steam (раздел "Инструменты")
2. **Необходимые моды** (если используете)
3. **Windows OS**

## 🚀 Установка

1. Скачайте или клонируйте репозиторий
2. Скопируйте `serverDZ.cfg` и `start.bat` в папку DayZ Server
3. Установите необходимые моды
4. Настройте файлы под вашу систему

## ⚙️ Настройка

### Файл serverDZ.cfg

Отредактируйте основные параметры:
- `hostname` - Имя сервера
- `password` - Пароль для входа
- `maxPlayers` - Максимальное количество игроков
- `serverTimeAcceleration` - Ускорение времени

### Файл start.bat

Измените следующие переменные:
- `serverLocation` - Путь к установке DayZ Server
- `serverPort` - Порт сервера (по умолчанию 2302)
- `serverCPU` - Количество используемых ядер процессора

## 🎯 Использование

1. Запустите `start.bat` от имени администратора
2. Сервер автоматически запустится и будет перезапускаться каждые 4 часа
3. Подключайтесь к серверу через IP: `127.0.0.1:2302` (локально)

## 🎥 Видео Уроки

### 1-я часть: Базовая настройка
**Ссылка:** [https://www.youtube.com/watch?v=9LN1nIzReow](https://www.youtube.com/watch?v=9LN1nIzReow)

### 2-я часть: Продвинутая настройка
**Репозиторий:** [DayZ-Server-Settings-With-Bots-2](https://github.com/AristarhUcolov/DayZ-Server-Settings-With-Bots-2)

## 🔧 Решение Проблем

### Сервер не запускается
- Проверьте пути к файлам в `start.bat`
- Убедитесь, что все моды установлены
- Запустите от имени администратора

### Проблемы с подключением
- Добавьте исключение в брандмауэр Windows
- Настройте проброс портов на роутере (порт 2302 UDP)
- Проверьте путь к BattlEye

## 📚 Дополнительные Файлы

- `value+usage - места для спавнов.txt` - Значения локаций для спавна предметов
- `Для тех у кого нету лицензий.txt` - Информация о запуске сервера без лицензии Steam

## 👤 Автор

**Аристарх Уколов (Aristarh Ucolov)**

---

**Если проект оказался полезным, поставьте ⭐ на GitHub!**
