# `Instances.new()`

`Instance.new()` is a function used to create new objects during runtime that did not previously exist in the game.

This is one of the most important functions in Roblox scripting, since it allows scripts to dynamically create:
* Parts
* GUIs
* Sounds
* Models
* Effects
* Tools
* And many other objects

---

## 🧩 Basic syntax & Examples

```lua
Instance.new("ClassName", Parent)

local LightPart = Instance.new("Part", game.Workspace) -- Creates a new part on the workspace
Instance.new("PointLight", LightPart) -- Creates a PointLight on that part
-- Instance.new("PointLight", game.Workspace.Part) is valid too
```
> ⚠️ If no parent is assigned, the object exists but will not appear in the game world until parented somewhere.

```lua
local Part = Instance.new("Part") -- Creates a new Part

Part.Parent = workspace -- Assigns a parent
Part.Position = Vector3.new(0, 10, 0) -- Assigns a position
Part.Material = Enum.Material.Neon -- Assigns the material
Part.Color = Color3.new(1, 0, 0) -- Assigns the color (red)
Part.Name = "NeonPart" -- Changes the name to NeonPart
```

---

Most developers prefer this method:
```lua
local Part = Instance.new("Part")
Part.Parent = workspace
```

Instead of:
```lua
Instance.new("Part", workspace)
```

Because it is:
* Cleaner
* Easier to modify
* Easier to debug
* More readable for large scripts
