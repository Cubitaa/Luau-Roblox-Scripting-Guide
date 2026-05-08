# `Return`

The `return` keyword is used to send a value back when a function finishes running.

This allows a function to **give information back** to the rest of the script.

---

## 🧠 Why use `return`?

Without `return`, a function simply runs code.

With `return`, the function can:
* Send back a value
* Be used inside conditions
* Store results in variables
* Reuse logic more efficiently

---

## 📦 Basic Structure

```lua
local function FunctionName()

	return Value

end
```

---

## ✅ Example: Checking if a Part is Invisible

```lua
-- Put this script inside ServerScriptService to test it

local Part = game.Workspace.Part

local function IsTransparent() -- creates a local function

	if Part.Transparency == 1 then
		return true -- send back a "true" value
	else
		return false -- send back a "false" value
	end -- ends condition

end -- ends function

if not IsTransparent() then 
	print("The Part is visible")
  -- if transparency == 1 (invisible) is false then the part is visible
end
```

## 📥 Storing returned values

You can save the returned value in a variable:

```lua
local IsInvisible = IsTransparent()

print(IsInvisible)
```

---

## ⚠️ Important

When `return` runs:
* The function instantly stops
* Any code below it will NOT execute

Example:

```lua
local function Test()

	return true

	print("Hello") -- This will never run

end
```

---

## 🧪 Multiple Returns

Functions can also return more than one value:

```lua
local function GetStats()

	return 100, 50, 25

end

local Health, Stamina, Hunger = GetStats()

print(Health)
print(Stamina)
print(Hunger)
```

This is commonly used in advanced systems and modules.
