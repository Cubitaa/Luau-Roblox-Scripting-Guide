# 🧠 Conditional Statements (if / elseif / else)

Conditional statements are used to execute parts of code only when certain conditions are met.

They allow your script to make decisions based on values, states, or events.

---

## 🧩 Types of Statements

- **`if`** → The first condition to check  
- **`elseif`** → Additional condition if the previous one is not met (you can use multiple)  
- **`else`** → Runs if none of the previous conditions are true  

---

## ⚙️ How They Work

- Conditions use `==` (double equals), not `=`  
- Every `if` block must end with `end`  
- After a condition, you must use `then`  
- Multiple conditions can be combined using:
  - `and` → both conditions must be true  
  - `and not` → ensures a condition is NOT true
  - `or` → only one condition must be true

---

## 📊 Comparison Operators

- `==` → Equal to  
- `~=` → Not equal to  
- `>` → Greater than  
- `<` → Less than  
- `>=` → Greater or equal to  
- `<=` → Less or equal to  

---

## 🧪 Example: Multiple Conditions

```lua
-- We create two variables for two different parts
local Part1 = game.Workspace.Part1
local Part2 = game.Workspace.Part2

if Part1.Transparency >= 0.5 then -- first condition: Part1 must be greater or equal to 0.5 to be true
    print("Part is transparent")

elseif Part1.Material == Enum.Material.Neon then -- if first condition is false → second condition: Part1 must be neon to be true 
    print("Material is Neon, Part is not transparent")

else -- if any of the conditions met, this one will
    print("Material is not Neon, Part is not transparent")
end
```
