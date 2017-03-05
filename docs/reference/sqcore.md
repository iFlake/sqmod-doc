## SqCore

---
The SqCore class provides some core functions to the script, such as events.

## SqCore.Reload
`null SqCore.Reload(bool status)`

This function reloads the script.

    SqCore.Reload(true);

## SqCore.Reloading
`bool SqCore.Reloading()`

This function returns `true` if the script is reloading and `false` if it isn't.

    if (SqCore.Reloading() == false) SqCore.Reload(true);

## SqCore.ReloadBecause
`null SqCore.ReloadBecause(int header, object payload)`

This function reloads the script and sets the header and payload

    SqCore.ReloadBecause(12, "Command");

## SqCore.SetReloadInfo
`null SqCore.SetReloadInfo(int header, object payload)`

This function sets the reload header and payload while the script is being reloaded

    SqCore.SetReloadInfo(11, "Script update");
    
## SqCore.GetReloadHeader
`int SqCore.GetReloadHeader()`

This function returns the reload header.

    local reload_header = SqCore.GetReloadHeader();

## SqCore.GetReloadPayload
`object SqCore.GetReloadPayload()`

This function returns the reload payload.

    local reload_payload = SqCore.GetReloadPayload();

## SqCore.GetState
`int SqCore.GetState()`

This function returns the current plugin state.

    local state = SqCore.GetState();

## SqCore.SetState
`null SqCore.SetState(int state)`

This function sets the plugin state.

    SqCore.SetState(0);

## SqCore.GetOption
`string SqCore.GetOption(string name)`

This function gets an option.

    local option = SqCore.GetOption(optionname);

## SqCore.GetOptionOr
`string SqCore.GetOptionOr(string name, string value)`

This function gets an option if it exists, and sets it if it doesn't.

    local option = SqCore.GetOption(optionname, value);

## SqCore.SetOption
`null SqCore.SetOption(string name, string value)`

This function sets an option.

    SqCore.SetOption(name, value);

## SqCore.GetBlip
`Entity::SqBlip SqCore.GetBlip(int id)`

This function retrieves a blip instance from its ID.

    local blip = SqCore.GetBlip(12);

## SqCore.GetCheckpoint
`Entity::SqCheckpoint SqCore.GetCheckpoint(int id)`

This function retrieves a checkpoint instance from its ID.

    local checkpoint = SqCore.GetCheckpoint(12);

## SqCore.GetKeybind
`Entity::SqKeyBind SqCore.GetKeyBind(int id)`

This function retrieves a key instance from its ID.

    if (key == SqCore.GetKeyBind(12)) return 0;

## SqCore.GetObject
`Entity::SqObject SqCore.GetObject(int id)`

This function retrieves an object instance from its ID.

    local object = SqCore.GetObject(12);

## SqCore.GetPickup
`Entity::SqPickup SqCore.GetPickup(int id)`

This function retrieves a pickup instance from its ID.

    local pickup = SqCore.GetPickup(12);

## SqCore.GetPlayer
`Entity::SqPlayer SqCore.GetPlayer(int id)`

This function retrieves a player instance from its ID.

    local player = SqCore.GetPlayer(12);

## SqCore.GetVehicle
`Entity::SqVehicle SqCore.GetVehicle(int id)`

This function retrieves a vehicle instance from its ID.

    local vehicle = SqCore.GetVehicle(12);

## SqCore.DestroyBlip
`bool DestroyBlip(int id, int header, object payload)`

This function deletes the specified blip after the current execution is complete, and specifies a header and payload for the current execution to use.

    SqCore.DestroyBlip(12, 8, "Race complete");

## SqCore.DestroyCheckpoint
`bool DestroyCheckpoint(int id, int header, object payload)`

This function deletes the specified checkpoint after the current execution is complete, and specifies a header and payload for the current execution to use.

    SqCore.DestroyCheckpoint(12, 8, "Race complete");

## SqCore.DestroyKeybind
`bool DestroyCheckpoint(int id, int header, object payload)`

This function deletes the specified keybind after the current execution is complete, and specifies a header and payload for the current execution to use.

    SqCore.DestroyKeybind(12, 8, "Key pressed");

## SqCore.DestroyObject
`bool DestroyObject(int id, int header, object payload)`

This function deletes the specified object after the current execution is complete, and specifies a header and payload for the current execution to use.

    SqCore.DestroyObject(12, 8, "Unstreamed");

## SqCore.DestroyPickup
`bool DestroyPickup(int id, int header, object payload)`

This function deletes the specified pickup after the current execution is complete, and specifies a header and payload for the current execution to use.

    SqCore.DestroyPickup(12, 8, "Unstreamed");

## SqCore.DestroyVehicle
`bool DestroyVehicle(int id, int header, object payload)`

This function deletes the specified vehicle after the current execution is complete, and specifies a header and payload for the current execution to use.

    SqCore.DestroyVehicle(12, 8, "Owner left");

## SqCore.OnPreLoad
`SqSignalImpl SqCore.OnPreLoad()`

This function returns an event which gets executed immediately before the primary ScriptLoad event.

    SqCore.OnPreLoad().Connect(function ()
    {
        print("Initializing scripts...");
    });

## SqCore.OnPostLoad
`SqSignalImpl SqCore.OnPostLoad()`

This function returns an event which gets executed immediately after the primary ScriptLoad event.

    SqCore.OnPostLoad().Connect(function ()
    {
        print("Initialized scripts");
    });

## SqCore.OnUnload
`SqSignalImpl SqCore.OnUnload()`

This function returns an event which gets executed immediately before the scripts are being unloaded.

    SqCore.OnUnload().Connect(function ()
    {
        Broadcast.Message("Server closing...");
    });

## SqCore.LoadScript
`bool SqCore.LoadScript(string name, bool delay)`

This function loads a script immediately if `delay` is false and puts it in the loading queue if `delay` is true, and returns true on success and false on error.

    SqCore.LoadScript("database.nut", false);

## SqCore.On
`table SqCore.On()`

This function returns a table which contains all primary events.

    SqCore.On().ScriptLoaded.Connect(function ()
    {
        print("Scripts loaded");
    });
