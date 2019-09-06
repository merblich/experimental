# experimental
possible linux kernel changes and other issues
Sept 6, 2019 : Add 3 Possible projects
1) GFP_NOWAIT returns: On embedded systems, if the watermark has dropped below the min level, then GFP_KERNEL calls sleep
Change the behaviour to have them the return ENOMEM : Callers must be able to handle this return versus them sliently sleeping
a) .. skbuff file reviews / mods
./include/linux/skbuff.h : internally uses GF_ATOMIC, but no GFP_KERNEL : has standard link list struct : 
                            What is performance improvrement if we support a faster lookup ,,, do we have a incr or decr order of items?
                            
2) Prime Number scaling : Removes large resource consumption with large power of two's
3) Timer windown: timeouts are now coarser due to fixing cascade issue, but how to we support fine grained or real-time timeouts
