## ⏱️ `wait()` and `task.wait()`

The `wait()` function pauses the script for a specified amount of time (in seconds) before continuing execution.

This is useful for creating delays, timing events, or sequencing actions in your scripts.

---

## 🧪 Basic Example (wait)

```lua
Print("Hi")

wait(1)

Print("Bye")
```

👉 In this example, the script:

- Print "hi"
- Waits 1 second
- Print "bye"

## ⚡ Recommended: task.wait()

`task.wait()` is the modern and improved version of `wait()`.

It is more accurate, more stable, and generally causes less performance issues (less jitter and delay inconsistencies).

```lua
Print("Hi")

task.wait(1)

Print("Bye")
```
