## A common issue with Flsun V400  
  
Problems with your Flsun V400 nozzle sometimes scraping or crashing into filament -&gt; layer shifts -&gt; spaghetti?

  
## Guide

1 - Make sure all screws are tight on your printer. Stepper motors, extruder block, extruder/arm connectors, bed, the three columns and so on. 

2 - Tighten all three belts to be exactly equally tight. With the extruder at the very top adjust the belt tightening knobs to tune them all to somewhere between 45-50Hz, but exactly the same all three! Use a guitar tuning app on your mobile phone listening to the sounds from the belts when you pluck them. When done make sure you tighten all the screws for the belts.  
    
3 - Do the Delta, Bed Mesh and Z height calibrations and so on as described in the Flsun V400 manual. **Do it when the bed has been hot for 15 minutes so it is evenly heated.**  
  
4 - Calibrate E-steps and add the result into the printer.cfg on your SpeederPad <a href="https://ellis3dp.com/Print-Tuning-Guide/articles/extruder_calibration.html"> with clear steps in this guide</a>   
  
5 - Calibrate Extrusion Multiplier (Flow) and add the result in Cura, <a href=https://ellis3dp.com/Print-Tuning-Guide/articles/extrusion_multiplier.html>with yet another great guide by Ellis</a>. This setting is per filament type. PETG and PLA can need different settings but even different makes _can_ differ. 
  
6 - Check that you got the bed height 100% set right <a href="https://ellis3dp.com/Print-Tuning-Guide/articles/first_layer_squish.html">with this great guide</a>. Also do test prints of a first layer while you fine tune Z on the pad screen live while printing.  
  
If you have carefully done each step above, and with a bit of luck, the printer will now work fine. If not try this: Download <a href="Updated%20config%20for%20Cura%20-%20Flsun%20V400%20(v0.8).zip?raw=true">this updated Flsun V400 zip file for Cura (zip v0.8)</a> and install it as described in the readme file inside it 

## These are the changes in the above zip done to the Flsun's stock V400 files for Cura  

- Infill changed to Gyroid
- Retraction Z hop raised from 0.3 to 0.8
- Combing off (can make prints take a longer time though, you can experiment with it on or off)
- Material Flow (A.K.A. Extrusion Multiplier) set to a better default value at 98,5 instead of 100 but you should still calibrate for your filament and change in Cura after adding these files! 
- The first extruder move from home is down to the edge of the bed instead of center to prevent filament drops in the bed center, changed in the start code  
- BED_MESH_PROFILE LOAD=default added to the start code
- All bed and nozzle temperatures are taken from the currently chosen filament instead of fixed values. So changing filament in Cura actually does something.
- Fan Speed takes it speed value from currently chosen filament instead of a fixed value
- Flow compensation added for first layer above sparse infill to prevent blobs at high speeds. Both threshold and flow increase added. Might need tweaking for ordinary bridges but so far very good.
- All speeds now automatically get values derived from the main printing speed instead of fixed individual values. Next step is to take the speed values from the filaments so TPU or PLA and so on to get speeds correctly adjusted automatically. 
- Added 0.1mm elephant foot compensation
  
Nothing else is changed from the original Flsun stock file you received on the USB stick. 
  
Thanks to everyone contributing info for the V400!!
  
## More info  
  
For further info check out Guilouz very thorough guide https://github.com/Guilouz/Klipper-Flsun-Speeder-Pad


