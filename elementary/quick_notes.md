# The Rig

I tried eOS on three machines, two laptops and one desktop.

Laptop #1:

```
$ neofetch
         eeeeeeeeeeeeeeeee            kevin@eos 
      eeeeeeeeeeeeeeeeeeeeeee         --------- 
    eeeee  eeeeeeeeeeee   eeeee       OS: elementary OS 5.0 Juno x86_64 
  eeee   eeeee       eee     eeee     Host: Precision 7710 
 eeee   eeee          eee     eeee    Kernel: 4.20.3-042003-generic 
eee    eee            eee       eee   Uptime: 6 hours, 17 mins 
eee   eee            eee        eee   Packages: 2106 
ee    eee           eeee       eeee   Shell: zsh 5.4.2 
ee    eee         eeeee      eeeeee   Resolution: 1920x1080, 1680x1050, 1680x1050 
ee    eee       eeeee      eeeee ee   DE: Pantheon 
eee   eeee   eeeeee      eeeee  eee   WM: Mutter(Gala) 
eee    eeeeeeeeee     eeeeee    eee   Terminal: tilix 
 eeeeeeeeeeeeeeeeeeeeeeee    eeeee    CPU: Intel i7-6820HQ (8) @ 3.600GHz 
  eeeeeeee eeeeeeeeeeee      eeee     GPU: AMD Radeon HD 8890M 
    eeeee                 eeeee       Memory: 14137MiB / 64354MiB 
      eeeeeee         eeeeeee 
         eeeeeeeeeeeeeeeee                                    
```

Laptop #2:

```
$ neofetch
         eeeeeeeeeeeeeeeee            kevin@chickenlegs 
      eeeeeeeeeeeeeeeeeeeeeee         ----------------- 
    eeeee  eeeeeeeeeeee   eeeee       OS: elementary OS 5.0 Juno x86_64 
  eeee   eeeee       eee     eeee     Host: HP Spectre x360 Convertible 13-ac0XX 
 eeee   eeee          eee     eeee    Kernel: 4.20.3-042003-generic 
eee    eee            eee       eee   Uptime: 10 days, 4 hours, 19 mins 
eee   eee            eee        eee   Packages: 2042 
ee    eee           eeee       eeee   Shell: zsh 5.4.2 
ee    eee         eeeee      eeeeee   Resolution: 1920x1080 
ee    eee       eeeee      eeeee ee   DE: Pantheon 
eee   eeee   eeeeee      eeeee  eee   WM: Mutter(Gala) 
eee    eeeeeeeeee     eeeeee    eee   Theme: Elementary [GTK3] 
 eeeeeeeeeeeeeeeeeeeeeeee    eeeee    Icons: Elementary [GTK3] 
  eeeeeeee eeeeeeeeeeee      eeee     Terminal: tilix 
    eeeee                 eeeee       CPU: Intel i7-7500U (4) @ 3.500GHz 
      eeeeeee         eeeeeee         GPU: Intel HD Graphics 620 
         eeeeeeeeeeeeeeeee            Memory: 4352MiB / 15919MiB 
```

The desktop I forgot to run `neofetch` before installing another distro. But it was:

```
OS: elementary OS 5.0 Juno x86_64 
Kernel: 4.20.3-042003-generic 
Shell: zsh 5.4.2 
Resolution: 1920x1080, 1920x1080 (vertical)
DE: Pantheon 
WM: Mutter(Gala) 
Terminal: tilix 
CPU: AMD Ryzen 2950x 16-core
GPU: AMD Vega64 8GB
Memory: 3254MiB 
```

**NOTE:** More recent kernel than `4.15` is required for `$REASONS`

# Positives

* Easily most consistent look and feel by default from a Linux Desktop, I really do love the look and little touches these people have put into it!
* Probably the best GUI based system update from an App Center
* Bar none their developer documentation is the best out there, I wish more distros cared this much about this
* So many little touches in the UI and consistency really shine.

# Negatives

* [VMWare took a good bit of work](https://elementaryos.stackexchange.com/a/18003/17127) to make (which is required for my job) 
* Resume from suspend requires power button (Dell Precisions 7710) and gives "neon checkerboard", also network connectivity drops (which means all VPNs drop, etc.)
* Not a fan of single click to open dirs/files
* Not a fan of no minimize (can be added with `elementary-tweaks`)
* Files application has micro freezes from time to time (gets hung?)
* Login screen also freezes from time to time
* Vertical screen orientation isn't repsected at login screen
* Apps open "between" multi-monitor setups. I.e. as if the entire workspace area is one giant monitor
* Files drag/drop is touchy and doesn't always work. Sometimes files just can't be dragged
* AppCenter crashes from time to time
* Package version get out of date quickly (Ubuntu 18.04 base, duh)
* Not a fan of some of the in house apps (mail, epiphany, code).
* Although I didn't copy the link, there were spots I felt like eOS took credit for things in upstream Ubuntu which felt disingenous to me. I'm sure it's not intentional, but as someone who knows the behind the scenes about the tech it felt strange.
* I'm not a fan of the "privacy and security" marketing speak. Telemetry isn't bad when done right, and it helps projects move forward in meaningful ways. I don't think saying just because it's linux it's secure is either accurate, or honest. It feels like marketing speak to capture on the hype.

# Neutral

* AppCenter is meh for me. I like the look, but still feels like an uncurrated mess to me (even though I know it's not). It's hard to tell what software does without digging into the actual page.
  * I would like some reviews/ratings (which I know is super hard to get right), but just *something* to tell me more about the software. Maybe more screenshots?
* Shows `*` for terminal passwords. I'm not a fan, but also don't believe it hurts much
* It's an ubuntu base but you can't add PPAs by default. I get *why* they did this...but it's an extra hoop I have to go through just to get the software I need.
* Being Ubuntu based, pretty much everything that works about Ubuntu works here, and also vice versa
* I'm not sure how I feel about how closely it resembles macOS in small ways (command icon in places, Files look so similar, settings app). Is it bad? No. I just think with as talented as the eOS devs are, they could stand on their own without having to stick to Apple's design. Maybe this is due to wanting to be familiar to those using macs?

# General Thoughts

I wrote longer prose about the points above, and my general feelings about eOS. However, it's difficult to give criticism (even constructive) publicly online without coming across as overly negative. Hence, these thoughts are in a private repository. If you are intereseted, you can message me to read them.

The TL;DR is eOS is gorgeous. I wish other distros put this much effort into consistency. However, I disagree with some of the fundamental decisiosn of the eOS team and can't really see myself using this distro long term which is a shame...because I *really* want a distro that looks as good as eOS just without the heavy handedness.
