1 - Download and install the <a href=https://ultimaker.com/software/ultimaker-cura>__latest__ version of Cura</a>. You don't need to use any Cura version from the Flsun V400 USB stick.


2 - Download <a href="Updated%20config%20for%20Cura%20-%20Flsun%20V400%20(v0.5).zip?raw=true">this updated Flsun V400 zip file for Cura (v0.5)</a> and install it as described in the readme file inside it 


3 - Start Cura and add your Flsun V400. Don't start printing!  


4 - Do the Delta, Bed Mesh and Z height calibrations and so on as described in the Flsun V400 manual. Bed mesh when bed has been hot for 15 minutes so it is evenly heated.  


5 - Check that you got the bed height 100% set right <a href="https://ellis3dp.com/Print-Tuning-Guide/articles/first_layer_squish.html">with this great guide</a>  


6 - Calibrate E-steps and add the result into the printer.cfg on your SpeederPad <a href="https://ellis3dp.com/Print-Tuning-Guide/articles/extruder_calibration.html"> with clear steps in this guide</a>   


7 - Calibrate Extrusion Multiplier and add the result in Cura, <a href=https://ellis3dp.com/Print-Tuning-Guide/articles/extrusion_multiplier.html>with yet another great guide by Ellis</a>  

8 - The three driver belts, one in each column, should be equally tightly stretched. Haven't found a guide yet but it is pretty easy, move the extruder down to the exact middle of the bed first (G1 X0 Y0 Z1 F3000). Then place your ear close to each column and pluck the belts like a guitar one by one and listen to the note of each being in same tune. You can pluck the belt on the column's right or left side, one side will not "ring" but the other one will give you a weak but clear base note.

9 - If you still get nozzle crashing into the print with layer shifts and possibly also spaghetti do Klipper's <a href="https://www.klipper3d.org/Delta_Calibrate.html#enhanced-delta-calibration">Enhanced Delta Calibration</a>

<hr>

For further info check out Guilouz very thorough guide https://github.com/Guilouz/Klipper-Flsun-Speeder-Pad

Support settings are not updated from the original Flsun stock file. On my V400 the supports are sometimes hard to remove so I'll see if that can be improved too.

<hr> 

Changes from Flsun's stock V400 files:  

- Combing off
- Infill changed to Gyroid
- Retraction Z hop raised from 0.3 to 0.8
- BED_MESH_PROFILE LOAD="default" added to the start code (although this might be redundant, the jury is still out)
- Material Flow (A.K.A. Extrusion Multiplier) set to a better default value at 98,5 instead of 100. 
- All bed and nozzle temperatures are taken from the currently chosen filament instead of fixed values. So changing filament in Cura actually does something.
- Fan Speed takes it speed value from currently chosen filament instead of a fixed value
- Flow compensation for first layer above sparse infill to prevent blobs at high speeds. Both threshold and flow increase added. Might need tweaking for ordinary bridges but so far very good.
- All speeds now automatically get values derived from the main printing speed instead of fixed individual values. Next step is to take the speed values from the filaments so TPU or PLA and so on to get speeds correctly adjusted automatically. 
- Three walls instead of two  
- Added 0.1mm elephant foot compensation
- The first extruder move from home is down to the edge of bed instead of center, changed in the start code 
  
Thanks to everyone contributing info for the V400!!
