# Custom Launcher — Distribution Repository

This repository is the **distribution channel** for a third-party launcher for
Minecraft: Java Edition. The launcher reads the modpack and server settings
from here.

> Not an official Minecraft product. Not approved by or associated with
> Mojang Studios or Microsoft.

## Repository layout

| Item | Purpose |
|---|---|
| `manifest.json` | Server address, current modpack version, notices, background image |
| Releases (`modpack-v{n}`) | Modpack zip for each version, plus `modpack.json` holding its SHA256 checksum and loader info |

The launcher reads `manifest.json` to find the current version, downloads that
release, verifies the SHA256 checksum, and installs it.

## What the launcher does

- Installs and updates the modpack (version selectable, SHA256 verified)
- Installs the mod loader automatically (Fabric / Forge / NeoForge)
- Provisions a Java runtime automatically (Adoptium)
- Shows server status and connects directly to the server

## Authentication and ownership

Players sign in with **their own Microsoft account**. Only an account that owns
Minecraft: Java Edition can launch the game.

- OAuth 2.0 device code flow with the `XboxLive.signin` scope
- Refresh tokens are stored **only in the operating system credential store**
  (Windows Credential Manager) and never leave the user's machine. No
  credentials are transmitted to any server we operate
- There is **no offline mode and no authentication bypass** of any kind

## Game files

The launcher does **not** include or redistribute any Minecraft game files,
assets, or paid content. The client jar, libraries, and assets are downloaded at
runtime directly from the official Mojang/Microsoft endpoints.

The modpack archives published here contain only mods and configuration files —
no Minecraft game files.

---

# 커스텀 런처 — 배포 저장소

이 저장소는 마인크래프트: 자바 에디션용 서드파티 런처의 **배포 채널**입니다.
런처가 여기서 모드팩과 서버 설정을 받아갑니다.

| 항목 | 역할 |
|---|---|
| `manifest.json` | 서버 주소, 현재 모드팩 버전, 공지, 배경화면 |
| Releases (`modpack-v{n}`) | 각 버전의 모드팩 zip + 체크섬·로더 정보를 담은 `modpack.json` |

**런처 기능** — 모드팩 설치·갱신(버전 선택, SHA256 검증), 모드로더 자동 설치,
Java 런타임 자동 준비, 서버 상태 표시 및 바로 접속.

**인증** — 본인의 Microsoft 계정으로 로그인하며, 마인크래프트를 소유한 계정만
실행할 수 있습니다. 리프레시 토큰은 OS 자격증명 저장소에만 저장되고 PC를
벗어나지 않습니다. 오프라인 로그인이나 인증 우회 경로는 없습니다.

**게임 파일** — 런처는 마인크래프트 게임 파일·에셋을 포함하거나 재배포하지
않습니다. 실행 시점에 Mojang/Microsoft 공식 엔드포인트에서 직접 받습니다.

이 프로젝트는 Mojang Studios 및 Microsoft와 무관하며, 공식 제품이 아닙니다.
