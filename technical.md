# computing: technical guidelines

To use the HPC cluster: see
[here](https://kb.wisc.edu/stat/internal/page.php?id=106361)
and more generally
[here](https://kb.wisc.edu/stat/internal/page.php?id=105902)
for Statistics computing facilities.
You will need your netID to access these kb pages.

To use clusters from our group: the full machine names are
`namexx.stat.wisc.edu`
where you replace `name` by `darwin` or `franklin`,
and `xx` by some appropriate number.

| name | number | RAM | number of cores
| -----|--------|-----|----------------
| darwin | 00 | 256 GB | 24
|   | 01 |  48 GB | 8 cores
|   | 02 | 512 GB | 24 cores (2 threads each)
|   | 03, 04, 05, 06 | 256 GB | 24 cores (2 threads each)
|   | 12 |  64 GB | 8 cores
|   | 13 | 128 GB | 24 cores (2 threads each)
| franklin | 00, 01, 02 | 1 TB | 64 cores (2 threads each)
|   | 03 | 512 GB | 64 cores (2 threads each)

darwin also has NVIDIA cuda capabilities (GPU)

All: 64 bits. 2.0-3.5 GHz
(low GHz can be actually faster than high GHz with better 'bus' speed).  
You can get more details with these commands:

```shell
cat /proc/cpuinfo
cat /proc/meminfo
free -g
```

After logging into a machine, do a little 'knock knock' to see who is there
already, and to check how busy the machine is, using 'top':

```shell
top
```

Doing `top` and checking the current usage (cpu and memory) of the machine is very important.

You will have priority over users like 'condor' or 'nobody'.
But check for others in our group. They will appear under their user name.
If you see that people in our group are already running 6 jobs on a machine
that has 8 cores, then log out and log into a different darwin machine to start
your own jobs. (again, do 'top' to see this information). If you plan to use all
cores from many machines for a few days, you should email me and others in the
group before starting. This is to make sure that there remains enough cores for
others to run their own jobs.

The cluster and HPC machines have access to files on the AFS system.
Don't keep large files in AFS, because you could quickly exceed your quota
and your jobs would fail.
Put intermediary files and any large files in `/nobackup/` on darwin,
`nobackup2/` on franklin and
`/workspace/` on the HPC. Create for yourself a folder inside,
named after your login name, and then put your large files in there
(well organized of course).

---
back [home](readme.md)
