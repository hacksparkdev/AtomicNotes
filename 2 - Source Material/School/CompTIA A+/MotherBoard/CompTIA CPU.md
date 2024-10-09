Tags: [[cpu]] [[CompTIA_A+]] [[motherboard]] [[school]] [[IT]] [[hardware]] [[Cyber Security]] 
Date: 2024-10-06 22:47

---

## Source: 
[WGU](https://learn.comptia.org/app/certmaster-learn-for-a-core-1-exams-220-1101#read/study_task/1323551/cpu-features-1)

---

## Summary:
The CPU or Central processing unit executes program instruction code. When software runs it is stored in the ram. From the ram it is loaded into the control unit it is either executed or sent to the (ALU) Arithmetic Logic Unit. The result is either sent to the register, cache, or back to the memory. 

---

## Detailed Notes:

- **Key Concept 1: Register**
	 - A register is a temporary storage area available to the different units within the CPU working at the same clock speed as the CPU. 
   
- **Key Concept 2: Cache**
	- The Cache is a small block of  memory that works at the speed of the CPU or close to it, depending on the cache level. Cache enhances performance by storing instructions and data that the CPU is using regularly. 
- **Key Concept 3: CPU Architecture**
	- **CISC (Complex Instruction Set Computing)**
		-  CISC CPUs are designed with a large set of complex instructions, where each instruction can execute multiple low-level operations. (e.g., load, store, arithmetic).
		- Intel x86 architecture (used in most desktops and laptops).
		- AMD processors also use a CISC architecture base on x86
		- **Features**
			- **Complex instruction set:** Instructions can perform more tasks per instruction, reducing the number of instructions a program needs. 
			- **Variable instruction length:** Instructions can vary in size, leading to more flexibility but also more complexity in decoding. 
			- **More memory operations:** CISC processors can perform operations directly on memory, without needing to load data into registers first. 

	-  **RISC (Reduced Instruction Set Computing)**
		- RISC CPUs are designed with a simpler, smaller set of instructions. These instructions are executed very quickly, typically in a single clock cycle. 
		- **Features**
			- **Simple instruction set:** The CPU can execute simple instructions quickly and efficiently, leading to faster performance for certain tasks. 
			- **Fixed instruction length** Instructions are usually of a uniform size, making decoding simpler and faster. 
			- **Load/store architecture:** Memory operations are limited to specific instructions(load and store), with most other operations done using registers. 
  
- **Key Concept 4: Enhancing CPU Performance**
- Performance of the CPU is based on the speed at which it can execute instructions, there are a few ways we can make the performance of the CPU faster. 
	- **Multithreading**
		- Improving the instruction pipeline is one way to improve the performance. Multithreading creates more than one thread for the CPU to run instructions on. This reduces the time for CPU to wait for instructions to be executed. 
	- **Symmetric Processing**
		- Using more than one processor can be a costly way to improve performance. The motherboard would hold two processors that would be used when one processor is working. 
	- **Multicore**
		- Older processor would have a single core. Multicore has 8 or more processors. These are also multi threaded. 
- **Key Concept 5: CPU Socket Types**
	- Socket types are different based on the manufacturer. AMD & Intel have different socket types. 
	- **AMD** 
		- AMD uses pin grid array(PGA) The PGA form factor positions the pin on the underside of the processor package. 
	- **Intel**
		- Intel uses land grid array (LGA) socket form factor CPUs. The LGA form factor position the pins that connect the CPU to the Socket. 
---

---
## Definitions

- **Multithreading**
	-  CPU architecture that exposes two or more logical processors to the OS, delivering performance benefits similar to multicore and multisocket to threaded applications. 

---
