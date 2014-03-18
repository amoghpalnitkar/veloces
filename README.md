veloces
=======

An Efficient I/O Scheduler for Solid State Devices
The veloces I/O scheduler is a scheduler that does basic merging and read preference. It peforms bundling of writes according to block boundary.
Its main uses include efficient scheduling for non rotational solid state devices.

Applying patch : 
	
	patch -p1 < pathtopatch/veloces

Compile linux kernel.

Selecting the scheduler : 
	
	cat /sys/block/sdX/queue/scheduler

		If the patch has been applied and kernel has been compiled correctly, then this command would show 'veloces' in the scheduler list. 
		*sdX - select the appropriate device for which scheduler is to be selected

	echo veloces > /sys/block/sdX/queue/scheduler

