# LegacyFuel
[![LegacyFuel](https://i.imgur.com/cdJoEia.png)](https://github.com/Betererokay/LegacyFuel)


### About
Fuel script originally by https://github.com/InZidiuZ/LegacyFuel
Updated this useful fuel script for ESX. (Updated FXManifest and removed-replaced deprecated code)

![Includes fuel bar and speedo](https://i.imgur.com/ivukrYc.png)


### Installation
1) Download the latest version in the "Releases" tab on GitHub.
2) Drag & drop the folder into your `resources` server folder.
3) Configure the config file to your liking.
4) Add `start LegacyFuel` to your server config.

### Exports
There are currently two (client-sided) exports available, which should help you control the fuel level for vehicles whenever needed.

```
SetFuel(--[[Vehicle--]] vehicle, --[[Float/Int: (0-100)--]] value)
GetFuel(--[[Vehicle--]] vehicle) -- Returns the vehicle's fuel level.
```

**Example usage:**
```
function SpawnVehicle(modelHash)
    local vehicle = CreateVehicle(modelHash, coords.x, coords.y, coords.z, true, false)

    exports["LegacyFuel"]:SetFuel(vehicle, 100)
end

function StoreVehicleInGarage(vehicle)
    local plate = GetVehicleNumberPlateText(vehicle)
    local fuelLevel = exports["LegacyFuel"]:GetFuel(vehicle)

    TriggerServerEvent('vehiclesStored', plate, fuel)
end
