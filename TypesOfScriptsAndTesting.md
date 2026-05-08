# 📁 Script / Server Script

- ⚙️ Scripts that **modify the server**, visible to **all players**
- 📍 Can be placed even in the `Workspace`
- 🌧️ Example: Weather systems (rain, snow, etc.), generations, etc

---

# 👤 Local Script

- 🎮 Scripts that **modify the client (player-side only)**
- 👀 Only the **affected player can see the result**
- 🚫 Cannot be placed in `Workspace`
- 📁 Must be inside objects starting with `Starter` or in `ReplicatedFirst`
- 🔁 They are copied into the player’s `PlayerScripts` when the game runs
- 🎒 Example: Inventory systems, UI, camera effects

# 🧩 Module Script
WIP

---

# 🧪 Script Testing Modes

- 🧑‍💻 **Play / Play Here:** Runs both **client and server**, including all scripts
- 🖥️ **Run:** Runs only the **server**
- 👥 **Team Test:** Same as Play, but with support for testing with your team
- 🌐 **Server & Clients:** Creates a dedicated server and multiple client players for full simulation testing in your pc
  
You can change it on the first icon of the screenshot

### ⏯️ In-Test Controls

When testing the game, you can:
- ⏸️ Pause the simulation (second icon)
- ⏹️ Stop the test (third icon)
- 🖥️ Switch to server view (fourth icon)

<img width="456" height="66" alt="image" src="https://github.com/user-attachments/assets/420c9542-0207-408b-ac9f-2c4b3238361b" />


---

# 🐞 Debugging

Debugging refers to the process of identifying and fixing errors in our scripts. These errors are displayed in the Output window, which helps us detect what is going wrong during execution.

There are two main types of errors:

Syntax Errors: These occur when the code is written incorrectly (e.g., missing punctuation, incorrect capitalization, or invalid structure). The script will not run until they are fixed.
Logic Errors: The code runs without crashing, but it does not behave as intended due to incorrect logic or design.

To help track script behavior, you can use print() statements to monitor values and execution flow in real time.

# 📊 Output Information

When an error occurs, the Output will display:

❌ The error message and its description
📄 The exact script and line number where the error happened
⏱️ The precise moment the error was triggered during execution
