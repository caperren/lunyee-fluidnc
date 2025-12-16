# lunyee-fluidnc

A project which hackily converts the motion controller for a lunyee 3018 cnc machine into one which runs with fluidnc

I decided to make this because the software on the controller which came with the machine is absolutely awful. It's
buggy, missing some standard grbl features, and isn't upgradeable. The "feature" which forced my hand was that it was
hardcoded to disable all the stepper motors a few seconds after motion stopped. This meant that when I tried to do tool
changes from a milling bit to a drilling one while routing PCBs, I would always shift the position of the gantry and the
drilling would fail. This is honestly a shame, because the electronics actually seem quite well-designed.

Maybe I'll design something fully custom in the future, but for now I just used my hot air station to remove the
microcontroller and am piggybacking an esp32-s3-wroom-1 running fluidnc to solve this problem. It also gives me the
added benefit of having it be accessible over the network, which is very convenient.