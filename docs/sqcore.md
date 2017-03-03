## SqCore

---
The SqCore class provides some core functions to the script, such as events.

## function SqCore.Reload
`null SqCore.Reload(bool status)`

This function reloads the script.

    SqCore.Reload(true);

## function SqCore.Reloading
`bool SqCore.Reloading()`

This function returns `true` if the script is reloading and `false` if it isn't.

    if (SqCore.Reloading() == false) SqCore.Reload(true);

## function SqCore.ReloadBecause
`null SqCore.ReloadBecause(int header, object payload)`

This function does something.

    SqCore.ReloadBecause(...);

## function SqCore.SetReloadInfo
`null SqCore.SetReloadInfo(int header, object payload)`

This function does something.

    SqCore.SetReloadInfo(...);
    
## function SqCore.GetReloadHeader
`int SqCore.GetReloadHeader()`

This function returns the reload header.

    var reload_header = SqCore.GetReloadHeader();

## function SqCore.GetReloadPayload
`object SqCore.GetReloadPayload()`

This function returns the reload payload.

    var reload_payload = SqCore.GetReloadPayload();

## function SqCore.GetState
`int SqCore.GetState()`

This function returns the current plugin state.

    var state = SqCore.GetState();

## function SqCore.SetState
`null SqCore.SetState(int state)`

This function sets the plugin state.

    SqCore.SetState(0);

