# cmpsc311---introduction-to-systems-assignment-3---mdadm-linear-device-writes-and-testing-solved
**TO GET THIS SOLUTION VISIT:** [CMPSC311 – Introduction to Systems Assignment #3 – mdadm Linear Device (Writes and Testing) Solved](https://www.ankitcodinghub.com/product/cmpsc311-introduction-to-systems-assignment-3-mdadm-linear-device-writes-and-testing-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;72438&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;1&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (1 vote)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CMPSC311 - Introduction to Systems Assignment #3 – mdadm Linear Device (Writes and Testing) Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

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
            5/5 - (1 vote)    </div>
    </div>
Your internship is going great. You have gained experience with C programming, you have experienced your first segmentation faults, and you’ve come out on top. You are brimming with confidence and ready to handle your next challenge.

<h1>Implementing <strong>mdadm_write</strong></h1>
Your next job is to implement write functionality for mdadm and then thoroughly test your implementation. Specifically, you will implement the following function:

int mdadm_write(uint32_t addr, uint32_t len, const uint8_t *buf)

As you can tell, it has an interface that is similar to that of the mdadm_read function, which you have already implemented. Specifically, it writes len bytes from the user-supplied buf buffer to your storage system, starting at address addr. You may notice that the buf parameter now has a const specifier. We put the const there to emphasize that it is an <em>in </em>parameter; that is, mdadm_write should only read from this parameter and not modify it. It is a good practice to specify const specifier for your in parameters that are arrays or structs.

Similar to mdadm_read, writing to an out-of-bound linear address should fail. A read larger than 1,024 bytes should fail; in other words, len can be 1,024 at most. There are a few more restrictions that you will find out as you try to pass the tests.

Once you implement the above function, you have the basic functionality of your storage system in place. We have expanded the tester to include new tests for the write operations, in addition to existing read operations. You should try to pass these write tests first.

<h1>Testing using trace replay</h1>
As we discussed before, your mdadm implementation is a layer right above JBOD, and the purpose of mdadm is to unify multiple small disks under a unified storage system with a single address space. An application built on top of mdadm will issue a mdadm_mount and then a series of mdadm_write and mdadm_read commands to implement the required functionality, and eventually, it will issue mdadm_unmount command. Those read/write commands can be issued at arbitrary addresses with arbitrary payloads and our small number of tests may have missed corner cases that may arise in practice.

Therefore, in addition to the unit tests, we have introduces trace files, which contain the list of commands that a system built on top of your mdadm implementation can issue. We have also added to the tester a functionality to replay the trace files. Now the tester has two modes of operation. If you run it without any arguments, it will run the unit tests:

$ ./tester

running test_mount_unmount: passed running test_read_before_mount: passed running test_read_invalid_parameters: passed running test_read_within_block: passed running test_read_across_blocks: passed running test_read_three_blocks: passed running test_read_across_disks: passed running test_write_before_mount: passed running test_write_invalid_parameters: passed running test_write_within_block: passed running test_write_across_blocks: passed running test_write_three_blocks: passed running test_write_across_disks: passed

&nbsp;

If you run it with -w pathname arguments, it expects the pathname to point to a trace file that contains the list of commands. In your repository, there are three trace files under the traces directory: simple-input, linear-input, random-input. Let’s look at the contents of one of them using the head command, which shows the first 10 lines of its argument:

$ head traces/simple-input

MOUNT

WRITE 0 256 0

READ 1006848 256 0

WRITE 1006848 256 93

WRITE 1007104 256 94

WRITE 1007360 256 95

READ 559872 256 0

WRITE 559872 256 139

READ 827904 256 0

<table width="733">
<tbody>
<tr>
<td width="183">SIG(disk,block) 0</td>
<td width="550">0 : 0xb3 0x76 0x88 0x5a 0xc8 0x45 0x2b 0x6c 0xbf 0x9c 0xed 0x81</td>
</tr>
<tr>
<td width="183">SIG(disk,block) 0</td>
<td width="550">1 : 0xb3 0x76 0x88 0x5a 0xc8 0x45 0x2b 0x6c 0xbf 0x9c 0xed 0x81</td>
</tr>
<tr>
<td width="183">SIG(disk,block) 0</td>
<td width="550">2 : 0xb3 0x76 0x88 0x5a 0xc8 0x45 0x2b 0x6c 0xbf 0x9c 0xed 0x81</td>
</tr>
<tr>
<td width="183">SIG(disk,block) 0</td>
<td width="550">3 : 0xb3 0x76 0x88 0x5a 0xc8 0x45 0x2b 0x6c 0xbf 0x9c 0xed 0x81</td>
</tr>
</tbody>
</table>
WRITE 827904 256 162

The first command mounts the storage system. The second command is a write command, and the arguments are similar to the actual mdadm_write function arguments; that is, write at address 0, 256 bytes of bytes with contents of 0. The third command reads 256 bytes from address 1006848 (the third argument to READ is ignored). And so on.

You can replay them on your implementation using the tester as follows:

$ ./tester -w traces/simple-input

…

If one of the commands fails, for example because the address is out of bounds, then the tester aborts with an error message saying on which line the error happened. If the tester can successfully replay the trace until the end, it takes the cryptographic checksum of every block of every disk and prints them out on the screen, as above. Now you can use this information to tell if the final state of your disks is consistent with the final state of the reference implementation, if the above trace was replayed on a reference implementation. You can do that by comparing your output to that of the reference implementation. The files that contain the corresponding cryptographic checksums from reference implementation are also under traces directory and they end with expected-output. For example, here’s how you can test if your implementation’s trace output matches with that of reference implementation’s output for the simple-input trace:

$ ./tester -w traces/simple-input &gt;my-output

$ diff -u my-output traces/simple-expected-output

The first line replays the trace file and redirects the output to my-output file in the current directory, while the second line runs the diff tool, which compares to files contents – when the files are identical, no output is displayed, which means your implementation’s final state after the commands in the trace file matches the reference implementation’s state. If there is a difference in the diff command output, then there is a bug in your implementation; you can see which blocks contents differ and that may help you with debugging.

&nbsp;
