# Assets / Weapons

Placeholder weapon meshes for the demo character — these are what `BP_Player` holds while testing Stratagems, and aren't part of the reusable system itself.

## Structure

Each weapon folder follows the same layout:

```
WeaponName/
├── Materials/   — material / material instance for the mesh
├── Meshes/      — skeletal mesh, physics asset, and (for GrenadeLauncher) a projectile mesh
└── Textures/    — diffuse/normal/mask textures
```

| Folder | Weapon | Notes |
|---|---|---|
| `Pistol/` | Sidearm | `SK_Pistol` / `SKM_Pistol` |
| `Rifle/` | Primary weapon | `SK_Rifle` / `SKM_Rifle` |
| `GrenadeLauncher/` | Secondary weapon | Includes `FirstPersonProjectileMesh` and its own fire sound (`FirstPersonTemplateWeaponFire02`) |

> **Not part of the system.** These exist so the demo character has something to aim down sights with while a Stratagem is on cooldown — they have no connection to `BPC_StratagemSystem` or any Data Asset in `DataAssets/`.
