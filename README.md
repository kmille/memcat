# memcat
Print core memory of a given a process ID (linux specific)

# How to use it
sudo python3 memcat.py $(pidof nextcloud)

# How does it work?
- iterate over /proc/$pid/maps
- open /proc/$pid/mem, seek(x), read(y)
- dump it to a file
- we need to ptrace to $pid so that we can read from /proc/$pid/mem
