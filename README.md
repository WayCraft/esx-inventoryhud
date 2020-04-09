# Dutch Players Edit // esx-inventoryhud // NOT SUPPORTED ESX 1.2
Esx_inventoryhud 2.3 was taken offline a while ago and would not be updated anymore. ESX has now also been updated (version 1.2), but now esx_inventoryhud 2.3 has become unusable.

We, Dutch Players, are still very much in favor of updating FiveM Artifacts and ESX. Both DISC inventoryhud and other UI oriented inventory systems have become unusable. Nevertheless, we would like a working UI for the inventory.

We are going to try to update esx_inventoryhud without bugs.
Your help is much appreciated in a pull request!

We did not make any of these scripts. We do not take any credits.

## Requirements
- [es_extended] (https://github.com/ESX-Org/es_extended)
- [B1G Notify] (https://forum.cfx.re/t/release-esx-b1g-notify-system-full-costumizable/)

## Installation
You need to do a couple steps to get it working.
First you start adding the resources to your server.cfg.

- Put all folders in your resources folder and start:
```
start esx_inventoryhud
start esx_inventoryhud_trunk
start esx_inventoryhud_glovebox
```

### Disable default esx inventory:

Open `es_extended`, then find and remove this code in `client/main.lua`:
```
-- Menu interactions
Citizen.CreateThread(function()
	while true do

		Citizen.Wait(0)

		if IsControlJustReleased(0, Keys['F2']) and IsInputDisabled(0) and not isDead and not ESX.UI.Menu.IsOpen('default', 'es_extended', 'inventory') then
			ESX.ShowInventory()
		end

	end
end)
```

### Fix for `esx_addoninventory`:

Go to `esx_addoninventory\server\classes\addoninventory.lua` line 39
Replace `label = Items[name]` to `label = items[name]`
    

> You need to edit your esx_policejob and esx_propery yourself!


## Features
- Drag and drop
- Using items
- Dropping items
- Giving items
- Cash included
- Accounts support (bank, black money, ...)
- Weapons support
- esx_property support
- Another players inventory support
- Fully configurable (check config.lua and html/js/config.js)
- Locale files included (check locales/ and html/locales/ directories)

### Known bugs
- Enable cash in inventory: players can turn money into black money from inventory to glovebox or trunk.

## Language support
Currently, only Dutch is supported. If you want to translate it then feel free to pull a request!

## Screens
    https://i.imgur.com/eHD01Tl.png
    
# Original threads: 
https://forum.fivem.net/t/esx-inventoryhud-glovebox/687328

https://forum.fivem.net/t/release-esx-inventory-hud-2-0/388318

https://forum.fivem.net/t/addon-esx-inventory-hud-vehicle-trunk/458152
