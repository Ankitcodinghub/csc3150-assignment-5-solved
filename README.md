# csc3150-assignment-5-solved
**TO GET THIS SOLUTION VISIT:** [CSC3150 Assignment 5 Solved](https://www.ankitcodinghub.com/product/csc3150-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;117538&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;2&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (2 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CSC3150 Assignment 5 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (2 votes)    </div>
    </div>
In Assignment 5, you are required to make a prime device in Linux, and implement file operations in kernel module to control this device.

Outline:

• We will make a device under /dev by mknod command.

• This device can find n-th prime number.

• You will implement file operations in a kernel module to control this device.

• And implement ioctl function to change the device configuration. • Simulate registers on device by allocating a memory region.

Global View:

Specification:

• Register character device and make it live:

 You can use alloc_chrdev_region() to allocate a range of char device numbers. And get available number by MAJOR() and MINOR() macro.

 In your kernel module, you could allocate a cdev structure by cdev_alloc() and initialize it by cdev_init() to bind cdev file_operations.

 Add a device by cdev_add() to make it live.

• Test program and printk:

 Before write module, we need to know what this module do. So we provide a test program to test this device.

 You can modify test program and test your module.

 We will check with our test cases.

 In kernel module, you need to write printk to help debug and use dmesg command to show message.

 To help demo program, your printk must be started with “OS_AS5: function_name: message”.

• File operations:

 You should write a struct file_operations to map the operations to functions in this module.

 And use cdev_init() at module init to bind cdev and file_ operations.

• ioctl:

 In Linux, device provide user mode program ioctl function to change the device configuration.

 ioctl define many types of operation with switch case to do coordinated work.

 And ioctl use mask to get value from these operation label.

 Here we provide “ioc_hw5.h” to define 6 works.

1) (HW5_IOC_SETSTUID) Set student ID: printk your student ID

2) (HW5_IOCSETRWOK) Set if RW OK: printk OK if you complete R/W function

3) (HW5_IOCSETIOCOK) Set if ioctl OK: printk OK if you complete ioctl function

4) (HW5_IOCSETIRQOK) Set if IRQ OK: printk OK if you complete bonus

5) (HW5_IOCSETBLOCK) Set blocking or non-blocking: set write function mode

6) (HW5_IOCWAITREADABLE) Wait if readable now (synchronize function): used before read to confirm it can read answer now when use non-blocking write mode.

 ioctl lables defined in “ioc_hw5.h”

“_IOW(type, nr, size )” is used for an ioctl to write data to the driver. It is to generate command numbers.

 Demo for ioctl call in user mode: ioctl(fd,

HW5_IOCSETBLOCK, &amp;ret)

 fd: an open file descriptor

 HW5_IOCSETBLOCK: device-dependent request code.

 &amp;ret: an untyped pointer to memory

• write:

 Define a data struct that is passed in write function.

 a is operator: ‘+’, ‘-‘, ‘*’, ‘/’, or ‘p’ (‘p’ means find prime number)

 b is operand 1

 c is operand 2

 Use INIT_WORK() and schedule_work() to queue work to system queue.

• Find Prime operation:

 It finds c-th prime number bigger than b.

(e.g, “1 p 3” means to find 3rd prime number which is bigger than 1, then it should be 5.)

 And you will feel the I/O latency when execute test program for “100 p 10000” and “100 p 20000”.

 We will check your blocking and non-blocking IO by observing the delay of the message printed by test program.

 R/W function packaged in arithmetic function in user mode program. arithmetic(fd, ‘p’, 100, 10000);

 fd: an open file descriptor

 p: operator

 100: operand1 10000: operand2

• Work Routine:

 The work you enqueued should be written in a work routine function in module.

 These work will be processed by another kernel thread. computation is written in a work routine in module

• Blocking and Non-Blocking IO:

 The test program can use ioctl to set blocking or non-blocking. Your write function in module can be blocking or non-blocking.

 Blocking write need to wait computation completed.

 Non-blocking write just return after queuing work.

 Read function only has blocking, because not queuing work.

• Blocking Write:

 In test program, we just need a write function.

 Do not need another synchronize function.

 But block when writing.

 Blocking write in test program:

• Non- Blocking Write:

 In test program, we can do something after write function.

 Write function return after queueing work, it is non-blocking.

 But need another synchronize function to wait work completed.

 Non-blocking write in test program:

