# E2EE-Lite

**为 Android App 提供端到端加密能力的轻量级库**

[![License](https://img.shields.io/badge/License-MIT-green)]()
[![Platform](https://img.shields.io/badge/Platform-Android-blue)]()
[![API](https://img.shields.io/badge/API-21%2B-brightgreen)]()

---

## 快速开始

### 1. 添加依赖

```gradle
dependencies {
    implementation 'com.e2eelite:e2ee-lite:1.0.0'
}
```

### 2. 初始化

```kotlin
// Application 中初始化一次
E2EE.initialize(this)
```

### 3. 生成密钥

```kotlin
val keyPair = E2EE.generateKeyPair("my_key")
```

### 4. 加密

```kotlin
val encrypted = E2EE.encrypt("Hello", recipientPublicKey)
```

### 5. 解密

```kotlin
val decrypted = E2EE.decrypt(encrypted, myPrivateKey)
```

---

## API

| 方法 | 说明 |
|------|------|
| `initialize(context)` | 全局初始化 |
| `generateKeyPair(alias)` | 生成密钥对 |
| `encrypt(text, publicKey)` | 加密消息 |
| `decrypt(cipher, privateKey)` | 解密消息 |

---

## 性能

| 操作 | 耗时 |
|------|------|
| 密钥生成 | ~35ms |
| 加密 (1KB) | ~1.8ms |
| 解密 (1KB) | ~1.9ms |

---

## 安全

- AES-256-GCM + ECDH
- Android Keystore 硬件保护
- 零外部依赖

---

## 系统要求

- Android 5.0+ (API 21)

---

## License

MIT

---

**GitHub**: [SamTang0/E2EE-Lite](https://github.com/SamTang0/E2EE-Lite)
