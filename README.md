# GameBooom Unity Plugin (Commercial DLL Distribution)

This folder is a staging template for the commercial Git-installable Unity Package.

## Required before publish

Place the obfuscated distribution binaries into:

- `Editor/DLL/GameBooom.Editor.dll`
- `Editor/DLL/GameBooom.Editor.dll.meta`

If your final build depends on bundled precompiled libraries, also place them into `Editor/DLL/` with matching `.meta` files.

## Git install URL

Use after publishing this folder to the root of the distribution repository:

`https://github.com/GameBooom/GameBooom-Unity-Plugin.git#v0.1.0`

## Notes

- Do not include Unity project folders such as `Library/`, `Temp/`, `Logs/`, `ProjectSettings/`, or source `.cs` files.
- Keep Unity `.meta` files for every distributed asset and DLL.
- Keep `package.json`, `Editor/GameBooom.Editor.asmdef`, and runtime resources in the repository root.
