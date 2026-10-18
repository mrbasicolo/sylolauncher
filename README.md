<p align="center">
  <img src="assets/branding/logo.png" alt="SYLO" width="160">
</p>

# SYLO

**🇮🇹 Italiano** · [🇬🇧 English below](#english)

SYLO è un progetto gratuito e non commerciale: un launcher desktop e un client in-game (mod Fabric) per **Minecraft: Java Edition 1.21.11**. Interfaccia in italiano, stile minimalista "Ice Blue".

> **Stato: sviluppo iniziale.** Non è ancora utilizzabile per giocare. Niente di quanto elencato come "non implementato" è presente.
> SYLO **non è affiliato a Mojang, Microsoft o Minecraft**.

## Principi

- **Accesso legittimo.** Per giocare serve un account Microsoft che possiede Minecraft Java Edition. L'accesso usa il flusso ufficiale Microsoft → Xbox Live → XSTS → Minecraft Services.
- **Nessuna modalità offline, nessun aggiramento** di autenticazione, licenza o controlli di sicurezza. Non verranno aggiunti.
- **Token protetti.** I token saranno conservati nel Credential Manager di Windows e non compariranno nei log né nell'interfaccia. Nessuna password viene salvata.
- **Nessuna telemetria né analytics.**
- **Codice e grafica originali.** Il logo è quello ufficiale di SYLO.

## Tecnologie

Launcher: Tauri 2, React, TypeScript, Vite, Rust. Mod: Java 21, Fabric (previsto, Gradle + Loom).

## Stato dei componenti

| Componente | Stato | Verifica |
|---|---|---|
| Logica core Rust (impostazioni, validazione, stato installazione) | implementata | 11 test automatici superati |
| Motore di avvio (regole librerie, profilo Fabric, classpath, argomenti, token oscurato nei log, SHA-1) | implementato, non ancora collegato al pulsante | 5 test su dati di esempio; non provato su dati reali né su un avvio vero |
| Frontend (5 sezioni, impostazioni, stati di caricamento/errore) | implementato | `tsc` e `vite build` superati |
| App desktop Tauri | scritta | **non ancora compilata né avviata** |
| Login Microsoft | non implementato | richiede l'approvazione dell'AppID da parte di Mojang |
| Installazione di Minecraft e Fabric, avvio di Minecraft | non implementati | — |
| Mod client Fabric (menu, HUD, moduli) | non iniziata | — |

I pulsanti GIOCA, login e installazione sono disattivati e indicano il motivo.

## Documentazione

- [`docs/setup.md`](docs/setup.md): prerequisiti e avvio in sviluppo (Windows 11)
- [`docs/phase1-analysis.md`](docs/phase1-analysis.md): analisi tecnica e versioni
- [`docs/roadmap.md`](docs/roadmap.md): roadmap e blocchi aperti

---

<a id="english"></a>

## English

SYLO is a free, non-commercial project: a desktop launcher and an in-game client (Fabric mod) for **Minecraft: Java Edition 1.21.11**. Italian UI, minimalist "Ice Blue" style.

> **Status: early development.** It cannot be used to play yet. Anything listed as "not implemented" below does not exist yet.
> SYLO is **not affiliated with Mojang, Microsoft or Minecraft**.

### Principles

- **Legitimate access only.** Playing requires a Microsoft account that owns Minecraft: Java Edition. Sign-in uses the official Microsoft → Xbox Live → XSTS → Minecraft Services flow.
- **No offline mode and no bypass** of authentication, license or safety checks. None will be added.
- **Tokens are protected.** They will be stored in the Windows Credential Manager and never written to logs or shown in the UI. No password is stored.
- **No telemetry or analytics.**
- **Original code and artwork.**

### Technology

Launcher: Tauri 2, React, TypeScript, Vite, Rust. Mod: Java 21, Fabric (planned, Gradle + Loom).

### Component status

| Component | Status | Verification |
|---|---|---|
| Rust core (settings, validation, install status) | implemented | 11 automated tests pass |
| Launch engine (library rules, Fabric profile, classpath, arguments, redacted token, SHA-1) | implemented, not wired to the button yet | 5 tests on sample data; not tried on real data or a real launch |
| Frontend (5 sections, settings, loading/error states) | implemented | `tsc` and `vite build` pass |
| Tauri desktop app | written | **not compiled or run yet** |
| Microsoft sign-in | not implemented | needs AppID approval by Mojang |
| Minecraft and Fabric installation, game launch | not implemented | — |
| Fabric client mod (menu, HUD, modules) | not started | — |

### Purpose of the Microsoft AppID

SYLO needs an approved AppID only to let a user sign in with their own Microsoft account, confirm that the account owns the game, and launch it. It does not access any other data.
