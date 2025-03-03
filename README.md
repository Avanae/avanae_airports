# Avanae Airports

Thank you for using Avanae Airports! This interactive airport is meant to enhance the roleplay experience by making it more immersive and is part of a project series I’m creating making public transport actually usable.   

# Basic Features

* Fully animated.
* Simple yet sleek UI design.
* NPC Stewardesses at key locations that can be fully customized and can even look like regular players and can be fully animated.
* Transported through cutscene. Not just a simple teleport.
* Very extensive config file. Pretty much anything you need to change can be done through the config.
* Support for multiple frameworks. Current support includes **esx**, **qb** or **qbox** or **standalone**. A template is provided for integrating a **custom framework** if applicable.
* Support for multiple notifications. Current support includes **esx**, **qb**, **ox**, **wasabi**, **okok** or the ability for integrating a **custom notification**.
* Support for multiple progress bars. Current support includes **esx**, **qb**, **ox**, or the ability for integrating a **custom progress bar**.
* Support for multiple target solutions. Current support includes **ox**, **qb**, **qtarget** or the ability for integrating a **custom target solution**.
* Code is very commented in an attempt to guide the user what parts of the code does.
* Performance friendly 0.00-0.01ms on the resmon if using the eye tracker. 0.00-0.03ms if using markers.

# Requirements

* oxmysql
* ox-lib is optional but recommended.

# Items

> [!IMPORTANT]
> Do not skip this step. The resource won't work if you do.


You have to add items manually if you don't use the default ESX inventory. This means editing the required files and down below you can find the instructions to do so based on your inventory. If your inventory is not listed, the script uses the following items:   

`planeticket_lsia`, `planeticket_ssa` and `planeticket_cayo`  

> [!NOTE]
> For Ox Inventory navigate to data/items.lua.

```
    ['planeticket_lsia'] = {
        label = 'Planeticket (LSIA)',
        weight = 10,
        stack = true,
        close = false,
        description = "A plane ticket to Los Santos International Airport.",
    },

    ['planeticket_ssa'] = {
        label = 'Planeticket (Sandy)',
        weight = 10,
        stack = true,
        close = false,
        description = "A plane ticket to the Sandy Shores Airstrip.",
    },

    ['planeticket_lsia'] = {
        label = 'Planeticket (Cayo)',
        weight = 10,
        stack = true,
        close = false,
        description = "A plane ticket to the Cayo Perico Airstrip.",
    },
```   

> [!NOTE]
> For QB Inventory navigate to qb-core/shared/items.lua.   
   
```
 planeticket_lsia  = { 
    name = 'planeticket_lsia', 
    label = 'Planeticket (LSIA)', 
    weight = 10, 
    type = 'item', 
    image = 'planeticket_lsia', 
    unique = false, 
    useable = false, 
    shouldClose = false, 
    description = 'A plane ticket to Los Santos International Airport.' 
},

 planeticket_ssa  = { 
    name = 'planeticket_ssa', 
    label = 'Planeticket (Sandy)', 
    weight = 10, 
    type = 'item', 
    image = 'planeticket_ssa', 
    unique = false, 
    useable = false, 
    shouldClose = false, 
    description = 'A plane ticket to the Sandy Shores Airstrip.' 
},

 planeticket_cpa  = { 
    name = 'planeticket_cpa', 
    label = 'Planeticket (Cayo)', 
    weight = 10, 
    type = 'item', 
    image = 'planeticket_cpa', 
    unique = false, 
    useable = false, 
    shouldClose = false, 
    description = 'A plane ticket to the Cayo Perico Airstrip.' 
},
``` 

# Configuration

A quick run down of what every option does:

