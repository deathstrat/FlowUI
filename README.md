# FlowUI

A UI library for Roblox. Windows, tabs, sub tabs, groupboxes and controls,
with live themes, a Home tab, notifications and dialogs, and config saving.

This repository is a restored copy of the OuroFlow UI library (originally
`joustingmatch/-3`, deleted upstream). It was recovered from the author's own
`Example.luau`, which embeds the full library, and is now self-hosted here so
it cannot disappear again.

## Load it

```lua
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/deathstrat/FlowUI/refs/heads/main/Source.luau"))()
```

## Quick start

```lua
local Window = Library:CreateWindow({
    Name = "My Hub",
    ToggleUIKeybind = "RightControl",
    ConfigurationSaving = { Enabled = true, FolderName = "MyHub" },
    Home = {
        Discord = "discord.gg/example",
        Stats = { "Players", "Session", "FPS", "Ping" },
    },
})

local Main = Window:CreateTab({ Name = "Main", Icon = "zap" })
local General = Main:CreateSubTab({ Name = "General" })
local Box = General:AddLeftGroupbox({ Name = "Automation", Icon = "repeat" })

Box:CreateToggle({
    Name = "Enabled",
    CurrentValue = false,
    Flag = "Enabled",
    Callback = function(Value)
        print("enabled", Value)
    end,
})
```

See `Example.luau` for a full reference build that shows every part of the
library in a realistic layout: window and Home options, sub tabs and
groupboxes, statuses and status lists, one of every element, popups, and the
Settings tab with the config manager and theme manager.

## Files

- `Source.luau` — the library itself, as a standalone
  `return (function() ... end)()` module.
- `Example.luau` — the original example, untouched. It embeds its own copy of
  the library, so it runs on its own.

## Notes

- At runtime the library fetches Lucide icons and the Valley Sans font from
  their public repositories, exactly as the original did.
- The original repository's README and `llms.txt` were not part of the
  downloaded example and could not be recovered; this README replaces them.
