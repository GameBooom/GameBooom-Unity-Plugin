# Commercial DLL Distribution Checklist

## Include
- `package.json`
- `README.md`
- `CHANGELOG.md`
- `LICENSE`
- `Editor/DLL/GameBooom.Editor.dll`
- `Editor/DLL/*.meta`
- Keep Newtonsoft resolved from `package.json` unless you have a proven binary-only requirement
- Only bundled dependency DLLs that are not already provided through `package.json` dependencies
- `Editor/Resources/GameBooom/Styles/GameBooom.uss`
- Resource `.meta` files

## Do not include
- Source `.cs` files
- `Library/`
- `Temp/`
- `Logs/`
- `ProjectSettings/`
- `Packages/`
- `.sln` / `.csproj`
- Internal staging notes

## Verify before publish
1. Open a clean Unity 2022.3 project.
2. Install from local path or Git URL.
3. Confirm Package Manager recognizes `com.gamebooom.editor`.
4. Confirm `GameBooom` menu appears.
5. Open the main window and settings window.
6. Confirm bundled DLL dependencies resolve without compile errors.
7. Confirm resources (USS/styles) load correctly.
