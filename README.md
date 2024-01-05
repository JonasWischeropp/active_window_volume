# Change Volume of Active Window
## Usage Example
|Action |Command|
|-|-|
| Set volume to 50% | `set_volume_of_active_window 50` |
| Increase by 20%   | `set_volume_of_active_window +20`|
| Decrease by 3%    | `set_volume_of_active_window -3` |

## Dependencies
- pacmd (to modify the volume)
- xdotool (to get the active window)

## Setup
- Place the files in some folder that is part of `$PATH`
- Place `update_volume_on_new_sink > /dev/null &` in `$HOME/.profile`
(or somewhere else where it automatically starts).

## Further Information
The current volume level of each process is stored in `$HOME/.volume`.  
This can be altered by changing the `storage_path` variable in `set_volume_of_active_window` and `update_volume_on_new_sink`.  
`update_volume_on_new_sink` runs in the background and sets the volume of new processes. 

## Known Issue
When skipping in a video in Firefox the volume shortly jumps to the original volume before it is updated by `update_volume_on_new_sink`.
If someone has an idea on how to fix this, please let me know.