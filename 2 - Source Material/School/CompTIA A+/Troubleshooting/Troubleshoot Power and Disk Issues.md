

Tags: [[troubleshooting]] [[IT]] [[school]] [[CompTIA_A+]] [[hardware]] [[CompTIA A+ Trouble Shooting Model]] 
Date: 2024-10-13 11:59

---

## Source: 
[CompTIA](https://learn.comptia.org/app/certmaster-learn-for-a-core-1-exams-220-1101#read/section/introduction-troubleshoot-power-and-disk-issues)

---

## Summary:


---

## Detailed Notes:
- **Steps to Troubleshoot Power Issues**
	- Check that other equipment in the area is working. There may be a fault in the power circuit or a wider complete failure of power. 
	- Try plugging another piece of known-good basic electrical equipment, such as a lamp, into the wall socket. If it does not work, the wall socket is faulty. Get an electrician to investigate the fault . 
	- Check that the PSU cabling is connected to the PC and the wall socket correctly and that all switches are in the "on" position.
	- Try another power cable. There may be a problem with the plug or fuse. Check that all the wire are connected to the correct terminals in the plug. check the fuse resistance with a multimeter or swap with a know good fuse. 
	- Try disconnecting extra devices, such as plug-in graphics card. If this solves the problem, either the PSU is underpowered and you need to fit one with a higher wattage rating, or one of the devices is faulty. 
	- If you can ensure a safe working environment, test the PSU using a multimeter or power supply tester.


- **Troubleshoot Post Issues**
	- **Ask what has changed**—If the system firmware has been updated and the PC has not booted since, the system firmware update may have failed. Use the reset procedure.

	- **Check cabling and connections, especially if maintenance work has just been performed on the PC**—An incorrectly oriented storage adapter cable or a badly seated adapter card can stop the POST from running. Correct any errors, reseat adapter cards, and then reboot the PC.

	- **Check for faulty interfaces and devices**—It is possible that a faulty adapter card or device is halting the POST. Try removing one device at a time to see if this solves the problem (or remove all non-essential devices, then add them back one by one).

	- **Check the PSU**—Even though the fans are receiving power, there may be a fault that is preventing the power good signal from being sent to the CPU, preventing POST.

	- **Check for a faulty CPU or system firmware**—If possible, replace the CPU chip with a known good one or update the system firmware.

![[Screenshot 2024-10-13 121946.png]]

---
## Definitions
- **Power Supply Unit(PSU)**
	- The power that is running the computer. 

- **Power-On-Self-Test(POST)**
	- Test routine build into PC firmware to confirm that system components are available at boot or to signal an error condition via a beep code or on-screen status message. 

---