• Interrupt driven IO:

 When implementing blocking write and synchronize function, they use a while loop busy waiting the interrupt.

 You can use a variable to simulate the interrupt.

 At the final of the work routine function, change this variable as triggering the interrupt.

 And then, blocking write and synchronize function can exit the while loop.

• DMA Buffer:

 To simulate register and memory on device, you need to kmalloc a dma buffer.

 This buffer is as I/O port mapping in main memory.

 What device do is written in work routine function. This function get data from this buffer.

 Defined value written into dma buffer:

• In and out functions:

 You need to implement in &amp; out function to access dma buffer just like physical device.

 out function is used to output data to dma buffer.

 in function is used to input data from dma buffer.

 The 6 in &amp; out functions are definded in module to operate dma_buf:

(‘c’, ‘s’ and ‘i’ maps with data type ‘char’, ‘short’ and ‘int’)

 Demo usage of in and out functions: myouti(value,

DMAIOCOKADDR)

 value: data you want to write into dma_buffer

 DMAIOCOKADDR: port in dma_buffer

• Data transfer between kernel and user space:

 get_user(x, ptr)

 Get a simple variable from user space.

 x: Variable to store result.

 ptr: Source address, in user space.

 put_user(x, ptr)

 Write a simple value into user space.

 x: Value to copy to user space.

 ptr: Destination address, in user space.

Template structure:

• Makefile is provided:

 Command: make

(It will firstly build your main.c as kernel module “mydev.ko”, insert “mydev.ko”, and then build “test.c” as executable file “test”.)

 Command: make clean

(It will remove “mydev.ko” and use “dmesg” to list kernel logs that includes keyword “OS_AS5”)

• “mknod” script is provided:

 Script

 In mknod command: c means character device. Followed two number are Major and Minor number to specify device.

 You can get available number by MAJOR() and MINOR()

macro after alloc_chrdev_region() in module_init() function.

 Demo of how to use mknod script: (Refer to Tutorial_11 Slide 3 to 6)

• Steps you need to run the template:

 Run “make”

 Run “dmesg” to check available device number

 Run “sudo ./mkdev.sh MAJOR MINOR” to build file node (MAJOR and

MINOR are the available device number checked from previous step)

 Run “./test” to start testing

 Run “make clean” to remove the module and check the messages Run “sudo ./rmdev.sh” to remove the file node You will get output:

• You should complete module init and exit functions:

• Implement read/write/ioctl operations and arithmetic routine:

Function Requirements (90 points):

• Register a character device when module initialized. (5 points)

• Initialized a cdev and add it to make it alive. (5 points)

• Allocate DMA buffer. (5 points)

• Allocate work routine. (5 points)

• Implement read operation for your device. (10 points)

• Implement write operation for your device. (20 points)

• Implement ioctl setting for your device. (15 points)

• Implement arithmetic routine for your device. (10 points)

• Complete module exit functions. (5 points)

• Update your student ID in test case and make it be print in kernel ioctl. (5 points)

• Run test cases to check write and read operations. (5 points)

Demo Output:

• Test case: (: ‘+’, ‘-‘, ‘*’, ‘/’ is for your testing, we will mainly test ‘p’ operation)

• User mode output:

• Kernel mode output:

• Steps for internal executions:

 find major and minor number

 allocate DMA buffer

 ioctl print set and get value

 write to queue work

 arithmetic routine to compute answer

 read to get answer

 free DMA buffer

 unregister device

Bonus (10 points)

• Global View (Bonus)

• Count the interrupt times of input device like keyboard.

• Hint: watch -n 1 cat /proc/interrupts

• Use request_irq() in module_init to add an ISR into an IRQ number’s action list.

• And free_irq() when module_ exit, otherwise kernel panic.

• Please define IRQ_NUM at head of code.

• Demo output:

Report (10 points)

Write a report (PDF) for your assignment, which should include main information as below:

• How did you design your program?

• What problems you met in this assignment and what is your solution?

• The steps to execute your program.

• Screenshot of your program output.

• What did you learn from this assignment?

Submission

• Please submit the file as package with directory structure as below:

◼ CSC3150_Assignment_5_Student ID

– Source

o main.c (if you complete bonus, submit only one “main.c”) o test.c o ioc_hw5.h o makefile o mkdev.sh o rmdev.sh

– Report(PDF)

Grading rules

Report 10 points

Bonus 10 points

Completed with good quality 80 ~ 90

Completed accurately 80 +

Fully Submitted (compile successfully) 60 +

Partial submitted 0 ~ 60

No submission 0
