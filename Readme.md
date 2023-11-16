## How to make USRP-based OpenBTS boards - URAN-1 / SRAD-1 work?

### get OpenBTS ISO

(Apply modified-USRP1 with 52Mhz、URAN-1 and SRAD-1)

-   [USRP1-52M-Clock-BTS.iso](https://rfagora.s3.amazonaws.com/image/en.iplinkme.iso)
    -  the ISO Autostarted OpenBTS 4.0 inside.
-   [OpenBTS 4.0 manual](https://drive.google.com/open?id=1wqb00XMShJUPrKVSh-3gWSepQO52eSeS)
-   [USRP1_52M_CLOCK_BTS Manual](https://drive.google.com/file/d/0B3ss_wNog58SSTB5VWRlUTBaMlE/view?usp=sharing)

### Some Testing Commands
(the root user)

-   Testing whether the system is connected

```
usrp_probe
```
-   Testing usrp1 of usb data transfer rate

``` 
/usr/local/share/gnuradio/examples/usrp/usrp_benchmark_usb.py
```
-   View sub-board and the motherboard is connected

``` 
lsusrp
```
-   Reprogram the USRP1 motherboard eeprom

``` 
/usr/local/src/gnuradio-3.4.2/usrp/firmware/src/usrp2/burn-usrp4-eeprom 
```
-   Benchmark emission command signal

``` 
/usr/local/share/gnuradio/examples/digital/benchmark_tx.py -f 900M -T A
```
-   Usrp_fft received signal command

```
usrp_fft.py -f 900M -R A
```