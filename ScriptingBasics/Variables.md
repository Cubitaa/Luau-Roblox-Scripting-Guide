# Variables

A **variable** is a container used to store data in a script.  
This data can be anything: a number, text, object, position, color, etc.

The main purpose of variables is to make your code:
- 🧩 Easier to read  
- ⚡ Faster to write  
- 🧠 More organized and reusable  

---

## 📌 Why do we use variables?

Imagine you have this path to an object:
```lua
game.Workspace.City.Street.House.Part
```

If you need to use it multiple times, repeating it becomes:
- Long
- Messy
- Hard to maintain

So instead of repeating the full path, you store it in a variable.

---

## 📦 Creating a Variable

In Luau, variables are created using local, usually at the top of the script:

> "local print" and "local warn" are not permited

```lua
local Part = game.Workspace.City.Street.House.Part -- Now the code becomes cleaner

Part.Position = Vector3.new(0, 0, 0)
Part.Material = Enum.Material.Neon

-- You can combine variables!

local PartPosition = Vector3.new(0, 0, 0)

Part.Position = PartPosition -- Now the position of the Part, it's the indicated on PartPosition

----

local SwordDamage = 25

print("The sword deals " .. SwordDamage .. " damage") -- Instead of writing numbers directly in many places, you store them in variables
```
