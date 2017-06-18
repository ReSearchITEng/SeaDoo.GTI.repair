# SeaDoo.GTI.repair
How to choose/repair SeaDoo GTI Sea Scooter with no repair manual.

CONS:
- As one would expect, nobody gives any warranty or assumes any responsability for the results of these hacks. 

PROS:
- cheap batteries
- unleash all the power of your GTI

## Choose the right seascooter model
I planned to buy initially an Aqua Ranger or Dolphin sea scooters (cheaper than GTI), but after getting feedbacks, I understood that even for 5yr old are not strong enough, - and they were right. So the min. version is the GTI.

With the Aqua Ranger money one can buy a 2nd hand GTI, (which, unfortunatelly may turn develop some issues - which we'll discuss later)

## Battery:
### Travel note: 
- If you plan to travel by airplane, don't take the battery with you, the airline will not allow your battery, even if it's dry/sealed Pb battery. 

### Good parts:
- with ~30$ you can get a new battery from any car battery shop, in any country. I am very happy with it and it was very wise, I saved ~70$ by not getting the original ones, which have identical parameters (sealed/dry Pb battery, same power or even better).
- They are so cheap, you can buy 2, to assure you for a really long day :). 
- Myself never managed to deplete a fully charged one in a single day.

### Getting fancy:
If you want to be more fancy, get into the Lithuium ones (even SeaDoo started to provide such option for the high end sea scooters).
As per my research, LiFePO4 would be the most appropriate, but, you may have other opinion.
Here are some options: https://www.aliexpress.com/popular/lifepo4-battery-12v.html . I never ordered them, and I am not aware how they ship them, as airlines rarelly accept batteries, so discuss with seller. The good part is that you have insurance, and if it doesn't reach you, you get a voucher or something like this with that amount.

Ensure you make the series/parallel arangement such that your voltage is within a Pb battery (11.x - 13.y)

## HOW TO OPEN
Under the battery, there are 4+1 rubbers.
The one with a whole in it, does not have any screw underneath, so you may want to leave it as is.
Using a piercing tool, remove the 4 rubbers, and under you will find 4 screws (1-4), just like in the picture below. Unscrew them.

![Open to access CVI electronics board - Screws](/images/GTI_howToOpenCVI_NumberedScrews.jpg)

In order to lift up this plastic section, you have to screw two long enough enough screws. They should be 6mm with more fine threads (I guess Pitch 0.75mm). Note, there are 2 types of threads in 6mm screws, choose the fine one. Anyway, you try them, should enter easily if they fit.
Screw them in wholes f6 f7 ~1cm to max 1.5cm deep - don't force them too deep, ensuring you won't damage the chasis below.
Tie some ropes from both of them, and use a tool to ensure you lift from both sides, keeping the ropes parallel.

Here is the tool I created:


You will have to use quite some force pulling up, you may need someone to help you.


## Electronics board (CVI)
The measured current the GTI takes from the battery when running outside of water is 2A. Probably under water it's more.
The original FET Transistor was a pretty weak one, and probably the board was using the chip on the board to open the transistor with a specific frequency, as opposed to always on (DC like).   
This is probably the reason for which, when we used the original transistor continuously (DC), it burned after few minutes of work.
Original FET was: IRL3303 (30V/38A;0.026 ohm) : irf.com/product-info/datasheets/data/irl3303.pdf
We searched for better ones, same package: TO220. Here are some examples:
- IRFB3077P8F
- PSMN1R8_30PL
- AU IRFB8405
- IRLB3034PBF

We managed to find the IRLB3034PBF (40V/195A;0.0017 ohm - way much better than original by all means http://www.infineon.com/dgdl/irlb3034pbf.pdf?fileId=5546d462533600a40153566027b22585)

