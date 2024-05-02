
# Max Worklog

This is the week by week log for Maxwell Kramer for ECE 445 in Spring 2024

# 01/26/2024

Met with Ben and agreed oon general idea and being group mates. Ben seems to have an idea he's passionate about so I'm inclined to go with that. No technical details from me yet to put here.

# 02/05/2024

Since last week we've looked for and gotten a new teammate with Manas Tiwari. Currently, work is just for homework, project remains in brainstorming stage.

# 02/12/2024

Discussed with machine shop and were suprisingly told our plans for a 3d-printed casing for our devices was the best route. Proposal document was submitted as well for our general idea.

Moved onto initial PCB work. I've been asked to focus on the power subsystem for now, with possible work in other subsystems after.

After some reserach and TA consultation we'll be going with a buck convertor over a linear regulator. This is due to heating concerns as the rocket launch may overheat the beacon device.

Since all other systems will run on 3.3V we will chose the adafruit LM3671 3.3V Buck Convertor for our devices.

![alt_text](https://github.com/maxwellk24/ECE445_Notebook/blob/main/Max/%231%20(power%20subsystem).PNG)

Ben is working on UI and MCU while Manas works on Sensors and Communication.

# 02/19/2024

Focusing this week on Design Document and Review assignments. We have had some workload issues with Manas. So far he has not shown much technical work ability. His involvement in the design doc has been low, with minimal written work despite the remaining time we have. Ben and I also have reviewed his work thus far and have some concerns about copy/paste or even AI tool usage for some work he has done. He has not been able to explain with much confidence the material he has done and does not seem to undertsand a lot of the subsystems he's been assigned, despite the few weeks he's had them.

We had a serious sit down with him to discuss these issues in a professional manner in accord with the team contract. He denied any practices that violated any guidlines. Ben and I have discussed privately that we will discuss this matter with the TA soon.

# 02/26/2024

Mainly working on PCB design for orders next week. Design review went well though so we have confidence in our current work. My focus besides power will be hardware testing so until parts arrive can't do much. Currently working though getting the order put together. 

Digikey order to get the GPS units should go out this week.

# 03/04/2024

Final PCB push this past weekend. Files for the tracker board were submitted.

![alt_text](https://github.com/maxwellk24/ECE445_Notebook/blob/main/Max/%232%20(tracker%20pcb).PNG)

GPS units are in for testing. We met to get some more tasks divided between us. I'm gonna be working on power testing as well as general board testing and solder work when more parts and boards arrive.

# 03/11/2024

Spring break so no work done

# 03/18/2024

Our tracker boards have been delivered. Beacon boards will be worked on later as we just need to remove the UI and re-organize the PCB.

I did some testing with the actual boards to check traces and ensure we have proper continuity between all nets and pads. Otherwise I did not do much work this week. Other classes and developments in my job hunt have needed my attention. Further parts orders and testing will be done soon as I can.

# 03/25/2024

Other parts orders put in, should arrive next week. More board tsting shows everything is working well. I'm currently waiting for the rest of the hardware in order to continue my responsibilities. Ben has let me know for the moment that software should be ok for now so I'm not needed elsewhere.

Tracker PCB work has started, will be ready for 4th round next week.

SMD parts from TA were in the friday of this week. Solder work to get them on will be done this weekend.

# 04/01/2024

Adafruit parts, including screen and radios are in. Also have ATMega's in as well. I'm soldering the microprocessor so Ben can test upload some code in isolation to check our ISP upload method. Essentially, we are using an arduino uno as a programmer instead of an on circuit programmer. This allowed us to save on parts, design time, and cost.

## Upload Issues

We have run into some trouble with the ISP uplad method. It seems unable to connect to the board and upload no matter what we do. Ben and I have traded the uno and board with the ATMega this week and have not been able to resolve it. This seems to be some sort of clock issue. The crystal oscillator is attactched with its capacitors so the extrenal clock should be running. This may continue to next week.

This is currently my main focus along with power testing

# 04/08/2024

Uploading to board continues to fail. We are considering a potential abandonment of the PCB but will consult with our TA at mock demo before doing so completely. Ben and Manas hav been doing the heavy lifting for software at the moment. I have moved to power testing fully. Remaining SMD parts and beacon board are incoming this week as well.

## Power

The Convertor seems to be having issues. The output stays at 0.0033V or ambiant voltage no matter input combo. The convertor has 4 pins. Vin, GND, 3V, and EN as shown below. I powered using the 5V out of an arduino board and the LiPo batteries we plan to use. Neither has worked. The breakout board it comes on seems to have EN (enable) set high with the Vin net but this shouldn't stop it. Replacements have been oreded in case this is a part malfunction.

![alt_text](https://github.com/maxwellk24/ECE445_Notebook/blob/main/Max/%233%20(buck%20converter).PNG)

## Software

Ben also made me aware of some work challenges with Manas again. It seems he has had little technical work/success so far and the radio system is far behind. With PCB on hold and power parts being delivered I am switching over to radio testing and code.

Simple RX/TX code was available at LoRa forums for testing the funcionality of the radio. After looking up the arduino uno pin mapping to hook up to the radio, I got RX and TX working (with dummy values as I had the single radio at this point). This only took an afternoon for setup and code testing to get started.

As I understand it Ben has library issues he's handling while core functionality of every subsystem seems to be working in isolation. Consolidation to a breadboard prototype is next phase after further radio work.

# 04/15/2024

## Radio

Work going well, we were able to get one way communication from beacon to tracker working with outline we had. We reversed and also got tracker to beacon working. The beacon sends GPS data while the Tracker sends frequency changes. What we have left is to get constant 2-way RXTX up. This was actually a larger challenge than originally thought. The data packets we send using the LoRa library commands are actually clogging both devices and preventing receives to happen when 2-way is up. To try and fix this we set data transmissions to occur once at a set time interval and to have the devices constantly listen otherwise.

## Group Issues

It should noted that at this point Manas has not been able to deliver any technical progress beyond some simple button input parsing for the UI, which Manas admitted to not testing before handing it off.

We had another serious sit down with him. Ben and I have essentially picked up all technical work and Manas has not been involved much. We had a team meeting and discussed these concerns and frustrations.

Essentially, after the issues with the design document Manas showed improved commitment to the team and we gave the benefit of the doubt. When we assigned him the UI and radio work we decided not to look over his shoulder. At team meetings he explained that he was working on his tasks and would consult if needed. As Ben and I had our own work and class load we left it there. However, as seen above the work he finished was not much.

At this point we jus did not trust his ability to finish any work within our strained deadlines. We did explain this choice and all other concerns to him in a professional manner. He explained to us that he was out of his depth in terms of technical knowledge and that he had been having trouble completing tasks due to mental health challenges, for which he has DRES accomodations for.

For his part, he was understanding of our position and we agreed to move forward as stated above.

# 04/22/2024

Final demo for us was Friday and outdoors, as stated in our design docs.

We did face a few last challenges...

## Screen

The original screen we had broke between testing sessions. The solder connections tore and there was a chip in the left bottom corner of the screen. We aquired a spare from a friend of Ben's. He integrated the screen with some siple but tedious code rewrites while I still worked on radio testing and fine tuning.

## Radio

After some testing by the NHB near the union we got fully 2-way communcation working! This was confirmed by Ben standing across Green street and getting accurate distance and direction on the UI. This was even with just using wires as the antennas. Intgration remains the only major obstacle.

## Integration

At this point integration was all that remained. Ben and I worked a lot of long nights this week to consolidate our code and test. After a while we got everything together on a single file for both devices. 

Testing was tedious. Final testing showed that some unseen errors were hampering consistent connection. After a lot of debugging we found that there were faulty net lines in the breadboards we used and this was causing the tracker radio to not properly receive data.

## Casing

We did make some basic 3D laser cut casing. Ben provided some old wood for to use. The design was simple enough, just rough dimensions to house the breadboards in rectangular house with connection holes drilled into them. The Tracker did have extra holes laser cut to allow for screen and button access.

# FINAL NOTES

This was a fun project despite the technical challenges we faced. The wide range of domains we explored like RF were fun to work with. I'm glad Ben mentioned this project, I think had we had another semester to work on this it could be a very succesful product.
