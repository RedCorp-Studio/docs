---
sidebar_position: 3
---

# Configuration

The configuration file can be found in the root folder of the project with the name `config.lua`.

## Default configuration

Here is the entire default `config.lua` file for Ultimate Admin Panel :

```lua title="config.lua"
Config = {}, Config.Statistics = {}

Config.Language = "en" -- Language available by default : en | fr
Config.Multichar = true -- Set to true if you use ESX Multicharacter

Config.Keys = { -- Keys used to open different menus
  Admin = 'H', -- Admin menu
  Reports = 'J' -- Player's reports menu
}

Config.Permissions = { -- Permissions applied for each group, please see https://redcorp.studio/docs/red-admin/configuration#permissions for more details
  admin = {
    Permissions.Admin.All,
    Permissions.Admin.Invisible,
    Permissions.Admin.Noclip,
    Permissions.Admin.ToMarker,
    Permissions.Admin.ToCoords,
    Permissions.Admin.SpawnCar,
    Permissions.Admin.RepairCar,
    Permissions.Admin.DisplayCoords,
    Permissions.Admin.DisplayNames,
    Permissions.Admin.SetPed,
    Permissions.Admin.Announce,
    Permissions.Players.All,
    Permissions.Reports.All
  },

  owner = { Permissions.All }
}

Config.Statistics.Jobs = { -- Jobs to monitor for repartition statistics
  'police', 
  'ambulance', 
  'reporter', 
  'miner', 
  'banker'
}

Config.AdminCarModel = 'baller' -- Default admin car model used for /car
Config.AdminCarPlate = 'RedCorp' -- Default admin car plate used for /car

-- DO NOT TOUCH IF NOT NECESSARY
Config.LogLevel = 0 -- 0 = Debug | 1 = Info | 2 = Warn | 3 = Danger
```

## Permissions

|Permission value|Description|
|---|---|
|`Permissions.All`|Grants all permissions|

### Admin actions
|Permission value|Description|
|---|---|
|`Permissions.Admin.All`|Grants all admin actions related permissions|
|`Permissions.Admin.Invincible`|Admin can be invincible|
|`Permissions.Admin.Invisible`|Admin can be invisible|
|`Permissions.Admin.Noclip`|Admin can noclip|
|`Permissions.Admin.ToMarker`|Admin can teleport to a marker|
|`Permissions.Admin.ToCoords`|Admin can teleport to specific coordinates|
|`Permissions.Admin.SpawnCar`|Admin can spawn cars|
|`Permissions.Admin.RepairCar`|Admin can repair cars|
|`Permissions.Admin.DisplayCoords`|Admin can display his coordinates|
|`Permissions.Admin.DisplayNames`|dmin can display players names|
|`Permissions.Admin.SetPed`|Admin can change his own ped|
|`Permissions.Admin.Announce`|Admin can post server announces|

### Player management
|Permission value|Description|
|---|---|
|`Permissions.Players.All`|Grants all players related permissions|
|`Permissions.Players.View`|Admin can view the whole data|
|`Permissions.Players.Goto`|Admin can teleport to players|
|`Permissions.Players.Bring`|Admin can bring players|
|`Permissions.Players.Heal`|Admin can heal players|
|`Permissions.Players.Revive`|Admin can revive players|
|`Permissions.Players.Kill`|Admin can kill players|
|`Permissions.Players.Freeze`|Admin can freeze players|
|`Permissions.Players.Warn`|Admin can warn players|
|`Permissions.Players.Message`|Admin can send a message to players|
|`Permissions.Players.Inventory`|Admin can manage players inventory|
|`Permissions.Players.Spectate`|Admin can spectate players|
|`Permissions.Players.Kick`|Admin can kick players|
|`Permissions.Players.Ban`|Admin can ban players|
|`Permissions.Players.Job`|Admin can set players job|
|`Permissions.Players.Money`|Admin can manage players money|
|`Permissions.Players.Unban`|Admin can unban players he banned|
|`Permissions.Players.UnbanAll`|Admin can unban every player|

### Reports management
|Permission value|Description|
|---|---|
|`Permissions.Reports.All`|Grants all reports related permissions|
|`Permissions.Reports.Assign`|Admin can assign himself reports|
|`Permissions.Reports.Close`|Admin can solve reports|
|`Permissions.Reports.SendMessage`|Admin can send messages in reports chats|