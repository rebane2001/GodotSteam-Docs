# Godot 4.x Change-Log

A history of all changes to [the ***godot4*** branch.](https://github.com/CoaguCo-Industries/GodotSteam/tree/godot4){ target="\_blank" }

---

## Version 4.6

- Added: new Remote Storage enum to WorkshopFileType
- Added: two new UGC enums to ItemState and ItemPreviewType
- Added: two new Friends class constants
- Added: new function `dismissGamepadTextInput()`
- Added: new Remote Play enum, form factor for VR headset
- Added: two new result enums; not supported and family size limit exceeded
- Added: three new enums to NetworkingConfigValue
- Added: new general constant ACCOUNT_ID_INVALID
- Changed: FEATURE_KIOSK_MODE enum now deprecated
- Changed: minor housekeeping by rearranging some functions
- Changed: k_ESteamNetworkingConfig_SDRClient_DebugTicketAddress was replaced by k_ESteamNetworkingConfig_SDRClient_DevTicket, value is the same but reference changed
- Changed: updated in-editor docs
- Fixed: spelling error in `getProfileItemPropertyInt()` bind
- Removed: App Lists class functions, callbacks, etc. due to SDK 1.59 changes
- Removed: Remote Play enums mistakenly added as constants

## Version 4.5.4

- Added: missing k_nSteamNetworkingSend_AutoRestartBrokenSession to constants
- Added: two missing Input constants: INPUT_HANDLE_ALL_CONTROLLERS and INPUT_MAX_ACTIVE_LAYERS
- Changed: `getInputTypeForHandle()` now returns int / enum instead of string for device models
- Changed: updated in-editor docs for missing content
- Changed: order of constants to be alphabetic
- Changed: changed returned variable name to `need_to_accept_tos` in `item_updated` callback
- Changed: Github Actions scripts, one for Vulkan and another for version numbers

## Version 4.5.3

- Fixed: `requestClanOfficerList()` using wrong internal function, ***thanks to sepTN***

## Version 4.5.2

- Fixed: `exchangeItems()`, `generateItems()`, and `startPurchase()` using wrong array size function, ***thanks to sepTN***
- Fixed: various spelling issues in in-editor docs, ***thanks to sepTN***

## Version 4.5.1

- Fixed: app ID automatically being set to 480, now default is 0 which makes GodotSteam ignore auto-setting app ID

## Version 4.5

- Added: two new arguments to `steamInit()` and `steamInitEx()` to set your app ID and run_callbacks interally, ***thanks to GreenFox***
- Added: two Music class callbacks
- Changed: `generateItems(0`, `exchangeItems()`, `getItemsByID()`, and `startPurchase()` all list-based arguments are now PoolIntArrays
- Changed: `getItemsByID()` now takes one argument, counts the elements in the passed array instead
- Changed: `getItemsWithPrices()` no longer requires any arguments passed to it
- Changed: in-editor docs have been updated
- Fixed: `getResultItems()` now returns all item data
- Fixed: missing DEFVAL for `steamInitEx()`
- Fixed: Joy Con name in `getInputTypeForHandle()`
- Removed: `getNumItemsWithPrices()` as it was unnecessary

## Version 4.4.2

- Fixed: `requestEquippedProfileItems()` was missing method bind, ***thanks to BOTLANNER***
- Fixed: `get_ticket_for_web_api` callback for getting actual ticket buffer, ***thanks to dicarne***
- Fixed: compiler complaining about comparison between Steam enum and GodotSteam enum for `steamInitEx()`
- Fixed: `getListenSocketAddress()` fixed to provide the actual address and optional port
- Changed: different defaults in Github Actions files
- Changed: `createBrowser()` now sends proper NULL when empty string passed
- Changed: `html_browser_ready` from callback to proper call result
- Changed: cast handle in `setSize()` as Steam HHTMLBrowser
- Removed: unnecessary steam_appid.txt from zips in Github Actions

## Version 4.4.1

- Fixed: missing descriptions for some in-editor functions/signals
- Fixed: `receiveMessagesOnChannel()`, `receiveMessagesOnPollGroup()`, and `receiveMessagesOnConnection()` had overwriting dictionary keys

## Version 4.4

- Added: new enums and constant related to new Steam initialization function
- Added: new enums for NetworkingConfigValue
- Added: new intialization function `steamInitEx()` that is more verbose
- Added: new UGC function `getUserContentDescriptorPreferences()`
- Added: new Remote Play function `startRemotePlayTogether()`
- Changed: UGC function `setItemTags()` to have new argument for admin tags
- Changed: compatible with Steamworks SDK 1.58
- Changed: in-editor docs now reflect all changes

## Version 4.3.1

- Fixed: wrong variant type for join_requested

## Version 4.3

- Added: full GodotSteam documentation into the editor
- Added: `steamShutdown()` to allow Steamworks to be manually shutdown
- Added: `requestEquippedProfileItems()` function and `equipped_profile_items` callback
- Added: Steam Deck as Steam Input type
- Changed: all enums are now directly linked to their SDK counterparts
- Changed: `getDigitalActionData()` returned keys are now state and active
- Changed: names of some Steam enums to be cleaner and leaner
- Changed: `getAppInstallDir()` now returns dictionary with absolute path and install size
- Fixed: some missing enum binds
- Fixed: missing function argument binds
- Fixed: `get_ticket_for_web_api` sending back strings
- Removed: enums that are not in the SDK but Valve's docs

## Version 4.2.2

- Added: new Input callback `input_gamepad_slot_change`
- Added: new User callback `get_ticket_for_web_api`
- Added: new User function `getAuthTicketForWebApi()`
- Changed: `getAuthSessionTicket()` argument is now optional, defaults to NULL

## Version 4.2.1

- Added: new return values for `overlay_toggled`; this will break compatibility with this
- Added: new Input and Parental Settings enums
- Added: new UGC Content Descriptor ID enums
- Added: new UGC functions `removeContentDescriptor()`, `addContentDescriptor()`, and `getQueryUGCContentDescriptors()`
- Added: new signal `filter_text_dictionary_changed`
- Changed: `getAuthSessionTicket()` now uses networking identities
- Changed: `gamepad_text_input_dismissed` now passes back the app ID
- Changed: Steam Input max analog and digital actions values
- Removed: ERegisterActivationCodeResult due to removal in SDK

## Version 4.2

* Added: various backports from Godot 3.x branch
* Fixed: options array size for new Networking classes and memory leaks, ***thanks to profour***
* Fixed: need for godotsteam.sh file on some Linux systems, ***thanks to mikix***

## Version 4.1.5

* Added: networking type message constants
* Added: more descriptions and tutorial links to in-editor docs
* Added: `avatar_image_loaded` callback to get raw response from Steamworks
* Changed: brought 4.x branch up-to-speed with master / 3.x branch
* Changed: enums now bound with BIND_ENUM_CONSTANT, ***thanks to raulsntos***
* Changed: bitwise enums now bound with BIND_ENUM_BITWISE_CONSTANT, ***thanks to raulsntos***
* Changed: platform of 'osx' to new 'macos'
* Fixed: platform of 'osx' not being recognized so the module doesn't get added
* Fixed: `microtransaction_auth_response` spelling for callback
* Fixed: `getLobbyData()` not returning UTF-8 encoded string
* Fixed: `sendLobbyChatMsg()` truncating non-English strings
* Fixed: `filterText()` truncating input; ***thanks to _tcoxon***
* Removed: MarketingMessageFlags as they don't exist in the header files

## Version 4.1.4

* Changed: layout to make Git cloning easier
* Changed: `submitItemUpdate()` to use null if no notes are passed, ***thanks to mashumafi***
* Fixed: incorrect use of io failure
* Fixed: DEFVAL type mismatch, ***thanks to raulsntos***
* Fixed: `getSessionConnectionInfo()` using old networking struct
* Removed: unused networking stricts

## Version 4.1.3

* Fixed: config.py and SCsub so that Linux compiling will link Steam correctly

## Version 4.1.2

* Changed: brought branch up to speed with GodotSteam 3.17.4

## Version 4.1.1

* Fixed: wrong arch in SCsub file
* Fixed: registering class in register_types.cpp

## Version 4.1

* Changed: brought branch up to speed with GodotSteam 3.17.1
* Fixed: various small issues to get it running with Godot alpha 1

## Version 4.0

* Added: Initial build, highly experimental!
