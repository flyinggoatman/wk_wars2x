<<<<<<< HEAD
# Wraith ARS 2X

The **Wraith ARS 2X** (Wraith Advanced Radar System) is a realistic police radar inspired by the real Stalker DSR 2X radar system. It features enhanced realism and experience, including a plate reader that scans vehicles in front and behind the patrol vehicle. The Wraith ARS 2X tracks both large, slower vehicles and smaller, faster targets, displaying speeds of up to four targets simultaneously when both antennas are active. Developers can also hook into the scanner to link it to other resources.

## Installation

1. Download the latest version from [GitHub](https://github.com/flyinggoatman/wk_wars2x/releases).
2. Place the `wk_wars2x` folder into your server's resource folder.
3. Add `ensure wk_wars2x` to your server configuration file.

Your server should now be set up to use the Wraith ARS 2X.

## Default Key Binds

The default key binds can be viewed in-game through the operator manual or in the table below.

| Action                        | Key                      | Description                                                                           |
| ----------------------------- | ------------------------ | ------------------------------------------------------------------------------------- |
| Open remote                   | F5                       | Opens the remote control if the driver is in a police vehicle.                        |
| Close remote                  | ESC / Right Mouse Button | Closes the remote/all displayed UI elements and returns focus to the game.            |
| Lock/unlock front antenna     | Numpad 8                 | Locks the current front antenna speed with audio confirmation.                        |
| Lock/unlock rear antenna      | Numpad 5                 | Locks the current rear antenna speed with audio confirmation.                         |
| Lock/unlock front plate       | Numpad 9                 | Locks the plate currently caught by the front plate reader, with a beep notification. |
| Lock/unlock rear plate        | Numpad 6                 | Locks the plate currently caught by the rear plate reader, with a beep notification.  |
| Copy front plate to clipboard | Numpad 1                 | Copies the front plate text to clipboard and shows a notification.                    |
| Copy rear plate to clipboard  | Numpad 3                 | Copies the rear plate text to clipboard and shows a notification.                     |
| Toggle keylock                | L                        | Toggles the keylock state, disabling keybinds until keylock is toggled again.         |

## Script Configuration

All configurations are done inside the `config.lua` file. Key options include setting default key binds, configuring operator menu defaults, and adjusting UI scale and safe zone.

### Key Configuration

```lua
-- Default key binds
CONFIG.keyDefaults = {
    remote_control = "f5",
    key_lock = "l",
    front_lock = "numpad8",
    rear_lock = "numpad5",
    plate_front_lock = "numpad9",
    plate_rear_lock = "numpad6"
}
```

### Operator Menu Defaults

```lua
-- Default values for the operator menu
CONFIG.menuDefaults = {
    fastDisplay = true,     -- Display faster targets
    same = 0.6,             -- Same lane sensitivity
    opp = 0.6,              -- Opposite lane sensitivity
    beep = 0.6,             -- Audible beep volume
    voice = 0.6,            -- Verbal lock confirmation volume
    plateAudio = 0.6,       -- Plate reader audio volume
    speedType = "mph",      -- Speed unit (mph or kmh)
    fastLock = false,       -- Automatic speed locking
    fastLimit = 60          -- Speed limit for automatic locking
}
```

### UI Scale and Safe Zone

```lua
-- UI scale and safe zone configuration
CONFIG.uiDefaults = {
    scale = {
        radar = 0.75,
        remote = 0.75,
        plateReader = 0.75
    },
    safezone = 20  -- Safe zone size
=======
# Wraith ARS 2X - Plate Reader with Copy to Clipboard Feature

The **Wraith ARS 2X** (Wraith Advanced Radar System) is a realistic police radar that takes heavy inspiration from the real Stalker DSR 2X radar system. It includes a plethora of features from the DSR 2X such as the new operator menu, to improve the realism and experience whilst using the newest instalment from the collection of Wraith radar systems. Previously with WraithRS, vehicle speeds were only displayed in the target window, with no priority to certain vehicles (such as large and slower vehicles, or smaller and faster vehicles). The Wraith ARS 2X tracks both large and faster, smaller targets and displays the speeds of both in the target windows, meaning the radar can track 4 different speeds with both antennas turned on and transmitting. Alongside the new radar system is also a plate reader that scans in front and behind the patrol vehicle, a BOLO plate can also be set, but developers can also hook into the scanner to link it into other resources.

In this version, the Wraith ARS 2X has been enhanced with the ability to copy license plate numbers directly from the plate reader interface. Officers can now easily copy the front and rear license plate numbers to their clipboard by clicking the "Copy Front Plate" and "Copy Rear Plate" buttons located under each plate in the plate reader UI. This new feature makes it easier for police to record license plates.

## Installation

Installing the Wraith ARS 2X into your FiveM can be done by following the listed steps below.

1. Download the latest version of the resource from [here](https://github.com/WolfKnight98/wk_wars2x/releases)
2. Open the zip file and place the `wk_wars2x` folder into your server's resource folder
3. Open up your server configuration file and add `ensure wk_wars2x` to your resource start list

It's now installed! When you boot your server you should see a Wraith ARS 2X message as well as the version check message.

## Default key binds

Although these can be viewed ingame through the operator manual, the default key binds are listed below.


| **Action**                    | **Key**                           | **Description**                                                                                                                                                                                                                                                                                                                             |
| ----------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Open Remote**               | `F5`                                  | Opens the remote control. This only works if you are the driver of a police vehicle (must have the vehicle class `VC_EMERGENCY`).                                                                                                                                                                                                               |
| **Close Remote**              | `ESC` or **Right Mouse Button** | Closes the remote and all displayed UI elements, returning focus to the game.                                                                                                                                                                                                                                                                     |
| **Lock/Unlock Front Antenna** | `Numpad 8`                            | Locks the current speed of the front antenna. If a fast speed is displayed, the system will lock the fast speed. Otherwise, it will lock the strong speed. When you lock a speed, the radar will audibly tell you which antenna is being locked, and the relative direction of the target compared to the patrol vehicle (e.g., "Front Closing"). |
| **Lock/Unlock Rear Antenna**  | `Numpad 5`                            | Locks the current speed of the rear antenna. If a fast speed is displayed, the system will lock the fast speed. Otherwise, it will lock the strong speed. When you lock a speed, the radar will audibly tell you which antenna is being locked, and the relative direction of the target compared to the patrol vehicle (e.g., "Rear Away").      |
| **Lock/Unlock Front Plate**   | `Numpad 9`                            | Locks the plate currently caught by the front plate reader. An audible beep will also be heard unless the plate reader audio option in the operator menu is changed.                                                                                                                                                                              |
| **Lock/Unlock Rear Plate**    | `Numpad 6`                            | Locks the plate currently caught by the rear plate reader. An audible beep will also be heard unless the plate reader audio option in the operator menu is changed.                                                                                                                                                                               |
| **Copy Front Plate**          | `Numpad 1`                            | Copies the front license plate text to the clipboard**only if** the plate reader's UI is **visible** and the **front plate box contains text**. If the plate box is empty or the UI is not active, an error notification is displayed.                                                                                          |
| **Copy Rear Plate**           | `Numpad 3`                            | Copies the rear license plate text to the clipboard**only if** the plate reader's UI is **visible** and the **rear plate box contains text**. If the plate box is empty or the UI is not active, an error notification is displayed.                                                                                            |
| **Toggle Keylock**            | `L`                                   | Toggles the**keylock state**. When enabled, **none of the keybinds** will work until keylock is toggled **off** again.                                                                                                                                                                                                          |

## Script configuration

All of the configuration for the Wraith ARS 2X is done inside the `config.lua` file, below is a copy of the configuration file. All of the options have comments to describe what they do, along with the available options you can set. You have the ability to change the key binds for the large and small key set, the default operator menu options, and the default UI element scale and safezone.

```lua
-- Radar fast limit locking
-- When enabled, the player will be able to define a fast limit within the radar's menu, when a vehicle
-- exceeds the fast limit, it will be locked into the fast box. Default setting is disabled to maintain realism
CONFIG.allow_fast_limit = true

-- Radar only lock players with auto fast locking
-- When enabled, the radar will only automatically lock a speed if the caught vehicle has a real player in it.
CONFIG.only_lock_players = false

-- In-game first time quick start video
-- When enabled, the player will be asked if they'd like to view the quick start video the first time they
-- open the remote.
CONFIG.allow_quick_start_video = true

-- Allow passenger view
-- When enabled, the front seat passenger will be able to view the radar and plate reader from their end.
CONFIG.allow_passenger_view = true

-- Allow passenger control
-- Dependent on CONFIG.allow_passenger_view. When enabled, the front seat passenger will be able to open the
-- radar remote and control the radar and plate reader for themself and the driver.
CONFIG.allow_passenger_control = true

-- Set this to true if you use Sonoran CAD with the WraithV2 plugin
CONFIG.use_sonorancad = false

-- Sets the defaults of all keybinds
-- These keybinds can be changed by each person in their GTA Settings->Keybinds->FiveM
CONFIG.keyDefaults =
{
	-- Remote control key
	remote_control = "f5",

	-- Radar key lock key
	key_lock = "l",

	-- Radar front antenna lock/unlock Key
	front_lock = "numpad8",

	-- Radar rear antenna lock/unlock Key
	rear_lock = "numpad5",

	-- Plate reader front lock/unlock Key
	plate_front_lock = "numpad9",

	-- Plate reader rear lock/unlock Key
	plate_rear_lock = "numpad6",

	-- Plate reader copy front plate key
	copy_front_plate = "numpad1",

	-- Plate reader copy rear plate key
	copy_rear_plate = "numpad3",
}

-- Here you can change the default values for the operator menu, do note, if any of these values are not
-- one of the options listed, the script will not work.
CONFIG.menuDefaults =
{
	-- Should the system calculate and display faster targets
	-- Options: true or false
	["fastDisplay"] = true,

	-- Sensitivity for each radar mode, this changes how far the antennas will detect vehicles
	-- Options: 0.2, 0.4, 0.6, 0.8, 1.0
	["same"] = 0.6,
	["opp"] = 0.6,

	-- The volume of the audible beep
	-- Options: 0.0, 0.2, 0.4, 0.6, 0.8, 1.0
	["beep"] = 0.6,

	-- The volume of the verbal lock confirmation
	-- Options: 0.0, 0.2, 0.4, 0.6, 0.8, 1.0
	["voice"] = 0.6,

	-- The volume of the plate reader audio
	-- Options: 0.0, 0.2, 0.4, 0.6, 0.8, 1.0
	["plateAudio"] = 0.6,

	-- The speed unit used in conversions
	-- Options: mph or kmh
	["speedType"] = "mph",

	-- The state for automatic speed locking. This requires CONFIG.allow_fast_limit to be true.
	-- Options: true or false
	["fastLock"] = false,

	-- The speed limit required for automatic speed locking. This requires CONFIG.allow_fast_limit to be true.
	-- Options: 0 to 200
	["fastLimit"] = 60
}

-- Here you can change the default scale of the UI elements, as well as the safezone size
CONFIG.uiDefaults =
{
	-- The default scale of the UI elements.
	-- Options: 0.25 - 2.5
	scale =
	{
		radar = 0.75,
		remote = 0.75,
		plateReader = 0.75
	},

	-- The safezone size, must be a multiple of 5.
	-- Options: 0 - 100
	safezone = 20
>>>>>>> main/master
}
```

## Suggestions

<<<<<<< HEAD
To suggest improvements, open a pull request with your code changes, or create an issue with a detailed description. Code should be well-formatted and commented.

## Reporting Issues

Open an issue if you encounter problems, providing detailed information on the issue and steps to reproduce it when applicable.
=======
If there is an improvement that you think should be made, open a pull request with your modified code, I will then review your request and either accept/deny it. Code in a pull request should be well formatted and commented, it will make it much easier for others to read and understand. In the event that you want to suggest something, but don't know how to code, open an issue with the enhancement tag and then fully describe your suggestion.

## Reporting issues/bugs

Open an issue if you encounter any problems with the resource, if applicable, try to include detailed information on the issue and how to reproduce it. This will make it much easier to find and fix.
>>>>>>> main/master
