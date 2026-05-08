# 🧩 Functions

A **function** is a reusable block of code designed to perform a specific task.

Functions help to:
* Organize code
* Avoid repetition
* Make scripts easier to read
* Reuse logic multiple times

---

## 🧠 Built-in Functions

Functions such as:

* `print()`
* `warn()`
* `task.wait()`

are also functions created by Roblox/Lua.

---

## ⚙️ Instance Functions

Some functions belong to objects (instances).

### 📌 Structure

```lua
Instance:FunctionName()
```
> The `:` means the function belongs to that specific object.

---

## 🔧 Common Functions

### 🧬 `:Clone()`

Creates a copy of an object.

```lua
Part:Clone()
```

---

### 🗑️ `:Destroy()`

Deletes an object permanently.

```lua
Part:Destroy()
```

---

### 🔍 `:FindFirstChild()`

Searches for a child object inside another object.

```lua
Part:FindFirstChild("Fire")
```

### 🧠 Important:

* Returns the object if found
* Returns `nil` if it does not exist

Useful when:
* Objects may not exist yet
* Objects are created dynamically by scripts
  
---

### ❌ `nil`

`nil` literally means “Nothing” or “No value”

```lua
local Fire = Part:FindFirstChild("Fire")

if Fire == nil then
  warn("Fire doesn't exists")
end
```

---

### ⏳ `:WaitForChild()`

Waits until a child object appears.

```lua
game.Workspace:WaitForChild("PlayerName", 20)
-- Waits for an object named `"PlayerName"`
-- Stops waiting after `20` seconds (optional)
```

Useful when:
* Loading players
* Waiting for GUIs
* Waiting for replicated objects

---

## 💻 Example using multiple functions

```lua
local Part = game.Workspace.Part

local Fire = Part:FindFirstChild("Fire") -- 1. Finds a Fire object inside the part
-- Alternative:
-- local Fire = Part:WaitForChild("Fire", 3)

task.wait(0.5) -- 2. Waits 0.5 seconds


local NewFire = Fire:Clone() -- 3. Clones the Fire

NewFire.Color = Color3.new(0, 1, 0) -- 4. Changes the cloned fire color to green

Fire:Destroy() -- 5. Deletes the original fire
```

---

# 🏗️ Local Functions

You can also create your own custom functions.

It's useful when you want to avoid doing a process multiple times.

---

## 📌 Structure

```lua
local function FunctionName()

end
```
> ⚠️ Creating a function does NOT execute it.
> You must call it manually.

---

## 💻 Example 1 — Basic Function

```lua
local function MyFirstFunction()

    print("The function is working")

end

MyFirstFunction() -- This is how you call it
```

---

# 💻 Example 2 — Reusable Object Creation

```lua
local function AddPart() -- creates a local function

    local NewModel = Instance.new("Model", workspace) -- creates a new model without anything inside
    NewModel.Name = "PartModel" -- rename the model

    local NewPart = Instance.new("Part", NewModel) -- creates a Part inside the new model

    -- edits the properties of the new part
    NewPart.Anchored = true
    NewPart.Color = Color3.new(1, 0, 0)
    NewPart.Material = Enum.Material.WoodPlanks
    NewPart.Shape = Enum.PartType.CornerWedge
    NewPart.Position = Vector3.new(0, 4.5, 0)

end -- function ends

-- everytime the function is called, a new model with a new part is created with that custom properties
AddPart()
AddPart()
AddPart()
```

---

# 💻 Example 3 — Function + Loops

```lua
local function MovePart() -- creates a custom function

    local Part = Instance.new("Part", workspace) -- creates a part

    -- Change the position and anchor
    Part.Position = Vector3.new(0, 0, 0) 
    Part.Anchored = true

    for i = 1, 50, 1 do -- creates a for loop (repeat 50 times)

        Part.Position = Part.Position + Vector3.new(0, 1, 0) -- Moves the part 1 stud upward

        task.wait(0.1) -- "Cooldown" of 0.1 seconds

    end -- loop ends

end -- function ends

MovePart() -- function is called
```

---

# 📦 Parameters

Parameters allow functions to receive custom values.

They act like temporary variables.

---

## 💻 Example with Parameters

```lua
local function AddPart(PartMaterial, PartColor) -- create a function with a parameter

    local NewModel = Instance.new("Model", workspace)
    NewModel.Name = "PartModel"
    -- create a new model with the name "partModel1"

    local NewPart = Instance.new("Part", NewModel)

    NewPart.Anchored = false
    NewPart.Position = Vector3.new(0, 30, 0)
    NewPart.Color = PartColor
    NewPart.Material = PartMaterial
    NewPart.Shape = Enum.PartType.CornerWedge
    -- Creates a new part inside the model with custom properties

end -- function ends

-- calls the function but with the parameters defined there)
AddPart(Enum.Material.Fabric, Color3.new(0, 1, 0)) 
AddPart(Enum.Material.Glass, Color3.new(0, 0, 1))
AddPart(Enum.Material.Neon, Color3.new(1, 0, 0))
```

---

## 🧠 Why parameters are useful

Without parameters:
* You repeat the same code many times

With parameters:
* One function can create many variations
* Scripts become cleaner and easier to maintain
