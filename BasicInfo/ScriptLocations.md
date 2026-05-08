# 📁 Script Locations in Roblox Studio

These services can be viewed in the **Explorer window**, accessible from the **View tab** in Roblox Studio or the **Home toolbar**. The Explorer shows a hierarchical structure of every instance inside an experience.

---

## 🧠 Overview

Script placement is essential in Roblox development because each service defines **where code runs (client, server, or both)** and how it behaves.

---

## 🌍 Workspace

Represents the **game world itself**.

This is the ideal location for **server-side scripts that are directly attached to objects and control their behavior in the world**.

**Usable scripts:**
- Scripts  
- ModuleScripts  

---

## 🔁 ReplicatedFirst & ReplicatedStorage

### ⚡ ReplicatedFirst

Contains objects that are replicated to the **client before anything else**.

Used for the **minimum required assets and scripts needed to display loading screens or initial UI**.

**Usable scripts:**
- LocalScripts  
- ModuleScripts  

### 🔄 ReplicatedStorage

Contains objects shared between **client and server**.

Ideal for **ModuleScripts used by both sides of the game architecture**.

- LocalScripts do **not execute** here  
- Scripts with `RunContext = Client` can execute  

**Usable scripts:**
- Scripts  
- LocalScripts (context-dependent)  
- ModuleScripts  

---

## 🖥️ ServerScriptService

Contains **server-side scripts**.

This is the main location for **game logic, secure systems, and backend functionality** that should not be exposed to the client.

**Usable scripts:**
- Scripts  
- ModuleScripts  

---

## 💾 ServerStorage

Stores **server-only objects** that are not replicated to clients immediately.

Used for **large assets, templates, or hidden data**.

- Scripts do not run here  
- ModuleScripts can be stored for server use  

**Usable scripts:**
- Scripts (not executed)  
- ModuleScripts  

---

## 👤 StarterPlayer

### 🧍 StarterCharacterScripts

Scripts inserted into the **character model when it spawns**.

Used for:
- Movement systems  
- Animations  
- Terrain interaction  
- Character-related logic  

**Usable scripts:**
- Scripts  
- LocalScripts  
- ModuleScripts  


### 🎮 StarterPlayerScripts

Contains **LocalScripts executed when the player joins the game**.

Placed inside the player’s `PlayerScripts` container.

Used for:
- UI logic (HUD)  
- Input handling (keyboard/mouse/controller)  
- Client-side systems  

**Usable scripts:**
- LocalScripts  
- ModuleScripts  

---

## 🖼️ StarterGui

Contains **GUI elements cloned to the client at runtime**.

Used for interfaces such as menus and HUDs.

Used for:
- Menus  
- HUDs  
- Popups and UI systems  

**Usable scripts:**
- LocalScripts  
- ModuleScripts  

---

## 🎒 StarterPack

Usually contains **Tools**, but can also include scripts inside them.

Used to give players starting items when they spawn.

**Usable scripts (inside tools):**
- Scripts  
- LocalScripts  
- ModuleScripts  

---

## ⚠️ Important Note

- **ReplicatedFirst** and **ReplicatedStorage** can contain Scripts with `RunContext = Client`
- All `Starter[]` services should primarily use **LocalScripts**
