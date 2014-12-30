=================
MAPLAB_M4L
by Mark IJzerman, December 2014
=================

DESCRIPTION:

MAPLAB_M4L provides a bridge between Ableton Live (using Max for Live) and the Statemachine recently implemented in Isadora as used in the HKU MAPLAB.
It is made to work with Ableton Live Suite 9 and Isadora 1.x and 2.x together with the PE_StatemachineReceive, PE_CreateInputs, and PE_CreateOutputs, but should work as long as it obeys the SIL-UDP protocol.

-----------------

MODULES:<br>

The MAPLAB_M4L package consists of four modules.
A2I stands for "Ableton TO Isadora". I2A stands for "Isadora TO Ableton".

== A2I_SimpleAnalysis ==
When Init is pressed, sends out amplitude data (on PE_CreateInputs) from the track it is placed on in Ableton. Has controls in Ableton to make sure the right slope is achieved. In most cases, simple analysis will do.

You can place this module on multiple tracks, but beware:
*warning* be sure NOT to change the name of the track after the module is placed. It will NOT work anymore when you save and load your file in Ableton.

== A2I_AdvancedAnalysis ==
When Init is pressed, sends out extensive analysis  data (on PE_CreateInputs) from the track it is placed on. Uses Tristan Jehan's Analyzer~ external. Pretty CPU intensive, and can be quite buggy. So use only if you really need that brightness, noisiness, attack, etc. data!

You can place this module on multiple tracks, but beware:
*warning* be sure NOT to change the name of the track after the module is placed. It will NOT work anymore when you save and load your file in Ableton.

== I2A_ValueMapper ==
When Init is pressed, eight inputs appear on the PE_CreateOutputs module, where one can send values from Isadora TO Ableton. The values will appear in Ableton, and can be mapped to ANY parameter by clicking "MAP" besides the number and then on the parameter one wants to map.

This module can only be placed ONCE in an Ableton session. Eight values to map should however be enough ;)

== I2A_ClipLauncher ==
When Init is pressed, two inputs appear on the PE_CreateOutputs module.
By sending a number between zero and one to "clip number", one can launch clip 1 to 10 in Ableton. By sending any number to "clipstop", one can stop the track from playing. It has to change from the previous value it had, as the PE modules only react to changes (sadly.)

If it takes some time before your clip starts, you might want to set the quantization in Ableton (its in the top left. By default it says "1 Bar".

You can place this module on multiple tracks, but beware:
*warning* be sure NOT to change the name of the track after the module is placed. It will NOT work anymore when you save and load your file in Ableton.