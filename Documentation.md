# Lynx Documentation  
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

### Adding a Toggle Button

```lua
local togglebutton1 = LynxLib:AddToggle({
    Title = "Toggle Button",
    Description = "Press the black button!",
    Tab = tab1,
    Callback = function(ToggleState)
        print(ToggleState)
    end,
})
```

| Argument      | Type       | Description                                                        |
|---------------|------------|--------------------------------------------------------------------|
| `Title`       | `string`   | Text displayed as the toggle's title.                              |
| `Description` | `string`   | Additional text or tooltip shown below the title.                 |
| `Tab`         | `Tab/instance`      | The tab where this toggle will be placed.                         |
| `Callback`    | `function` | Function that runs when the toggle is changed. Receives `true` or `false` as an argument. |

---

### Adding a Text Box

```lua
local textbox1 = LynxLib:AddTextBox({
    Title = "TextBox",
    Description = "Type some text in the textbox!",
    Tab = tab1,
    Callback = function(input)
        print(input)
    end,
})
```

| Argument      | Type       | Description                                                     |
|---------------|------------|-----------------------------------------------------------------|
| `Title`       | `string`   | The title displayed above the textbox.                          |
| `Description` | `string`   | Optional description or instruction shown below the title.      |
| `Tab`         | `Tab`      | The tab where this textbox will appear.                         |
| `Callback`    | `function` | Function that runs when the user inputs text. Returns the text. |

---

### Adding a DropDown

```lua
local dropdown1 = LynxLib:AddDropDown({
    Title = "Buttons",
    Description = "See all buttons.",
    Buttons = { "Button1", "Button2" },
    Tab = tab1,
    Callback = function(SelectedButton)
        print(SelectedButton)
    end,
})
```

| Argument      | Type         | Description                                                                 |
|---------------|--------------|-----------------------------------------------------------------------------|
| `Title`       | `string`     | The title displayed at the top of the dropdown.                            |
| `Description` | `string`     | Optional subtext displayed below the title.                                |
| `Buttons`     | `table`      | A list of strings representing the buttons to show inside the dropdown.    |
| `Tab`         | `Tab`        | The tab where the dropdown will be added.                                  |
| `Callback`    | `function`   | Function called when a button is selected. Receives the selected button name. |

---

### Adding a ColorPicker

```lua
Lib:AddColorPicker({
    Title = "ColorPicker",
    Description = "My colorpicker",
    Tab = tab1,
    Callback = function(Color3)
       print(Color3)
    end,
})
```

| Argument      | Type         | Description                                                                 |
|---------------|--------------|-----------------------------------------------------------------------------|
| `Title`       | `string`     | The title displayed at the top of the color picker.                         |
| `Description` | `string`     | Optional subtext displayed below the title.                                 |
| `Tab`         | `Tab`        | The tab where the color picker will be added.                               |
| `Callback`    | `function`   | Function called when the selected color changes. Receives the selected `Color3`. |

---

### Adding a Slider

```lua
local slider1 = LynxLib:AddSlider({
    Title = "Brightness",
    Description = "Adjust screen brightness.",
    Tab = tab1,
    Callback = function(value)
        print("Slider value:", value)
    end,
})
```

| Argument      | Type       | Description                                                              |
|---------------|------------|--------------------------------------------------------------------------|
| `Title`       | `string`   | The title displayed above the slider.                                   |
| `Description` | `string`   | Optional subtext or explanation below the title.                         |
| `Tab`         | `Tab`      | The tab where the slider will be displayed.                             |
| `Callback`    | `function` | Function called when the slider value changes. Returns the current value. |

**Note:**  
- The slider's default minimum value is `0`,  
- The default maximum value is `100`,  
- The default starting value is `0`.

---

### Adding a Key Bind

```lua
local keybind1 = LynxLib:AddKeyBind({
    Title = "Open Menu",
    Description = "Press a key to bind the action.",
    InitialBind = "E",
    Tab = tab1,
    Callback = function()
        print("Binded key pressed")
    end,
})
```

| Argument      | Type       | Description                                                              |
|---------------|------------|--------------------------------------------------------------------------|
| `Title`       | `string`   | The label/title of the keybind.                                         |
| `Description` | `string`   | Optional description to guide the user.                                 |
| `Tab`         | `Tab`      | The tab where the keybind will appear.                                  |
| `Callback`    | `function` | Function that runs when a key is bound. Returns the input object.        |

---

### Adding a Label

```lua
local label1 = LynxLib:AddLabel({
    Text = "Welcome to Lynx UI!",
    Tab = tab1,
})
```

| Argument  | Type     | Description                                |
|-----------|----------|--------------------------------------------|
| `Text`    | `string` | The text content of the label.             |
| `Tab`     | `Tab`    | The tab where the label will be displayed. |

---

## Misc Functions

---

### Closing the UI

```lua
LynxLib:CloseGui()
```

Closes the interface completely and removes it from the screen.

---

### Minimizing the UI

```lua
LynxLib:Minimize()
```

Collapses the UI window into a smaller or hidden state.

---

### Maximizing the UI

```lua
LynxLib:Maximize()
```

Restores the UI window to its full view after being minimized.

---

### Changing the UI Title

```lua
LynxLib:SetTitle({
    Text = "New Title",
})
```

| Argument | Type     | Description                     |
|----------|----------|---------------------------------|
| `Text`   | `string` | The new title to display in UI. |

Changes the title of the main UI window dynamically.

---

### Sending a Notification

```lua
local notification = LynxLib:SendNotification({
    Title = "Lynx Lib",
    Description = "You have received a notification!",
    Duration = 5,
})
```

| Argument      | Type     | Description                           |
|---------------|----------|---------------------------------------|
| `Title`       | `string` | Title of the notification.            |
| `Description` | `string` | Message displayed inside the popup.   |
| `Duration`    | `number` | Duration (in seconds) the notification stays visible. |

---

### Crashing the Client

```lua
-- use with caution
LynxLib:Crash()
```

Forcefully crashes the local player’s game client. Intended for testing or deterrent purposes only.

---
