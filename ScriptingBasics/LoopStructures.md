# 🔁 Loop Structures

Loops are used to repeat code automatically. They are essential for automation, animations, and gameplay systems.

There are three main types of loops: 

`while`, `for`, and `repeat`.

---

## 🔄 While Loops

A **`while loop`** repeats code **as long as a condition is true**.

⚠️ Always use `task.wait()` to prevent lag or freezing.

```lua
local Part = script.Parent

while Part.Anchored and Part.Transparency ~= 1 do

    print("Part is anchored and visible")
    Part.Position = Part.Position + Vector3.new(0, 0.1, 0)

    task.wait(0.1)

end
```

### 🧠 How it works:

* The loop checks the condition before every repetition
* If the condition becomes false, the loop stops
* Useful for continuous effects like movement, checks, or timers

---

## 🔢 For Loops

A **`for loop`** repeats a fixed number of times.

You define:

* Starting number
* Ending number
* Step (increment)

```lua
for i = 1, 10, 1 do
    print(i)
    task.wait(1)
end
```

### 🧠 How it works:

* Starts at `1`
* Ends at `10`
* Increases by `1` each time

👉 This loop runs exactly **10 times**

### 💡 Step explanation:

* `1` → counts normally (1, 2, 3...)
* `2` → skips numbers (1, 3, 5...)
* `-1` → counts backwards

---

## 🔁 Repeat Loops

A **`repeat loop`** always runs at least once and continues until a condition becomes true.

Unlike `while`, the condition is checked **at the end**.

```lua
repeat
    task.wait(1)
until condition
```

### 🧠 How it works:

* Executes code first
* Then checks the condition
* Stops only when the condition is met

---

### ♾️ Infinite Repeat Loop

If you use a condition that never becomes true, the loop runs forever:

```lua
repeat

until false
```

⚠️ This is dangerous if not controlled properly. Always use a `task.wait()` to control the loop speed

---

## 🔁 Nested Loops (Loops inside loops)

You can place a loop **inside another loop**.
These are called **nested loops**.

This allows you to repeat actions multiple times in more complex patterns.

They are commonly used for:
* Grid systems
* Procedural generation
* Tables and inventories
* Terrain generation
* Repeating actions in rows and columns


### 💻 Example of nested loops

```lua
for x = 1, 3, 1 do

    for z = 1, 3, 1 do

        print("X:", x, "Z:", z)

    end
end
-- The first loop controls `x`
-- The second loop runs completely for every `x`

-- Output:
--[[
    X: 1 Z: 1
    X: 1 Z: 2
    X: 1 Z: 3
    
    X: 2 Z: 1
    X: 2 Z: 2
    X: 2 Z: 3
    
    X: 3 Z: 1
    X: 3 Z: 2
    X: 3 Z: 3
]]
```

---

## 🧨 Breaking Loops (`break`)

You can force a loop to stop immediately using `break`.

```lua
local Part = script.Parent

for i = 1, 100, 1 do

    print(i)

    Part.Transparency = Part.Transparency + 0.01

    task.wait(0.1)

    -- Stop the loop if the part becomes invisible
    if Part.Transparency >= 1 then
        break
    end
end
```

### 🧠 How it works:

* Exits the loop instantly
* Ignores remaining iterations
* Useful for stopping based on events or conditions

Example logic:

* Loop runs up to 100 times
* If a condition changes mid-loop → stop immediately

---

## 💡 Summary

* **`while`** → repeats while condition is true
* **`for`** → repeats a fixed number of times
* **`repeat`** → runs at least once, stops when condition is met
* **`nested`** → A loop inside another loop
* **`break`** → forces loop to stop immediately
