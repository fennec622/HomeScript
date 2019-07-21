# HomeScript
Python script for command line control of [HomeBridge](https://github.com/nfarina/homebridge) (HomeKit)

Used to toggle Homebridge accessories On or Off via python script, no Home app required. You can set up a cronjob to enable automation, scripting and mimic other HomeKit functionalities

## Examples
`python homeScript.py MainLight 0`  | Switch off  
`python homeScript.py MainLight 1`  | Switch on  
`python homeScript.py MainLight`   | Toggle

## Easy Match
The script doesn't require full names of the accessories.  

**For example**, if your light is called "MainLight", you can run:  
`python homeScript.py MainLight 0` or  
`python homeScript.py main 0`  
The script will automatically search for matching substrings and set the accessory value

## Group Actions
You can set multiple accessories (of the same type) in a single command:  
`python homeScript.py all lights 1`  
`python homeScript.py all switches 0`  

## Dependencies
 - Python requests library
 - Python JSON library
 
 ## Installation
  - Install the requests library `pip install requests` or `pip3 install requests`
  - Move **homeScript.py** to a convenient location
  - Edit the script to include your homebridge URL, port and authorization key
  - Change permissions `chmod +x /path/to/homeScript.py` (on linux)

## Usage
`python homeScript.py [option] [argument]`
### Options:
 - list : lists all available HomeKit accessories
   - Usage: `python homeScript.py list [argument]`
   - Arguments:
     - \<none\> : lists accessory names
     - aid : lists accessory names with AID value
     - iid : lists accessory names with IID value
     - id : lists accessory names with AID and IID
     - type : lists accessory names with type [Lightbulb, Switch, Fan, etc.]
     - value : lists accessory names current state
     - all : lists all of the above
     - json: prints all attributes in JSON string format
 - \<accessory-name\> : [EasyMatch Supported] toggles the accessory On or Off, or sets to value
   - Usage: `python homeScript.py <accessory-name> [value]`
   - Values:
     - \<none\> : toggles the state
     - 0 : sets to OFF
     - 1 : sets to ON
 - all : sets value of multiple HomeKit accessories
   - Usage: `python homeScript.py all <accessory-type> value`
   - \<accessory-type\> : [EasyMatch Supported] sets all \<accessory-type\> to \<value\>
 - help : prints usage info

## PRs and Commit Template
PRs and commits that you make to this repo must include the following:  
- Type: bug-fix or enhancement
- Description: Brief description about what the commit achieves
- Notes: (heads ups/pointers to other developers if necessary)

<hr/>

## Changelog
### v3.0
- Added group actions. You can now set values for all matching accessory types

### v2.2
- Added json listing support

### v2.1
- Added type support to identify accessory type
- Updated help doc

### v2.0
- List of accessories are now automatically fetched from the homebridge, instead of having to manually set them up in the script

### v1.3
- Added easy name matching

### v1.2
- Added help doc
- Added listing

### v1.1
- Added toggling

### v1.0
- Initial release

<hr/>

