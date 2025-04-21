# Lynx Documentation  
---

**Lynx** is a lightweight, performance-oriented UI library for Roblox, built to accelerate interface creation with a clean and modern design. Whether you're developing advanced tools or simple utility panels, Lynx offers intuitive methods for building responsive UIs with minimal code.

This documentation will guide you through the core features of the library, from initializing the UI to creating fully interactive components like buttons, sliders, toggles, and more.

---

# Getting Started  

**How to initialize the UI?**

```lua
local LynxLib = loadstring(game:HttpGet("https://raw.githubusercontent.com/JaoExploiter/Lynx/refs/heads/main/Source"))()
```

---

### Creating a window

```lua
local window = LynxLib:MakeWindow("Lynx Lib")
```

- **argument1**: `string` — The name/title of your UI window.

