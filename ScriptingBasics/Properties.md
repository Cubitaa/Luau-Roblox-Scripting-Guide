# Properties

**Properties** are the attributes of an object. They define *what an object is like* or *how it behaves*.

For example, a Part can have properties such as:
- its position in the world
- its color
- whether it is anchored or not
- its transparency

---

## 🧭 How to Reference a Part in a Script

The Explorer works like a family tree. To access an object or one of its properties, you must follow its hierarchy from the most general element to the most specific one.

At the top of the hierarchy is `game`, and from there you navigate through its children.

### 📌 Basic referencing examples

```lua
game.Workspace.Pato
```

If the part is inside a folder or model:
```lua
game.Workspace.Model.Pato
game.Workspace.Folder.Pato
```

If the script is inside the part itself:
```lua
script.Parent
script.Parent.Parent -- etc
```

If the object name contains spaces, you must use brackets:
```lua
game.Workspace["My part"]
```

---

## 📦 Data Types

Data Types define the kind of value a property can store. Every property expects a specific type of data. For example:
- a position uses Vector3
- a color uses Color3
- a name uses a String

These are the most common data types used in Roblox scripting:

- **Number** → Any numeric value (e.g. `10`, `3.5`)
- **Boolean** → Logical value: `true` or `false`
- **String** → Text values inside quotes (`"Hello"`)
- **Object (Instance)** → Reference to another Roblox object
- **Vector3** → 3D position or direction `(X, Y, Z)`
- **Color3** → RGB color values (0 to 1 range)
- **BrickColor** → Predefined Roblox color system
- **Enum** → Fixed list of predefined options

---

## 📌 General syntax

```lua
game.ParentOfTheObject.ReferenceObject.PropertyName = value
script.Parent.PropertyName = value

game.Workspace.Part.Transparency = 0.5 -- Change the part transparency to 0.5
script.Parent.Anchored = True -- Enable the Anchor to the script parent
```

---

## 📋 Common Properties

| Property | Data Type | Description | Example |
|----------|----------|-------------|----------|
| Transparency | Number (0.0 - 1.0) | Controls how visible the part is | `game.Workspace.Part.Transparency = 0.5` |
| Anchored | Boolean | Determines if physics affects the part | `game.Workspace.Part.Anchored = true` |
| Name | String | Changes the object's name | `script.Parent.Part.Name = "MyFirstPart"` |
| Parent | Object (Instance) | Changes the parent of the object | `script.Parent.Part.Parent = game.Workspace` |
| Position | Vector3 | Sets the position in the world | `game.Workspace.Part.Position = Vector3.new(10, 20, 5)` |
| Color | Color3 | Sets the RGB color of the part | `game.Workspace.Part.Color = Color3.new(1, 0, 1)` |
| BrickColor | BrickColor | Uses Roblox predefined colors | `script.Parent.Part.BrickColor = BrickColor.new("White")` |
| Material | Enum | Changes the surface material | `script.Parent.Part.Material = Enum.Material.Grass` |

---

## ➕ Basic Math Operations in Properties

You can modify values dynamically using basic math operators:

- ➕ Addition (`+`)
- ➖ Subtraction (`-`)
- ✖️ Multiplication (`*`)
- ➗ Division (`/`)

These are commonly used with **Number**, **Vector3**, and sometimes **Color3** values.

---

## 🧪 Examples

```lua
game.Workspace.Part.Position = game.Workspace.Part.Position + Vector3.new(0, 5, 0) -- Move a part upward

game.Workspace.Part.Transparency = game.Workspace.Part.Transparency / 2 -- Reduce transparency by half

game.Workspace.Part.Position = game.Workspace.Part.Position * 2 -- Scale a position
```
