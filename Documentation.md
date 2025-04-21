# 📚 Lynx Documentation  
---

**Lynx** is a sleek, lightweight, and highly optimized UI library for Roblox, crafted to streamline the creation of interactive and visually polished user interfaces. Whether you're building developer tools, admin panels, or feature-rich menus, Lynx allows you to create advanced UI systems with minimal effort and maximum control.

This documentation covers all essential functions, including how to set up the library, create windows and tabs, and add components like buttons, toggles, sliders, and more — all through simple, modular code.

---

#  Getting Started  

###  Initializing the UI Library

```lua
local LynxLib = loadstring(game:HttpGet("https://raw.githubusercontent.com/JaoExploiter/Lynx/refs/heads/main/Source"))()
```

Loads the main library into your script.

---

### Creating a Window

```lua
local window = LynxLib:MakeWindow({
    Name = "Lynx UI"
})
```

| Argument   | Type     | Description                      |
|------------|----------|----------------------------------|
| `Name`     | `string` | The title of the main UI window. |

---

### Creating a Tab

```lua
local tab1 = LynxLib:NewTab({
    Name = "Main Tab"
})
```

| Argument   | Type     | Description               |
|------------|----------|---------------------------|
| `Name`     | `string` | The name/title of the tab |

---

###  Adding a Button

```lua
local button1 = LynxLib:AddButton({
    Title = "Click Me!",
    Description = "This is a test button.",
    Tab = tab1,
    Callback = function()
        print("Button clicked!")
    end,
})
```

| Argument      | Type       | Description                            |
|---------------|------------|----------------------------------------|
| `Title`       | `string`   | Text displayed on the button.          |
| `Description` | `string`   | Optional tooltip or subtext.           |
| `Tab`         | `Tab`      | The tab object to insert this button into. |
| `Callback`    | `function` | Function to run when the button is clicked. |

---
