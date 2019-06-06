# perls
 I tried to implement ls in perl

#### perls

```
ryuichi@DESKTOP-FNET0JL# time strace -c perl ls.pl test/ > /dev/null   
% time     seconds  usecs/call     calls    errors syscall
------ ----------- ----------- --------- --------- ----------------
  0.00    0.000000           0        21           read
  0.00    0.000000           0       135           write
  0.00    0.000000           0        32           close
  0.00    0.000000           0        94        87 stat
  0.00    0.000000           0        25           fstat
  0.00    0.000000           0        20         2 lseek
  0.00    0.000000           0        35           mmap
  0.00    0.000000           0        14           mprotect
  0.00    0.000000           0         2           munmap
  0.00    0.000000           0       302           brk
  0.00    0.000000           0        70           rt_sigaction
  0.00    0.000000           0         1           rt_sigprocmask
  0.00    0.000000           0        10         8 ioctl
  0.00    0.000000           0         7         7 access
  0.00    0.000000           0       369           mremap
  0.00    0.000000           0         1           execve
  0.00    0.000000           0         2           fcntl
  0.00    0.000000           0        99           getdents
  0.00    0.000000           0         1           readlink
  0.00    0.000000           0         4           getuid
  0.00    0.000000           0         4           getgid
  0.00    0.000000           0         4           geteuid
  0.00    0.000000           0         4           getegid
  0.00    0.000000           0         1           arch_prctl
  0.00    0.000000           0         1           time
  0.00    0.000000           0         2           futex
  0.00    0.000000           0         1           set_tid_address
  0.00    0.000000           0        32           openat
  0.00    0.000000           0         1           set_robust_list
  0.00    0.000000           0         1           prlimit64
------ ----------- ----------- --------- --------- ----------------
100.00    0.000000                  1295       104 total
strace -c perl ls.pl test/ > /dev/null  0.20s user 0.11s system 83% cpu 0.373 total
```

#### ls

```
ryuichi@DESKTOP-FNET0JL# time strace -c ls test/ > /dev/null           
% time     seconds  usecs/call     calls    errors syscall
------ ----------- ----------- --------- --------- ----------------
  0.00    0.000000           0         9           read
  0.00    0.000000           0       218           write
  0.00    0.000000           0        26           close
  0.00    0.000000           0         1           stat
  0.00    0.000000           0        25           fstat
  0.00    0.000000           0        32           mmap
  0.00    0.000000           0        12           mprotect
  0.00    0.000000           0         1           munmap
  0.00    0.000000           0        27           brk
  0.00    0.000000           0         2           rt_sigaction
  0.00    0.000000           0         1           rt_sigprocmask
  0.00    0.000000           0         3         3 ioctl
  0.00    0.000000           0         8         8 access
  0.00    0.000000           0         6           mremap
  0.00    0.000000           0         1           execve
  0.00    0.000000           0        99           getdents
  0.00    0.000000           0         2         2 statfs
  0.00    0.000000           0         1           arch_prctl
  0.00    0.000000           0         1           futex
  0.00    0.000000           0         1           set_tid_address
  0.00    0.000000           0        24           openat
  0.00    0.000000           0         1           set_robust_list
  0.00    0.000000           0         1           prlimit64
------ ----------- ----------- --------- --------- ----------------
100.00    0.000000                   502        13 total
strace -c ls test/ > /dev/null  0.09s user 0.08s system 78% cpu 0.218 total
```
