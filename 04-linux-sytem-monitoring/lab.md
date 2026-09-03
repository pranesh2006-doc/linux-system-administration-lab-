root
ubuntu@Ubuntu:~$ whoami
ubuntu
ubuntu@Ubuntu:~$ nproc
2
ubuntu@Ubuntu:~$ lscpu
Architecture:                x86_64
  CPU op-mode(s):            32-bit, 64-bit
  Address sizes:             48 bits physical, 48 bits virtual
  Byte Order:                Little Endian
CPU(s):                      2
  On-line CPU(s) list:       0,1
Vendor ID:                   AuthenticAMD
  Model name:                AMD Ryzen 5 7520U with Radeon Graphics
    CPU family:              23
    Model:                   160
    Thread(s) per core:      1
    Core(s) per socket:      2
    Socket(s):               1
    Stepping:                0
    BogoMIPS:                5589.29
    Flags:                   fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pg
                             e mca cmov pat pse36 clflush mmx fxsr sse sse2 ht s
                             yscall nx mmxext fxsr_opt rdtscp lm constant_tsc re
                             p_good nopl xtopology nonstop_tsc cpuid extd_apicid
                              tsc_known_freq pni pclmulqdq ssse3 fma cx16 sse4_1
                              sse4_2 movbe popcnt aes xsave avx f16c rdrand hype
                             rvisor lahf_lm cmp_legacy cr8_legacy abm sse4a misa
                             lignsse 3dnowprefetch ssbd vmmcall fsgsbase bmi1 av
                             x2 bmi2 rdseed adx clflushopt sha_ni arat
Virtualization features:     
  Hypervisor vendor:         KVM
  Virtualization type:       full
NUMA:                        
  NUMA node(s):              1
  NUMA node0 CPU(s):         0,1
Vulnerabilities:             
  Gather data sampling:      Not affected
  Ghostwrite:                Not affected
  Indirect target selection: Not affected
  Itlb multihit:             Not affected
  L1tf:                      Not affected
  Mds:                       Not affected
  Meltdown:                  Not affected
  Mmio stale data:           Not affected
  Old microcode:             Not affected
  Reg file data sampling:    Not affected
  Retbleed:                  Mitigation; untrained return thunk; SMT disabled
  Spec rstack overflow:      Mitigation; SMT disabled
  Spec store bypass:         Not affected
  Spectre v1:                Mitigation; usercopy/swapgs barriers and __user poi
                             nter sanitization
  Spectre v2:                Mitigation; Retpolines; STIBP disabled; RSB filling
                             ; PBRSB-eIBRS Not affected; BHI Not affected
  Srbds:                     Not affected
  Tsa:                       Not affected
  Tsx async abort:           Not affected
  Vmscape:                   Not affected
ubuntu@Ubuntu:~$ free -h
               total        used        free      shared  buff/cache   available
