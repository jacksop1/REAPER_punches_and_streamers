Punches and Streamers
---------------------
by Christian Afonso

![Alt text](/doc/screenshot1.png?raw=true "Punches and Streamers screenshot")

REAPER script to overlay punches and streamers over video track. Still early version, some
things might not work all the time. Also contains a simple script to generate sections of
click track for rendering as audio stem.

Usage:
- Copy this folder (or clone this repository) into %APPDATA%/Roaming/REAPER/Scripts/ 
  (on Windows - look for analogous folder on Mac). You can change the folder name, but
  in that case you have to change the "ScriptPath" constant at the beginning of the lua
  file to the new folder name, so the script can find its data files.
- Load the script "update_streamers.lua" in the Actions Menu (and assign a shortcut)
- Add markers named "P" or "PUNCH" for punches, "S [N COLOR]" or "STREAMER [N COLOR]"
  for streamers (with concluding punch). Optional parameters: N = streamer duration 
  in seconds (default 2), COLOR = streamer color (default white, currently also possible:
  [red yellow green blue magenta cyan black]; add a - in front to suppress the default
  punch at the end, e.g. "S 3 -red" for a 3-second red streamer without a punch)
- Call the script. It should add two tracks "Streamers" and "Punches" (if not already
  existing), add a "remove black" Video FX to the Punches track, and then add items for 
  every marker matching the specified patterns. The streamer items should automatically
  get a "streamer" Video FX. Additional "Streamers" tracks are created in case of over-
  lapping streamers (due to only one concurrent video effect being displayed per track).

- To use the simple "update_click_track" utility script, place marker pairs "C IN" and
  "C OUT" and call the script. It will create a Click Source item between each pair of
  markers on a new track "Click".
  
This script is a work-in-progress, provided as-is without any warranties.
You can use it however you like, but at your own risk (Meaning: save your project 
before using it!)
I'm very open for feedback and suggestions: chr.afonso AT gmail.com

