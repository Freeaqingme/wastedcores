# The Linux Scheduler: a Decade of Wasted Cores

As a central part of resource management, the OS thread scheduler must maintain
the following, simple, invariant: make sure that ready threads are scheduled on
available cores.

As simple as it may seem, we found that this invariant is often broken in Linux.
Cores may stay idle for seconds while ready threads are waiting in runqueues.

The patches provided in this repo intend to fix performance bugs caused
many-fold performance degradation for synchronization-heavy scientific
applications, 13% higher latency for kernel make, and a 14-23% decrease in
TPC-H throughput for a widely used commercial database.

# Applying these patches

If you don't know how to apply these patches, you can check out
[this repo](https://github.com/turbine1991/build_ubuntu_kernel_wastedcores),
which provides some easy means to get you up and running.

# Important note about the patches

The provided patches fix the issues encountered with our workloads,
but they are not intended as generic bug fixes. They may have unwanted side
effects and result in performance loss or energy waste on your machine.

But then of course, you could always try :)

# Article

http://www.ece.ubc.ca/~sasha/papers/eurosys16-final29.pdf

**The Linux Scheduler: a Decade of Wasted Cores**, Jean-Pierre Lozi, Baptiste
Lepers, Justin Funston, Fabien Gaud, Vivien Quéma, and Alexandra Fedorova. *To
appear in* Proceedings of the Eleventh European Conference on Computer Systems
*(EuroSys '16), London, United Kingdom, 2016.*