Mem:           3.3Gi       1.2Gi       225Mi        55Mi       2.1Gi       2.1Gi
Swap:             0B          0B          0B
ubuntu@Ubuntu:~$ df -h
Filesystem      Size  Used Avail Use% Mounted on
tmpfs           680M  2.1M  678M   1% /run
/dev/sda2        35G  9.1G   24G  29% /
tmpfs           1.7G     0  1.7G   0% /dev/shm
tmpfs           1.7G  8.0K  1.7G   1% /tmp
none            1.0M     0  1.0M   0% /run/credentials/systemd-journald.service
none            1.0M     0  1.0M   0% /run/credentials/systemd-resolved.service
tmpfs           340M   88K  340M   1% /run/user/1000
ubuntu@Ubuntu:~$ du -sh
18M	.
ubuntu@Ubuntu:~$ du -sh ~
18M	/home/ubuntu
ubuntu@Ubuntu:~$ ls
Desktop  Documents  Downloads  Music  Pictures  Public  Templates  Videos  cybersecurity  linux-admin-lab  snap
ubuntu@Ubuntu:~$ du -sh ~linux-admin-lab
du: cannot access '~linux-admin-lab': No such file or directory
ubuntu@Ubuntu:~$ du -sh linux-admin-lab
448K	linux-admin-lab
ubuntu@Ubuntu:~$ du -sh ~/linux-admin-lab
448K	/home/ubuntu/linux-admin-lab
ubuntu@Ubuntu:~$ du -sh ~/linux-admin-lab/*
8.0K	/home/ubuntu/linux-admin-lab/01-linux-basics
20K	/home/ubuntu/linux-admin-lab/02-linux-permission
24K	/home/ubuntu/linux-admin-lab/filesystem
20K	/home/ubuntu/linux-admin-lab/linux-process-management
ubuntu@Ubuntu:~$ du -sh ~/*
4.0K	/home/ubuntu/cybersecurity
4.0K	/home/ubuntu/Desktop
4.0K	/home/ubuntu/Documents
4.0K	/home/ubuntu/Downloads
448K	/home/ubuntu/linux-admin-lab
4.0K	/home/ubuntu/Music
1.6M	/home/ubuntu/Pictures
4.0K	/home/ubuntu/Public
784K	/home/ubuntu/snap
4.0K	/home/ubuntu/Templates
4.0K	/home/ubuntu/Videos
ubuntu@Ubuntu:~$ vmstat
procs -----------memory---------- ---swap-- -----io---- -system-- -------cpu-------
 r  b   swpd   free   buff  cache   si   so    bi    bo   in   cs us sy id wa st gu
 2  0      0 335320  25340 2059948    0    0  1526    52  322    2  1  3 96  0  0  0
ubuntu@Ubuntu:~$ vmstat -h

Usage:
 vmstat [options] [delay [count]]

Options:
 -a, --active           active/inactive memory
 -f, --forks            number of forks since boot
 -m, --slabs            slabinfo
 -n, --one-header       do not redisplay header
 -s, --stats            event counter statistics
 -d, --disk             disk statistics
 -D, --disk-sum         summarize disk statistics
 -p, --partition <dev>  partition specific statistics
 -S, --unit <char>      define display unit
 -w, --wide             wide output
 -t, --timestamp        show timestamp
 -y, --no-first         skips first line of output

 -h, --help     display this help and exit
 -V, --version  output version information and exit

For more details see vmstat(8).
ubuntu@Ubuntu:~$ htop
ubuntu@Ubuntu:~$ 
ubuntu@Ubuntu:~$ top

top - 11:18:21 up 19 min,  1 user,  load average: 0.09, 0.16, 0.27
Tasks: 200 total,   1 running, 199 sleeping,   0 stopped,   0 zombie
%Cpu(s):  5.6 us,  5.6 sy,  0.0 ni, 88.9 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st 
MiB Mem :   3398.8 total,    322.1 free,   1314.9 used,   2039.7 buff/cache     
MiB Swap:      0.0 total,      0.0 free,      0.0 used.   2083.9 avail Mem 

    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND                                                                                                                                                        
   2929 ubuntu    20   0 4030228 411524 190640 S  33.3  11.8   0:28.64 gnome-shell                                                                                                                                                    
   4062 ubuntu    20   0 1815052 396388 163280 S   8.3  11.4   0:13.75 ptyxis                                                                                                                                                         
   4502 ubuntu    20   0   13444   5888   3716 R   8.3   0.2   0:00.01 top                                                                                                                                                            
      1 root      20   0   25352  16612  11652 S   0.0   0.5   0:05.23 systemd                                                                                                                                                        
      2 root      20   0       0      0      0 S   0.0   0.0   0:00.02 kthreadd                                                                                                                                                       
      3 root      20   0       0      0      0 S   0.0   0.0   0:00.00 pool_workqueue_release                                                                                                                                         
      4 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-rcu_gp                                                                                                                                               
      5 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-sync_wq                                                                                                                                              
      6 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-kvfree_rcu_reclaim                                                                                                                                   
      7 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-slub_flushwq                                                                                                                                         
      8 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-netns                                                                                                                                                
     10 root       0 -20       0      0      0 I   0.0   0.0   0:00.31 kworker/0:0H-kblockd                                                                                                                                           
     12 root      20   0       0      0      0 I   0.0   0.0   0:01.70 kworker/u8:0-events_unbound                                                                                                                                    
     13 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-mm_percpu_wq                                                                                                                                         
     14 root      20   0       0      0      0 S   0.0   0.0   0:00.15 ksoftirqd/0                                                                                                                                                    
     15 root      20   0       0      0      0 I   0.0   0.0   0:00.53 rcu_preempt                                                                                                                                                    
     16 root      20   0       0      0      0 S   0.0   0.0   0:00.00 rcu_exp_par_gp_kthread_worker/0                                                                                                                                
     17 root      20   0       0      0      0 S   0.0   0.0   0:00.11 rcu_exp_gp_kthread_worker                                                                                                                                      
     18 root      rt   0       0      0      0 S   0.0   0.0   0:00.05 migration/0                                                                                                                                                    
     19 root      20   0       0      0      0 S   0.0   0.0   0:00.00 kprobe-optimizer                                                                                                                                               
     20 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/0                                                                                                                                                  
     21 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/0                                                                                                                                                        
     22 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/1                                                                                                                                                        
     23 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/1                                                                                                                                                  
     24 root      rt   0       0      0      0 S   0.0   0.0   0:00.05 migration/1                                                                                                                                                    
     25 root      20   0       0      0      0 S   0.0   0.0   0:00.28 ksoftirqd/1                                                                                                                                                    
     28 root      20   0       0      0      0 S   0.0   0.0   0:00.00 kdevtmpfs                                                                                                                                                      
     29 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-inet_frag_wq                                                                                                                                         
     30 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_kthread                                                                                                                                              
     31 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_rude_kthread                                                                                                                                         
     32 root      20   0       0      0      0 S   0.0   0.0   0:00.00 kauditd                                                                                                                                                        
     33 root      20   0       0      0      0 S   0.0   0.0   0:00.00 khungtaskd                                                                                                                                                     
     34 root      20   0       0      0      0 S   0.0   0.0   0:00.00 oom_reaper                                                                                                                                                     
     36 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-writeback                                                                                                                                            
     37 root      20   0       0      0      0 S   0.0   0.0   0:00.17 kcompactd0                                                                                                                                                     
     39 root      25   5       0      0      0 S   0.0   0.0   0:00.00 ksmd                                                                                                                                                           
     40 root      39  19       0      0      0 S   0.0   0.0   0:00.00 khugepaged                                                                                                                                                     
     41 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-kblockd                                                                                                                                              
     42 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-blkcg_punt_bio                                                                                                                                       
     43 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-kintegrityd                                                                                                                                          
     44 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 irq/9-acpi                                                                                                                                                     
     45 root      20   0       0      0      0 I   0.0   0.0   0:01.24 kworker/1:1-events                                                                                                                                             
     46 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-tpm_dev_wq                                                                                                                                           
     47 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-ata_sff                                                                                                                                              
     48 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-md_bitmap                                                                                                                                            
     49 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-md_llbitmap_io                                                                                                                                       
     50 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-md_llbitmap_unplug                                                                                                                                   
     51 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-edac-poller                                                                                                                                          
ubuntu@Ubuntu:~$ 
ubuntu@Ubuntu:~$ htop
ubuntu@Ubuntu:~$ uptime
 11:19:16 up 20 min,  1 user,  load average: 0.40, 0.23, 0.28
ubuntu@Ubuntu:~$ vmstat 1 5
procs -----------memory---------- ---swap-- -----io---- -system-- -------cpu-------
 r  b   swpd   free   buff  cache   si   so    bi    bo   in   cs us sy id wa st gu
 4  0      0 322000  25676 2065544    0    0  1163    40  305    2  1  3 96  0  0  0
 0  0      0 322000  25676 2065548    0    0     0     0 1026 1413  4  4 92  0  0  0
 0  0      0 322000  25676 2065548    0    0     0     0  828  674  2  3 95  0  0  0
 2  0      0 322000  25676 2065548    0    0     0     0  492  535  1  2 97  0  0  0
 1  0      0 322000  25676 20655
