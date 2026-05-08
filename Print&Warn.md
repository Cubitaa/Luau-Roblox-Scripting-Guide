# `Print` and `Warn` Function
The `print()` and `warn()` function is used to display values in the output window.
If you want to show the quotation marks (`" "`), you have to use the simple ones (`' '`) or using `\`


## 🖨️ Print function

The `print()` function display the values highlighted in white, making it useful for debugging or tracking events.

```lua
print("Text here") -- Text here
-- ⚠️ Always use quotation marks when printing strings.

print("Hello 'Cubita'") -- Hello "Cubita"
print("He said: \"Hello World\"") -- He said: "Hello World"


```

You can also print variables or other values:

```lua
local hi = "Hello World!"
print(hi) -- this prints the variable with the String "Hello World!"

local n = 1
print(n) -- this prints the variable with the value "1"
print(2) -- this prints the number "2"
```

---

## ⚠️ Warn function

The `warn()` function works similarly to print, but its output appears highlighted in orange, making it useful for warnings or important notices.

```lua
warn("This message was warned") -- This message was warned

local w = "warn"

warn("This is a 'test'") -- This is a "test"
warn("Another \"test\" for a ") -- Another "test"
warn(w) -- warn 
```
Example of the print and warn function:

<img width="850" height="66" alt="image (1)" src="https://github.com/user-attachments/assets/37515c9c-d03a-4d5c-beab-36e32cba9dbe" />

---

## 🔗 Combining text with variables (print & warn)

You can combine text and variables in a `print` or `warn` using concatenation (`..` in Lua).

### 📌 Example with `print`

```lua
local name = "Cubita"
print("Hello, my name is " .. name .. "!") -- Hello, my name is Cubita!

local level = 5
warn("Warning: You are at level " .. level) -- Warning: You are at level 5
```

## 🧠 Alternative (cleaner and more scalable way)

Instead of joining text with `..`, you can use `string.format()`, which is more organized and easier to read when messages get complex.

### 📌 How it works

`string.format()` lets you create a template string and then replace placeholders with values:

- `%s` → text (string)
- `%d` → numbers (integer)
- `%f` → decimals

---

### 📌 Example

```lua
local name = "Cubita"
local level = 5
local hp = 50.5
local game = "Project FrontRooms"

print(string.format("Hello %s, you are level %d and you have %f HP", name, level, hp)) -- Hello Cubita, you are level 5 and you have 50.5 HP

print(string.format("%s is creating '%s'", name, game)) -- Cubita is creating "Project FrontRooms"
