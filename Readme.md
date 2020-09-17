# Breacher
This is a squad mod that add a Breacher role who uses explosives and grappling hook.

## Description

Currently only US and RUS factions has breacher role.

To use grappling hook:

1. Select the breacher role in role selection.

2. Press 4 to switch to the grapplehook weapon.

3. Throw it to the edge of building you want to grapple. The hook will automatically attach to the edge when the rope hits the edge.

To retrieve the grappling hook, use shovel to remove it and the item will return to your inventory.

## Technical Information

### Core Classes

- BP_GrapplingHook_Proj: The hook projectile. Currently using an m67 mesh because of no hook mesh in the SDK. This projectile has an CableComponent attached between the projectile and the soldier, and constantly detecting if there's anything collide with the CableComponent on server. Once collision is detected or the hook movement stops, the hook is attached and BP_Rope_Interaction is spawned.
- BP_Rope_Interaction: Spawned by BP_GrapplingHook_Proj when impact. This actor acts like a trigger to spawn ropes, and has an icon to show the position of attach points to players.
- BP_RopeEnd: Used by a free end rope. Currently unused.
- BP_SoldierHeldRope: A CableActor derived rope actor, just display a CableComponent between BP_GrapplingHook_Proj and the soldier pawn. Currently unused and replaced by BP_GrapplingHook_Proj, may remove in the future.

### Maps
Mapnames:
- Jensens_Range_v2_breacher
- Narva_AAS_v1_breacher

## Usage
Use AdminChangeMap [mapname] to play with breacher.

## ChangeLog
- 200917
Initial Commit.