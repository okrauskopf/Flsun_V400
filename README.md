1 - <a href="https://www.3djake.com/3d-printer-accessories/buildplateadhesion">Buy adhesive spray here</a> or somewhere else (or hairspray) and never have a print detach from the PEI bed ever again.   

 
2 - Download and install the <a href=https://ultimaker.com/software/ultimaker-cura>latest version of Cura</a>


3 - Install <a href="Updated%20config%20for%20Cura%20-%20Flsun%20V400%20(v0.1).zip?raw=true">this zip file</a> as described in the readme file inside it 


4 - Start Cura and add your Flsun V400. Don't start printing!  


5 - Do the Delta, Bed Mesh and Z height calibrations and so on as described in the Flsun V400 manual  


6 - Check that you got it set right <a href="https://ellis3dp.com/Print-Tuning-Guide/articles/first_layer_squish.html">with this great guide</a>  


7 - Calibrate E-steps and add the result into the printer.cfg on your SpeederPad <a href="https://ellis3dp.com/Print-Tuning-Guide/articles/extruder_calibration.html"> with clear steps in this guide</a>   


8 - Calibrate Extrusion Multiplier and add the result in Cura, <a hef="https://ellis3dp.com/Print-Tuning-Guide/articles/extrusion_multiplier.html">with yet another great uide by Ellis</a>  

9 - The three driver belts, one in each column, should be equally tightly stretched. Haven't found a guide yet but it is pretty easy to place your ear close and pluck them like a guitar one by one and listen to the note of each being in same tune. You can pluck the belt on either each columns right or left side, one side will not "ring" but the other one will give you a weak but clear base note.

10 - If you still get nozzle crashing into the print with layer shifts and possibly also spaghetti do Klipper's <a href="https://www.klipper3d.org/Delta_Calibrate.html#enhanced-delta-calibration">Enhanced Delta Calibration</a>

<hr>

Support settings are not updated from the original Flsun stock file. On my V400 the supports are very hard to remove so I'll see if that can be improved too.

<hr> 

Changes from Flsun's stock V400 files:  

- BED_MESH_PROFILE LOAD="default" added to start code
- First move down the edge of bed instead of center, changedin start code 
- Combing off
- Infill changed to Gyroid
- Fan Speed takes it speed value from currently chosen filament instead of a fixed value
- All bed and nozzle temperatures are taken from currently chosen filament instead of fixed values
- Flow compensation for first layer above sparse infill to prevent blobs at high speeds. Both threshold and flow increase added. Might need tweaking for ordinary bridges but so far very good.
- All speeds now automatically get values derived from the main printing speed instead of fixed individual values. Next step is to take the speed values from the filaments so TPU or PLA and so on to get speeds correctly adjusted automatically. 
- Added 0.1mm elephant foot compensation
- Three walls instead of two  
  
Thanks to everyone contributing info for the V400!!
