# Aggressivity Changer (Fabric) - Minecraft 1.21.9 (v2)

Improvements in v2:
- Persist aggressivity state to entity NBT so changes survive world save/reload.
- Mixin on LivingEntity to prevent targeting when PASSIVE, and allow NATURAL behavior.
- Tick updates every 20 ticks (1 second) to reduce server load.
- Safer best-effort approach: we don't permanently mutate goalSelector; instead we block target setting when necessary,
  and use a controlled method to assign targets in FULLY_AGGRESSIVE state.

## Build instructions
1. Install JDK 17.
2. Run `./gradlew build` (or generate wrapper then build).
3. You'll find the jar in `build/libs/`.

## Notes
- Mixin behavior depends on mappings and method names; you may need to adjust if mappings differ.
- This version uses NBT keys: `AggressivityChanger_state` stored on entities.
