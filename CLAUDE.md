# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Blueprint-only Unreal Engine 5.5 first-person shooter project inspired by Counter-Strike. Originally created from the **TP_BlankBP** template. No C++ source — all gameplay logic lives in Blueprint assets under `Content/Blueprints/`.

## Engine & Rendering

- **Engine**: UE 5.5
- **RHI**: DX12 with Shader Model 6
- **Features enabled**: Lumen GI, Virtual Shadow Maps, RayTracing, Mesh Distance Fields
- **Static lighting**: Disabled (fully dynamic)
- **Hardware target**: Desktop / Maximum quality
- **External Actors (OFPA)**: Enabled — map actors stored in `Content/__ExternalActors__/`

## Input System

Uses **Enhanced Input** (`EnhancedPlayerInput` / `EnhancedInputComponent`). Input actions and mapping context are at `Content/Blueprints/Player/Input/`:
- `IA_Look` / `IA_Movement` — Input Actions
- `IMC_Default` — Input Mapping Context

## Content Structure

```
Content/
├── Blueprints/
│   ├── interface/INT_PlayerController.uasset
│   ├── PC_CounterStrike.uasset          # PlayerController
│   ├── Player/
│   │   ├── BP_PlayerBase.uasset         # Base player class
│   │   ├── BP_CounterTerrorism.uasset   # CT pawn
│   │   ├── BP_Terrorists.uasset         # T pawn
│   │   └── Input/                       # Enhanced Input assets
│   └── GM_CounterStriker.uasset         # GameMode (set in DefaultEngine.ini)
├── Map/Map_1.umap                       # Main level (editor startup + game default)
└── marketplace/                         # Purchased/imported content packs
    ├── GoodSky/                         # Dynamic sky & weather system
    ├── Knife_FPS_Animations/            # FPS knife weapon (animations, audio, BP_Knife)
    ├── Modern_Insurgent_7/              # Character model pack
    ├── QuantumCharacter/                # Modular military character
    └── SuperGrid/                       # Level prototyping kit
```

## Key Config Files

- `Config/DefaultEngine.ini` — GameMode, map paths, renderer settings
- `Config/DefaultInput.ini` — Enhanced Input config
- `Config/DefaultGame.ini` — Project ID only (no custom game settings)

## Build & Testing

There is no build step, no automated tests, and no source code compilation. This is a content-only project. Open `CSGO.uproject` directly in the Unreal Editor to work on it. All assets are binary `.uasset` files managed by the editor — do not edit them as text files.

## 用户要求

每次回复都需要在内容前加上“Ciallo～(∠・ω< )へ☆”。
