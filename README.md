<div align="center">

<img src="https://img.shields.io/badge/Unity-2021.3%2B-black?style=for-the-badge&logo=unity&logoColor=white"/>
<img src="https://img.shields.io/badge/C%23-Professional-blue?style=for-the-badge&logo=csharp"/>
<img src="https://img.shields.io/badge/License-Commercial-red?style=for-the-badge"/>
<img src="https://img.shields.io/badge/Asset%20Store-Available-brightgreen?style=for-the-badge"/>

<br/><br/>

# 🎮 FPS Kit
### Professional First-Person Shooter System for Unity

**Plug-and-play FPS framework. No third-party dependencies. One click setup.**

<br/>

[![Asset Store](https://img.shields.io/badge/🛒%20Buy%20on%20Unity%20Asset%20Store-$24.99-orange?style=for-the-badge)](https://assetstore.unity.com)

<br/>

</div>

---

## ✨ What's Included

### 🧍 Character Controller
- Walk, sprint, crouch, slide — smooth transitions between all states
- Advanced jump system with **coyote time**, **jump buffering**, optional double jump
- Full **stamina system** with configurable drain and delayed regeneration
- Dynamic **head bobbing** based on movement speed and state
- **Surface-aware footsteps** — concrete, grass, metal auto-detected via raycast
- Slope handling, step height, fall multiplier, terminal velocity

### 📷 Camera System
- Smooth mouse look with per-axis sensitivity, invert Y, and input smoothing
- **Trauma-based camera shake** using Perlin noise (non-linear, cinematic feel)
- **Per-weapon recoil patterns** — define exactly how each weapon kicks
- Q / E **lean system** with wall collision detection
- Breath sway, movement tilt, sprint / ADS **FOV transitions**

### 🔫 Weapon System
- Three fire modes: **Semi-Auto, Full-Auto, Burst**
- Two shoot modes: **Hitscan** and **Projectile**
- Damage falloff over distance + **headshot multiplier**
- Normal and **tactical reload** (bullet-in-chamber aware), cancelable reload
- **Valorant-style recoil pattern list** — fully editable in the Inspector
- Spread per shot, ADS accuracy bonus, automatic recovery
- Muzzle flash, shell ejection, **bullet tracers**, surface impact effects
- Optional **overheat system** with smoke effect and cooldown

### 🎒 Weapon Manager
- Unlimited weapon slots
- Scroll wheel, number keys, **Q quick-switch**
- Holster / draw animations with configurable timing
- World **pickup & drop** system via `WeaponPickup` component

### 🚀 One-Click Demo Builder
A custom Editor tool builds a **fully playable demo scene** in one click:
- FPS Player prefab with all components wired
- Complete environment (walls, cover, crates, pillars, ramps, platforms)
- Animated target dummies with health bars, damage numbers, respawn
- Full HUD (ammo, HP, stamina, crosshair, kill feed, stats)
- Proper lighting and fog

---

## 📸 Screenshots

> *Screenshots will be added after the demo scene is built.*

---

## 🎮 Controls

| Key | Action |
|---|---|
| `W A S D` | Move |
| `Mouse` | Look |
| `Left Click` | Fire |
| `Right Click` | ADS (Aim Down Sights) |
| `Space` | Jump |
| `Left Shift` | Sprint |
| `Left Ctrl` | Crouch / Slide (while sprinting) |
| `R` | Reload |
| `Q / E` | Lean Left / Right |
| `1–9 / Scroll` | Switch Weapon |
| `G` | Drop Weapon |

---

## ⚙️ Technical Details

| Property | Value |
|---|---|
| Unity Version | 2021.3 LTS+ |
| Render Pipeline | Built-in, URP, HDRP |
| Platforms | Windows, macOS, Linux, iOS, Android, WebGL |
| Dependencies | **None** |
| Input System | Legacy (New Input System: see docs) |
| Scripts | 8 C# files, ~2,300 lines |

---

## 🧩 API Highlights

```csharp
// Camera shake (explosions, impacts)
cameraController.AddTrauma(0.6f);

// Apply weapon recoil
cameraController.ApplyRecoil(vertical: 1.5f, horizontal: 0.2f);

// Any object can take damage — just implement IDamageable
public class Enemy : MonoBehaviour, IDamageable
{
    public void TakeDamage(float damage, Vector3 hitPoint,
                           Vector3 hitNormal, string hitTag)
    {
        health -= damage;
        if (health <= 0f) Die();
    }
}

// Weapon events
weapon.OnAmmoChanged  += (cur, res) => UpdateAmmoUI(cur, res);
weapon.OnHit          += (dmg, hit)  => ShowDamageNumber(dmg, hit.position);
weapon.OnReloadStart  += ()          => ShowReloadIndicator();
```

---

## 📦 What You Get

```
Assets/FPSKit/
├── Scripts/
│   ├── Character/    → CharacterController_FPS.cs
│   ├── Camera/       → FPSCameraController.cs
│   ├── Weapon/       → WeaponController.cs + WeaponManager.cs
│   ├── UI/           → DemoHUD.cs
│   └── Demo/         → DemoTarget.cs + DemoPlayerHealth.cs
├── Editor/           → FPSKitBuilder.cs  ← One-click scene generator
└── Documentation/    → README + Setup Guide
```

---

## 🛒 Purchase

> **This asset is sold exclusively on the Unity Asset Store.**  
> Source code is not available in this repository.

<div align="center">

[![Buy on Unity Asset Store](https://img.shields.io/badge/🛒%20Buy%20Now%20—%20Unity%20Asset%20Store-$24.99-orange?style=for-the-badge)](https://assetstore.unity.com)

</div>

---

## 📬 Support

| Channel | Link |
|---|---|
| 📧 Email | your-email@domain.com |
| 💬 Unity Forum | unity.com/community |
| 🐛 Bug Reports | [Open an Issue](../../issues) |
| 📖 Documentation | Included in the package |

---

## 📄 License

This asset is **proprietary commercial software**.  
See [LICENSE](LICENSE) for full terms.

**Source code is not included in this repository.**  
Purchase on the [Unity Asset Store](https://assetstore.unity.com) to obtain a license.
