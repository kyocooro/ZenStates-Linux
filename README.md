# ZenStates-Linux
  Collection of utilities for Ryzen processors and motherboards

## zenstates.py
  Dynamically edit AMD Ryzen processor parameters.
  Current version supports Zen2-based CPUs only.

  Requires root access and the msr kernel module loaded (just run "modprobe msr" as root).
  ```console
  $ sudo modprobe msr
  ```

  The utility is based on [r4m0n's ZenStates-Linux](https://github.com/r4m0n/ZenStates-Linux).

  GUI is based on [PySimpleGUI](https://pypi.org/project/PySimpleGUI/).

  CPUID module used: [flababah's cpuid.py](https://github.com/flababah/cpuid.py).

## CLI
```console
$ sudo ./zenstates.py --no-gui [args...]
```

    usage: zenstates.py [-h] [--no-gui] [-l] [-p {0,1,2,3,4,5,6,7}] [--enable] [--disable] [-f FID] [-d DID] [-v VID] 
    [--smu-test-message]

    Sets parameters of Ryzen processors

    required arguments:
      --no-gui              Run in CLI without GUI

    optional arguments:
      -h, --help            Show this help message and exit
      -l, --list            List all P-States
      -p {0,1,2,3,4,5,6,7}, --pstate {0,1,2,3,4,5,6,7}
                            P-State to set
      --enable              Enable P-State
      --disable             Disable P-State
      -f FID, --fid FID     FID to set (in hex)
      -d DID, --did DID     DID to set (in hex)
      -v VID, --vid VID     VID to set (in hex)
      --c6-enable           Enable C-State C6
      --c6-disable          Disable C-State C6
      --smu-test-message    Send test message to the SMU (response 1 means 'success')
      --lock-freq           Lock frequency for better perf
      --oc-frequency        Set Overclock frequency (in MHz)
      --oc-vid              Set Overclock VID (in hex)
      --ppt                 Set PPT limit (in W)
      --tdc                 Set TDC limit (in A)
      --edc                 Set EDC limit (in A)

## GUI
  ![Screenshot](ZenStates%20for%20Linux%20v1.0_006.png?raw=true "ZenStates for Linux screenshot")
  
  To run the GUI, additional packages are needed:
  ```console
  $ sudo apt install pip3 python3-tk wheel
  $ pip3 install pysimplegui
  ```

  Then run:
  ```console
  $ sudo python3 zenstates.py
  ```

## togglecode.py
  Turns on/off the Q-Code display on ASUS Crosshair VI Hero motherboards (and other boards with a compatible Super I/O chip)

  Requires root access and the portio python module.
  To install run:
  ```console
  $ pip install wheel portio
  ```
