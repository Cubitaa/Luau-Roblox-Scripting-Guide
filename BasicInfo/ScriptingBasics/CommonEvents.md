# ⚡ Events

An **event** is a signal that activates when something happens in the game.

These signals **can be connected to functions and local functions**

Examples of events:
* A player touches a part
* A property changes
* A player joins the game
* A button is clicked
* A tool is equipped

---

## ⚡ How to identify events

When typing: `Instance.` you will see many members in the autocomplete menu.

Events usually have a lightning icon (⚡)

---

## 🔗 Connecting Events

To make an event execute code, you use:
```lua
Event:Connect(function()

end)
```

> `:Connect()` links the event to a function
> The function runs every time the event happens

---

# Common Events

## 🟨 `Touched` Event

The `Touched` event activates when a part collides with something.

This is commonly used for:
* Buttons
* Traps
* Damage zones
* Teleporters
* Pressure plates

### ❌ Incorrect Example

```lua
local Part = script.Parent

Part.Touched:Connect(function()

    print("Collision detected")

end)
```
This activates with:
* Players
* NPCs
* Parts
* Debris
* Literally anything touching the part, including other parts

### ✅ Correct Example (Players/NPCs only)

```lua
local Part = script.Parent

local Debounce = false -- A "debounce" prevents the event from activating repeatedly too fast. It's like a cooldown

Part.Touched:Connect(function(Hit) -- calls the Touched event with a function and a parameter called "Hit"

    if not Debounce and Hit.Parent:FindFirstChild("Humanoid") then -- the Hit parameter is used in this conditional to check if it hits an humanoid (only characters contains "humanoid")

        Debounce = true -- activates the cooldown. If not = lot of coding in a second = lag

        print("Player or NPC touched the part") -- prints it to check

        task.wait(1) -- waits one second

        Debounce = false -- desactivates the cooldown

    end

end)
```

---

## 🟦 `Changed` Event

The `Changed` event activates whenever a property changes.

Useful for:
* Detecting value changes
* GUIs
* Leaderstats
* Gamepasses
* Health systems
* Transparency changes

---

### 💻 Example

```lua
local Part = script.Parent

task.wait(3)

Part.Transparency = 0.5  -- waits 3 seconds to change the transparency

Part.Changed:Connect(function(Property) -- Stores the name of the changed property as a string

    if Property == "Transparency" then
    -- writes the ONLY change we want to consider because Changed event activates for ANY property change.

        print("Transparency was changed")

    end -- condition ends

end) -- event ends
```
