# Game Lab 4: ผจญภัยป่าเวทมนตร์ (Mystic Forest Escape)

**รหัสนักศึกษา:** 673380637-7
**ชื่อ-สกุล:** มนัสนันท์ จันดาเวียง

**Game Story** — นักผจญภัยหลงเข้าไปในป่าลึกลับที่ถูกสาป ต้องหลบกับดักใบมีดและหอกแกว่ง
เก็บไอเทมเวทมนตร์ (ไม้กายสิทธิ์เร่งความเร็ว, แสงเวทเพิ่มพลังกระโดด, ยาแดงฟื้นพลังชีวิต)
เพื่อเอาชนะเห็ดพิษและสไลม์ แล้วเดินทางผ่าน 4 ด่าน ไปให้ถึงประตูมิติเพื่อกลับบ้าน

**Game Style** — พิกเซลอาร์ตแนวแฟนตาซี โทนสีป่าไม้เขียว-ม่วง

โครงการนี้ต่อยอดจาก 2D Platformer Starter Kit ของวิชา **Computer Game Development**
**College of Computing, Khon Kaen University**

## Preview

<img src="docs/demo1.jpg" width="300">
<img src="docs/demo2.jpg" width="300">

- [Game Preview](https://manatsanancha-sys.github.io/GameLab4/)
- [Demo VDO](https://drive.google.com/drive/folders/12XrgxQdmw0Q6GZZ9ahRpEPAYJjzY_HVz?usp=sharing)

## Features

- **Game Menu** — เมนูหลักพร้อมปุ่ม Start, Continue, Option, Credit และ Exit
- **Mobile & Web Design** — เล่นได้ทั้งบนคอมและมือถือผ่านปุ่มสัมผัสบนจอ
- **Platformer Controller** — เดิน กระโดด รองรับ Double Jump ปรับค่าได้จาก Inspector
- **Weapon System** — ยิงกระสุนแบบมีฟิสิกส์กระเด้ง กำจัดศัตรูและเพิ่มคะแนน
- **Enemy AI** — ศัตรู 3 ชนิด (เห็ด, สไลม์, เห็ดเร็ว) เดินลาดตระเวน หันกลับเมื่อเจอกำแพง ไล่ตามผู้เล่น
- **Traps** — กับดักใบเลื่อยหมุน, หอกแกว่ง, ใบมีดแถว, ลาวา
- **Level Objects** — กระดานเด้ง, แผ่นเลื่อน/ลิฟต์, ประตูวาร์ป
- **Items** — เหรียญ/เพชรเก็บคะแนน, ยาแดงฟื้นพลังชีวิต, ไม้กายสิทธิ์เร่งความเร็ว, แสงเวทเพิ่มพลังกระโดด
- **Custom Character** — ตัวละครผู้เล่นออกแบบเอง แบบ Skeleton2D พร้อมแอนิเมชัน Idle/Walk/Jump/Attack
- **Particle Effects** — เอฟเฟกต์วิ่ง, ตาย, โดนตี
- **Damage & Health System** — มีพลังชีวิต (HP) และจำนวนชีวิต (Life) แสดงผลบน UI
- **Save & Load** — บันทึก/โหลดตำแหน่ง คะแนน และชีวิตด้วยไฟล์ JSON
- **Sound & Music Toggle** — เปิด/ปิดเสียงเพลงและเอฟเฟกต์ได้
- **Score System** — เก็บเหรียญหรือกำจัดศัตรูเพื่อเพิ่มคะแนน
- **4 ด่าน** — level_01 ถึง level_04 ความยากเพิ่มขึ้นตามลำดับ พร้อมพื้นหลัง Parallax
- **GameOver / WinGame** — ฉากจบพร้อมภาพประกอบและเสียง
- **Level Management** — เปลี่ยนฉากลื่นไหลผ่าน Scene Transition Manager

## Getting Started

1. เปิดโปรเจกต์ด้วย [Godot 4.7](https://godotengine.org/) ขึ้นไป
2. กด **F5** หรือปุ่ม Play เพื่อรันเมนูหลัก
3. ใช้ **A/D** หรือปุ่มลูกศร ซ้าย-ขวา เดิน, **Space** กระโดด, **X** ยิง
4. บนมือถือ/เว็บ ใช้ปุ่มสัมผัสด้านล่างจอ
5. เก็บเหรียญ กำจัดศัตรู หลบกับดัก แล้วไปถึงประตูเพื่อผ่านด่าน

## Project Structure

```
Scenes/
├── Actors/           # Player, enemies, and spawners
├── Levels/           # Level scenes, base level template, and UI
├── Managers/         # GameManager, SceneTransition, AudioManager
└── Prefabs/          # Reusable objects (bullet, coin, potion, traps, items, door, button)

Assets/
├── Fonts/            # Custom fonts
├── Icons/            # UI icons
├── Sound/            # BGM and SFX
├── Spritesheet/      # Character and tile sprites
└── Textures/         # Particle and effect textures
```

## Controls

| Input | Action |
|-------|--------|
| A / Left Arrow | Move left |
| D / Right Arrow | Move right |
| Space / S | Jump |
| X | Shoot |
| On-screen buttons | Mobile and web touch controls |

## Inspector Tips

- **Player**: Toggle `double_jump` เปิด/ปิด Double Jump ปรับ `move_speed`, `jump_force`, `shoot_cooldown_time`, `bullet_lifetime` ได้
- **Enemy Spawner**: ปรับ `enemy_scenes`, `speed_range`, `respawn_time`, `max_instance`
- **Bullet**: ปรับ `speed` และ `lifetime`

## Saving

- กดปุ่ม **Save** มุมขวาบนเพื่อบันทึกความคืบหน้า
- เกมบันทึกตำแหน่งผู้เล่น คะแนน ชีวิต และการตั้งค่าเสียง

## Credits

**Modified By**
- 673380637-7 มนัสนันท์ จันดาเวียง

**Original Developer**
- [AdilDevStuff](https://github.com/AdilDevStuff) — [2D-Platformer-Starter-Kit](https://github.com/AdilDevStuff/2D-Platformer-Starter-Kit)

**2D Assets**
- [Kenney.nl](https://www.kenney.nl/)
- [craftpix.net](https://craftpix.net/)
- [Ravenmore](https://ravenmore.itch.io/)
- [Icons8.com](https://icons8.com)

**Sound Effects**
- GDFXR (Sfxr plugin for Godot)

**Modified for Educational Use By**
- College of Computing, Khon Kaen University