|         Config value        |                                        Description                                             |               Default Value             |
|-----------------------------|------------------------------------------------------------------------------------------------|-----------------------------------------|
| Config.Language             | Defines the language for the resource.                                                         | `en`                                    |
| Config.Framework            | Defines the framework the resource will use.                                                   | `esx`                                   |
| Config.UpdateCheck          | Defines if there will be checked for updates.                                                  | `true`                                  |
| Config.DatabaseCheck        | Defines if there will be a database item check.                                                | `true`                                  |
| Config.Phone                | Defines what phone will be used for the resource.                                              | `none`                                  |
| Config.Target               | Defines what target system will be used for the resource.                                      | `none`                                  |
| Config.HelpText             | Defines what helptext will be used for the resource.                                           | `default`                               |
| Config.Notifications        | Defines what notification system will be used for the resource.                                | `default`                               |
| Config.ProgressBar          | Defines what progress bar will be used for the resource.                                       | `default`                               |
| Config.Cutscene             | Defines if you will fade to black teleport to your destination, or through a cutscene          | `default`                               |
| Config.Airline              | Defines the display name of the Airline of which communication will be sent out.               | `FlyUS`                                 |
| Config.Currency             | Defines the display currency that you use.                                                     | `$`                                     |
| Config.TicketPrice          | Defines the global price for a plane ticket.                                                   | `1100`                                  |
| Config.UseBuild2189         | Defines wether or not you use build 2189 or higher.                                            | `false`                                 |
| Config.StreamingCayoPerico  | Defines wether or not you stream Cayo Perico assets.                                           | `false`                                 |
| Config.TicketMachineModel   | Defines the model used for the ticket machines.                                                | `prop_train_ticket_02`                  |
| Config.EnableBlips          | Defines if there will be blips shown on the map.                                               | `true`                                  |
| Config.StewardessLSIA       | Defines the vector2 location for the Stewardess at LSIA.                                       | `vector2(-1039.34, -2747.94)`           |
| Config.StewardessSandy      | Defines the vector2 location for the Stewardess at Sandy Shores.                               | `vector2(1748.99, 3296.80)`             |
| Config.StewardessCayo       | Defines the vector2 location for the Stewardess at Cayo Perico.                                | `vector2(4459.69, -4479.87)`            |
| Config.Zones                | Defines marker zones. Only relevant if `Config.Target` is set to none.                         | `Pos={x=0.0,y=0.0,z=0.0},`              |

# NPC Configuration   

> [!IMPORTANT]
> Please note that if you use vMenu to decide the look for them, you have to go back 1 for every Drawable Texture. For example: You wish to use Shoes 51 with texture 4, make sure you note it as:
> `['shoes_1'] = 51, ['shoes_2'] = 3,`
> This is because vMenu starts at texture #1 whereas Skinchanger starts at #0.


It's possible to create Peds for usage along side the resource. You can style them however you like, or use default peds. Down below you can find an example.   

```
Config.AirportPeds = {
	{
		Location = "Stewardess at LSIA",
		Position = vector3(-1039.34, -2747.94, 20.35),
		Heading = 330.0,
		Model = "mp_f_freemode_01",
		Scenario = 'CODE_HUMAN_MEDIC_TIME_OF_DEATH',
		AnimDict = nil,
		Animation = nil,
		AnimLoop = true,

		Appearance = {
			-- Face
			['sex'] = 1,
			['face'] = 40,      
			['makeup_1'] = 0,       ['makeup_2'] = 0,
			['makeup_3'] = 0,       ['makeup_4'] = 0,
			['hair_1'] = 60,        ['hair_2'] = 0,
			['hair_color_1'] = 0,   ['hair_color_2'] = 0,
			['eyebrows_1'] = 32,    ['eyebrows_2'] = 0,
			['eyebrows_3'] = 0,     ['eyebrows_4'] = 0,
			['eye_color'] = 2,
			['beard_1'] = 1,        ['beard_2'] = 0,
			['beard_3'] = 0,        ['beard_4'] = 0,
			['lipstick_1'] = 0,     ['lipstick_2'] = 0,
			['lipstick_3'] = 0,     ['lipstick_4'] = 0,

			-- Clothing
			['tshirt_1'] = 104,     ['tshirt_2'] = 16,
			['torso_1'] = 306,      ['torso_2'] = 7,
			['decals_1'] = 0,       ['decals_2'] = 0,
			['arms'] = 7,
			['pants_1'] = 6,        ['pants_2'] = 2,
			['shoes_1'] = 0,        ['shoes_2'] = 3,
			['helmet_1'] = -1,      ['helmet_2'] = 0,
			['chain_1'] = 13,       ['chain_2'] = 0,
			['glasses_1'] = -1,     ['glasses_2'] = 0,
			['bproof_1'] = 0,       ['bproof_2'] = 0,		
			['mask_1'] = 0,         ['mask_2'] = 0,		
			['bags_1'] = 0,         ['bags_2'] = 0,	
			['ears_1'] = -1,        ['ears_2'] = 0
		},
	},	
```
