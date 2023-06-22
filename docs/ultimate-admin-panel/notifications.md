---
sidebar_position: 4
---

# Notifications

Notification system can be modified in `client/functions/notifications.lua` :

```lua title="notifications.lua"
function showNotification(content, id, type)
    -- Possible types : admin_info / info / warn / message / announce
    ESX.ShowNotification(content)    
end
```