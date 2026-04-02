# Table of contents

- [Table of contents](#table-of-contents)
- [VR Payment Android Payment SDK](#vr-payment-android-payment-sdk)
  - [Installation](#installation)
- [VR-Payment Checkout Android SDK — Migration Guide v2.0.0](#vr-payment-checkout-android-sdk--migration-guide-v200)
  - [Requirements](#requirements)
  - [Installation](#installation-1)
  - [What's new](#whats-new)
  - [Breaking change — Entry class renamed](#breaking-change--entry-class-renamed)
  - [Migration](#migration)
    - [1. Update the import](#1-update-the-import)
    - [2. Update initialization](#2-update-initialization)
  - [Summary](#summary)
  - [Documentation](#documentation)

# VR Payment Android Payment SDK

[![Maven Central](https://img.shields.io/maven-central/v/de.vr-payment/vr-payment)](https://central.sonatype.com/artifact/de.vr-payment/vr-payment/1.5.2)

## Installation

# VR-Payment Checkout Android SDK — Migration Guide v2.0.0

## Requirements

|                             | Version |
| --------------------------- | ------- |
| Kotlin                      | 2.1.20  |
| Android Gradle Plugin (AGP) | 8.7.0   |

## Installation

Latest version: **2.0.0** — [Maven Central](https://central.sonatype.com/artifact/de.vr-payment/vr-payment)

Add the dependency to your `build.gradle.kts`:

```kotlin
implementation("de.vr-payment:vr-payment:2.0.0")
```

---

## What's new

Version 2.0.0 brings a complete architectural overhaul of the SDK. The public API and component behavior remain unchanged — the only breaking change is the **entry class rename**.

The architecture has also been updated to comply with the **Android 16KB page size alignment requirement**, ensuring compatibility with devices running on 16KB memory page sizes as required by Google. For more details, see the [official Android documentation](https://developer.android.com/guide/practices/page-sizes).

> **Still seeing 16KB alignment issues in your app?**
> The problem may be caused by other libraries or an outdated build toolchain in your project. We recommend upgrading to **AGP 8.7.0 or higher** and updating your other dependencies to their latest versions.

---

## Breaking change — Entry class renamed

The main entry class has been renamed:

| v1.x           | v2.0.0      |
| -------------- | ----------- |
| `VRPaymentSdk` | `VRPayment` |

Update your import and all references accordingly.

---

## Migration

### 1. Update the import

```kotlin
// Before
import de.vr-payment.VRPaymentSdk

// After
import ch.vr-payment.VRPayment
```

### 2. Update initialization

```kotlin
VRPayment.init(...)
...
VRPayment.instance?.launch(...)
```

---

## Summary

No logic or API changes — only find & replace `VRPaymentSdk` → `VRPayment` across your codebase.

## Documentation

- [API Reference](./docs/api-reference.md)
- [Integration](./docs/integration.md)
- [Theming](./docs/theming.md)
- [Troubleshooting](./docs/troubleshooting.md)
