# solved-cs6210-project-1-vm-cpu-scheduler-and-memory-coordinator-fall2026
**TO GET THIS SOLUTION VISIT:** [[SOLVED] CS6210 # Project 1 : VM CPU scheduler and Memory Coordinator FALL2026](https://www.ankitcodinghub.com/product/cs6210-project-1-vm-cpu-scheduler-and-memory-coordinator-fall2026/)


---

📩 **If you need this solution or have special requests Email:** ankitcoding@gmail.com
📱 **WhatsApp:** +1 419 877 7882
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;169964&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;2&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (2 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS6210 # Project 1 : VM CPU scheduler and Memory Coordinator FALL2026&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

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
Please read through the entire page, before getting started. You may create a PRIVATE github repository on GT github to render this README.md.

Project Overview

In this project, you are going to implement a vCPU scheduler and a memory coordinator to dynamically manage the resources assigned to each guest machine. Each of these programs will be running in the host machine’s user space, collecting statistics for each guest machine through hypervisor calls and taking proper actions.

During one interval, the vCPU scheduler should track each guest machine’s vCpu utilization, and decide how to pin them to pCpus, so that all pCpus are “balanced”, where every pCpu handles similar amount of workload. The “pin changes” can incur overhead, but the vCPU scheduler should try its best to minimize it.

Similarly, during one interval, the memory coordinator should track each guest machine’s memory utilization, and decide how much extra free memory should be given to each guest machine. The memory coordinator should set the memory size of each guest machine and trigger the balloon driver to inflate and deflate. The memory coordinator should react properly when the memory resource is insufficient.

Tools that you will need:

qemu-kvm, libvirt-daemon-system, libvirt-dev are packages you need to install so that you can launch virtual machines with KVM and develop programs to manage virtual machines.

libvirt is a toolkit providing lots of APIs to interact with the virtualization capabilities of Linux.

Virtualization is a page you should check.

virsh, uvtool, virt-top, virt-clone, virt-manager, virt-install are tools that may help you play with virtual machines.

script command to make a typescript of your terminal session and generate a log file.

Environment Setup

Please use the cloud VM on Azure for your development. While you can develop locally on a Linux machine, it is much easier to set up and manage a cloud VM for this project. We strongly recommend that you use this method.

If you’re on Windows (WSL2) or macOS, please use the Azure cloud VM.

Refer to EnvironmentSetup.md (section: Setting Up Your Environment) for step-by-step instructions on how to configuring an Azure cloud VM.

The EnvironmentSetup.md file also provides instructions for creating VMs on a KVM hypervisor (section: Creating Test VMs).

Where can I find the APIs I might need to use?

libvirt-domain provides APIs to monitor and manage the guest virtual machines.

libvirt-host provides APIs to query the information regarding host machine.

Directory layout

This directory contains a boilerplate code, testing framework, and example applications for evaluating the functionality of your CPU Scheduler and Memory Coordinator.

The boiler plate code is provided in /cpu/src/ and /memory/src/ folders.

Details for testing the CPU Scheduler can be found in cpu/test/ folder and details for testing the Memory Coordinator can be found in the memory/test/ folder.

Project Flow

Refer to the flowchart below to help understand the overall project concept. We are taking the CPU scheduler as an example here.

&nbsp;

vCPU Scheduler

Tasks

Complete the function CPUScheduler() in vcpu_scheduler.c.

If you are adding extra files, make sure to modify the Makefile accordingly.

Compile the code using the command make all.

You can run the code by ./vcpu_scheduler &lt;interval&gt;. For example, ./vcpu_scheduler 2 will run the scheduler with an interval of 2 seconds.

While submitting, write your algorithm and logic in the readme cpu/src/Readme.md.

Step-by-Step Guide

Connect to the Hypervisor:

Use the virConnect* functions in libvirt-host to establish a connection.

For this project, connect to the local hypervisor at qemu:///system.

List Active Virtual Machines:

Retrieve all actively running virtual machines within qemu:///system using the virConnectList* functions.

Collect vCPU Statistics:

Use the virDomainGet* functions from libvirt-domain to gather vCPU statistics.

If host pCPU (physical CPU) information is also required, use the relevant APIs in libvirt-host.

Handle vCPU Time Data:

vCPU time is typically provided in nanoseconds, not as a percentage.

Transform this data into a usable format or incorporate it directly into your calculations.

Determine vCPU to pCPU Mapping:

Use the virDomainGet* functions to identify the current mapping (affinity) between vCPUs and pCPUs.

Develop Your Algorithm:

Based on the collected statistics, design an algorithm to find the “best” pCPU for each vCPU.

Optimize for efficient CPU usage while ensuring no pCPU is over- or under-utilized.

Update vCPU-Pinning:

Use the virDomainPinVcpu function to dynamically assign each vCPU to its optimal pCPU.

Create a Periodic Scheduler:

Start with a “one-time scheduler” to establish a baseline.

Revise it to run periodically for ongoing optimization.

Test Your Scheduler:

Launch several virtual machines and simulate workloads to consume CPU resources.

Evaluate the scheduler’s performance by observing how well it balances and stabilizes CPU usage across pCPUs.

Key Considerations

Algorithm Requirements

The algorithm must be independent of the number of vCPUs and pCPUs.

It should handle all configurations, including:

#vCPUs &gt; #pCPUs: More virtual CPUs than physical CPUs.

#vCPUs = #pCPUs: Equal number of virtual and physical CPUs.

A generic approach that focuses on stabilizing processor usage is sufficient and will naturally handle these cases without requiring specific logic for each scenario.

The expectation of the test cases provided operate under the assumption of 8 vCPU and 4 pCPUs. But they can be extended to a different count of pCPUs. For example, for an 8 core system (8 pCPUs), you should be able to evaluate your algorithm for a setup of 16 VMs (16 vCPU) with similar expectation.

&nbsp;

What Constitutes a Balanced Schedule?

A balanced schedule ensures that no pCPU is underutilized or overutilized.

The standard deviation of CPU utilizations is a suitable metric for assessing balance:

For a balanced schedule, the absolute value of the standard deviation should be ≤ 5.

&nbsp;

What Constitutes a Stable Schedule?

A stable schedule minimizes unnecessary changes to vCPU-pCPU assignments once a balanced schedule is achieved.

Frequent reassignments should be avoided unless required to maintain balance.

Memory Coordinator

Tasks

Complete the function MemoryScheduler() in memory_coordinator.c.

If you are adding extra files, make sure to modify Makefile accordingly.

Compile the code using the command make all.

You can run the code by ./memory_coordinator &lt;interval&gt;. For example, ./memory_coordinator 2 will run the coordinator with an interval of 2 seconds.

While submitting, write your algorithm and logic in the readme memory/src/Readme.md.

Step-by-Step Guide

Connect to the Hypervisor:

Use the virConnect* functions in libvirt-host to establish a connection.

For this project, connect to the local hypervisor at qemu:///system.

List Active Virtual Machines:

Retrieve all active virtual machines within qemu:///system using the virConnectList* functions.

Enable Memory Statistics Collection:

Use the virDomainSetMemoryStatsPeriod function to configure memory statistics collection.

Retrieve Memory Statistics:

Decide which memory statistics are relevant for your use case.

Use the virDomainGet* and virDomainMemory* functions to fetch the required data.

Fetch Host Memory Information:

Use the virNodeGet* functions in libvirt-host to gather host memory details.

Design Your Algorithm:

Develop a policy to allocate extra free memory to each virtual machine based on the collected statistics.

Decide how much memory should be reserved and how much can be dynamically allocated.

Update Memory Allocation:

Use the virDomainSetMemory function to dynamically adjust the memory for each virtual machine. This triggers the balloon driver.

Create a Periodic Memory Scheduler:

Start with a “one-time scheduler” and revise it to run periodically for continuous optimization.

Test the Memory Coordinator:

Launch several virtual machines and simulate memory usage by running test workloads.

Gradually consume memory resources and evaluate the performance of your memory scheduler.

&nbsp;

Key Considerations

Algorithm Requirements

Ensure that both the VMs and the host retain sufficient memory after releasing any memory.

Release memory gradually:

For example, if a VM has 300 MB of memory, do not release 200 MB in a single step.

While there’s no magic number here (like 50 MB or 100 MB), your graph should look like the ones we’ve provided as sample solutions.

Maintain a minimum of 100 MB of unused memory in each VM so that the guest OS does not crash.

The host should not release memory if it has less than or equal to 200 MB of unused memory.

Recording Test Results with script

To validate your scheduler or coordinator, use the script command to record terminal sessions and store the results in a log file. This process ensures a detailed record of test outcomes. Follow these steps:

Steps to Record Test Results

Start Recording:

Run the script command to start recording terminal output: bash script vcpu_scheduler1.log or bash script memory_coordinator1.log

Run the Monitor:

Execute the monitor test using the monitor.py script: bash python3 monitor.py -t runtest1.py Replace runtest1.py with the appropriate test case. Run 3 test cases each for CPU and memory.

Run Your Scheduler or Coordinator:

Launch your program on a separate terminal to perform scheduling or memory coordination.

Stop Recording:

Exit the script command by typing: bash exit

Verify that the log file has been generated and contains the expected results.

Repeat for All Test Cases:

Ensure you generate separate log files for each test case.

For accurate results, reboot your VMs before running each test.

&nbsp;

Additional Information

The log file will be saved in the current working directory upon exiting the script command.

For more details about script, refer to its manual by running: bash man script

Testing Process

Testing the CPU Scheduler:

Follow the instructions provided in ./cpu/test/HowToDoTest.md.

There are 3 test cases for the CPU scheduler. Detailed scenarios and expected outcomes for each test case are available in ./cpu/test/HowToDoTest.md.

Testing the Memory Coordinator:

Follow the instructions provided in ./memory/test/HowToDoTest.md.

There are 3 test cases for the memory coordinator. Detailed scenarios and expected outcomes for each test case are available in ./memory/test/HowToDoTest.md.

Note: In the autograder environment:

Up to 4 VMs will be used for memory coordinator tests.

Up to 8 VMs will be used for vCPU scheduler tests.

Each VM will be configured with 1 vCPU.

Project Interview

Project 1 includes a short oral interview after submission. The purpose of the interview is to verify that you understand the resource-management policies and code you submitted. The interview is not a second autograder and is not intended to test memorization. You should be prepared to open your submitted code and explain your design, important implementation decisions, correctness and safety reasoning, and how your testing supports your implementation.

The interview itself will take about 15 minutes and will be scheduled in a 20-minute appointment slot.

You are responsible for signing up for an interview slot by the announced deadline. If none of the available slots work for you, contact the head TAs as early as possible.

Missing the interview without a valid documented reason will result in a zero for the project.

Arriving more than 5 minutes late may result in a 25% deduction from the project grade.

AI tools may be used according to the course AI policy, including any required disclosure/log submission. Regardless of tool use, you are responsible for understanding all code you submit.

How the Interview Affects Your Project Grade

The autograder and existing project grading components determine your base project score. The oral interview determines a multiplier between 0 and 1, which is applied to the entire base project score:

Final Project Score = Base Project Score × Oral Interview Multiplier

A student who demonstrates strong understanding of the submitted implementation should receive a multiplier close to 1. Working code by itself does not guarantee a high interview multiplier if the student cannot explain the submitted design or correctness reasoning.

Interview Rubric

The interview will cover the following four areas. The weights below are the relative weights within the oral interview multiplier.

Category

Weight

What you should be prepared to explain

A. Controller and Code Ownership

20%

The high-level control flow of both CPUScheduler() and MemoryScheduler(), where important logic lives in your submitted code, and how your README corresponds to the implementation.

B. vCPU Scheduling Policy

35%

How you measure vCPU utilization, evaluate pCPU balance, choose or preserve vCPU-to-pCPU mappings, avoid unnecessary pin changes, and handle different numbers of vCPUs/pCPUs.

C. Memory Coordination Policy

35%

How you obtain and interpret memory statistics, decide when VMs should receive or release memory, adjust memory gradually, and protect both guest VMs and the host from unsafe memory pressure.

D. Robustness and Evidence of Testing

10%

How your implementation handles relevant edge cases and how your submitted README, logs, Gradescope output, or graphs support the behavior you expect.

In general, strong understanding means that you can explain the relevant logic independently and connect your explanation directly to your submitted code. Partial understanding means that you understand the main idea but need prompting or are unclear on important implementation details. Weak understanding means that you cannot explain or locate important parts of your submitted implementation, or your explanation conflicts with the code you submitted.

Example Question Styles

The questions below are illustrative examples only. They are intended to show the level and style of the interview; the actual questions and follow-up questions may differ and may be adapted to your implementation.

“Open one of your scheduler functions and walk us through how it decides what action to take during one interval.”

“How does your vCPU scheduler decide whether the current mapping is balanced or stable, and when should it change a pinning decision?”

“How does your memory coordinator decide when to give memory to or reclaim memory from a VM while keeping the guest and host safe?”

“Choose one edge case or test result from your submission and explain what behavior you expected and why.”

You do not need to memorize a script for the interview. The best preparation is to review your own submitted code and README and make sure you understand the decisions you made and why your implementation satisfies the project requirements.

&nbsp;

Grading

The existing autograder and manual project-grading components below determine the base project score. As described in the Project Interview section, the final project score is the base project score multiplied by the oral interview multiplier.

This is not a performance-oriented project; we will test the functionality only. Please refer to the sample output pdfs (CPU run, annotated and full autograder run with memory graphs) to understand the expected behavior from the scheduler and coordinator across test cases on the autograder. More details can be found in the test directories described in the testing section.

The functional part is auto-graded on Gradescope:

vCPU scheduler – 8 points (auto-graded)

The scheduler should aim to make the pCPUs enter a stable and a balanced state.

1 point for compiling.

7 test cases worth 1 point each: 0.5 for a balanced schedule and 0.5 for a stable schedule.

1 additional point for the Readme, graded manually after the autograder runs.

Memory coordinator – 8 points (auto-graded)

The VMs should consume or release memory appropriately for each test case.

1 point for compiling.

4 test cases worth 1.75 points each: 0.875 for taking memory gradually and 0.875 for releasing it gradually.

0.25 points are deducted for a test case in which no VM ever gets close to the 2 GB limit (within a ~100 MB margin).

Don’t kill the guest operating system (do not take all the memory resource from guests) — a test case where a guest is drained to death scores 0.

Don’t freeze the host (do not give all available memory resources to guests).

1 additional point for the Readme, graded manually after the autograder runs.

Deliverables &amp; Submission

You need to implement two separate C programs, one for vCPU scheduler (/cpu/src/vcpu_scheduler.c) and another for memory coordinator(/memory/src/memory_coordinator.c). Both programs should accept one input parameter, the time interval (in seconds) your scheduler or coordinator will trigger. For example, if we want the vCPU scheduler to take action every 2 seconds, we will start your program by doing ./vcpu_scheduler 2. Note that the boiler plate code is provided in the attached zip file.

You need to submit one zipped file named FirstName_LastName_p1.zip (e.g. George_Burdell_p1.zip) containing a subfolder named FirstName_LastName_p1 and two separate subfolders(cpu and memory) within the FirstName_LastName_p1 subfolder, each containing a Makefile, Readme.md (containing code description and algorithm), source code and the log files generated through script command for each test case. Use the script collect_submission.py to generate the zip file.

Please note that while you’re required to submit the log files, we will be grading based on the Gradescope output. So, please ensure that your program runs correctly on Gradescope and produces reasonable graphs.

We will compile your program by just doing make. Therefore, your final submission should be structured as follows after being unzipped. Don’t change the name of the files. Please adhere to the submission instructions, not doing so will result in a penalty of points.

– FirstName_LastName_p1/

– cpu/

– vcpu_scheduler.c

– Makefile

– Readme.md (Code Description and algorithm)

– 3 vcpu_scheduler.log files — vcpu_scheduler1.log and so on for each test case

– memory/

–&nbsp; memory_coordinator.c

–&nbsp; Makefile

–&nbsp; Readme.md (Code Description and algorithm)

–&nbsp; 3 memory_coordinator.log files — memory_coordinator1.log and so on for each test case

To generate the final zip file, ensure that all the required files are present and run the following command:

python3 collect_submission.py

Once you’ve successfully created a zip folder as per instructions, you must upload that zip folder on Gradescope. Keep in mind that each submission will take around 40 minutes to autograde during off-peak hours, so be advised to submit early!

In the interest of being fair to all students, please refrain from using the gradescope environment as your developing environment as this will affect your fellow students’ ability to submit. To this end, there is a modest limit of 20 submissions per user (enforced manually by the teaching team after the deadline).
