Download Link: https://assignmentchef.com/product/solved-cs3423-systems-programming-assignment-0
<br>
: Getting Familiar




The goals of this assignment are as follows.

<ul>

 <li>Find the main CS lab at <strong>NPB 2.118</strong></li>

 <li>Log in to a machine with your user id</li>

 <li>Utilize some essential <strong>Unix </strong>commands</li>

 <li>Utilize <strong>vi </strong>(actually vim) and get familiar with the vi cheat sheet</li>

 <li>Create and run a simple shell script</li>

 <li>Learn to submit assignments via <strong>Blackboard</strong></li>

</ul>

This assignment refers to a <strong>setup page </strong>which can be found on Blackboard under the Miscellaneous section. In particular, you should get visit the <strong>vi cheat sheet</strong>, <strong>Unix cheat sheet</strong>, <strong>vim tutor</strong>, and <strong>ssh download </strong>if you are planning on using Windows to connect to the department machines.

<h1>Steps</h1>

<ol>

 <li>Log in to Linux</li>

</ol>

<ul>

 <li>Go to the CS Department lab at NPB 2.118. If working remotely, see how to log in remotely on the setup page and skip to step 1(e).</li>

 <li>There are two types of workstations in the lab:

  <ul>

   <li>Dell Thin Client – (left side of lab) These access the VDI (like the machines in the classrooms). To use them, see the instructions on the setup page.</li>

   <li>Linux Workstations – (right side of lab) These run Ubuntu 14.04 and are ideal for the work you will do in this course.</li>

  </ul></li>

 <li>Using a Linux workstation, log in using your <strong>abc123 </strong> Your password will be defaulted to your UTSA banner ID without the @.</li>

 <li>Open a terminal window. From the desktop menu, use <em>Applications&gt;Accessories&gt;Terminal </em>or <em>Applications&gt;Accessories&gt;LXTerminal</em></li>

 <li>Since you are using a temporary password, change your password using the <strong><sub>passwd </sub></strong> (Note that the “$” is being used to indicate that the Linux shell is prompting you for input). The actual prompt may look different (e.g., your user ID). In the terminal window, type (without the “$”):</li>

</ul>

<h2>$ passwd</h2>

<strong>Notes: </strong>If you are logging in remotely, do the following instead:

<ul>

 <li>If using Linux:</li>

</ul>

<strong>– </strong>Start a terminal window and enter the following command:

<h2>$ ssh <em>abc123</em>@fox<em>ii</em>.cs.utsa.edu</h2>

(where <em>abc123 </em>is your abc123 and <em>ii </em>is one of 01 through 06)

<ul>

 <li>If using Windows:</li>

 <li>You should install <strong>ssh </strong>(see the setup page).</li>

 <li>You can transfer files with an <strong>sftp </strong>client (<em>not </em>ftp)</li>

 <li>For both, you will specify <em>abc123</em>@fox<em>ii</em>.cs.utsa.edu to connect (where <em>abc123 </em>is your abc123 and <em>ii </em>is one of 01 through 06)</li>

 <li>In the future, consider using a virtual machine (e.g., VirtualBox), dual boot, or Cygwin.</li>

</ul>

<ol start="2">

 <li>Create a directory for this course and copy important course files to it. (You may want to check the <strong>Unix Cheat Sheet </strong>for help here).</li>

</ol>

<ul>

 <li>After logging in, check your current directory using the <strong>p</strong>rint <strong>w</strong>orking <strong>d</strong>irectory command:</li>

</ul>

<strong>$ pwd</strong>

<ul>

 <li>See what files are in your current directory:</li>

</ul>

<h2>$ ls -al</h2>

(This will show <strong>a</strong>ll files and give <strong>l</strong>ong details on them. You will notice “hidden” files beginning with a “.”.)

(c) Create a directory for this course:

<strong>$ mkdir ~/courses/cs3423 -p </strong>(d) Change to your cs3423 directory:

<h2>$ cd ~/courses/cs3423</h2>

(You should verify that you are in the directory with the <strong><sub>pwd </sub></strong>command.) (e) Copy the course materials to your directory:

<h2>$ cp /usr/local/courses/rslavin/cs3423/* . -r</h2>

(You should verify that the material was copied by using the <strong><sub>ls </sub></strong>command.)

<ol start="3">

 <li>Use the <strong>vi </strong>editor to create a simple shell script.</li>

</ol>

(a) Study the <strong>vi Cheat Sheet </strong>from the setup page. (b) (optional) Try the vi tutorial:

<h2>$ mkdir ~/tmp 2&gt; /dev/null; cd ~/tmp $ vimtutor</h2>

(follow the instructions)

(c) If you haven’t already in a prior course, create a <strong><sub>.vimrc </sub></strong>file to set up defaults in vim for indention and line numbers.

<h2>$ vi ~/.vimrc</h2>

<table width="536">

 <tbody>

  <tr>

   <td width="43">:set</td>

   <td width="494">ai sw=4</td>

  </tr>

  <tr>

   <td width="43">:set</td>

   <td width="494">number</td>

  </tr>

  <tr>

   <td width="43">:set</td>

   <td width="494">expandtab</td>

  </tr>

  <tr>

   <td width="43">:set</td>

   <td width="494">softtabstop=4</td>

  </tr>

  <tr>

   <td width="43">:set</td>

   <td width="494">smartindent</td>

  </tr>

 </tbody>

</table>

(d) Create your first script for this class using <strong>vi</strong>. <strong>Note: </strong>Be careful to type each character, including spaces, exactly as it appears below. Copying and pasting will not preserve spaces correctly.

<ol>

 <li><strong>$ cd ~/courses/cs3423</strong></li>

 <li><strong>$ mkdir assignments</strong></li>

</ol>

<h3>iii. $ cd assignments iv. $ vi cs3423a0</h3>

<ol>

 <li>Enter the following code <em>exactly </em>as it appears.</li>

</ol>

<table width="509">

 <tbody>

  <tr>

   <td width="509">#!/bin/bashif [ $# -ne 2 ]; thenecho “usage: $0 &lt;firstName&gt; &lt;lastName&gt;” exit 1fiecho “My name is $1 $2”echo “I am running this script from `pwd`” echo “My username is `whoami`” echo “I am logged in to `hostname`”</td>

  </tr>

 </tbody>

</table>

<ol start="4">

 <li>Exit your text editor and make your script executable:</li>

</ol>

<h2>$ chmod u+x ./cs3423a0</h2>

<ol start="5">

 <li>Execute your script and verify the output. In the command below, replace <em>myFirstName </em>and <em>myLastName </em>with your actual name.</li>

</ol>

<strong>$ ./cs3423a0 <em>myFirstName myLastName</em></strong>

It should print the following:

<strong>My name is <em>myFirstName myLastName</em></strong>

<strong>I am running this script from /home/<em>myUsername</em>/courses/cs3423/assignments</strong>

<h2>My username is <em>myUsername</em></h2>

<h3>I am logged in to <em>myHostName</em></h3>

<ol start="6">

 <li>You now need to save the output of your script by redirecting the output to <strong>txt</strong>.</li>

</ol>

<strong>$ ./cs3423a0 <em>myFirstName myLastName </em>&gt; a0Out.txt</strong>

<ol start="7">

 <li>Zip all your deliverables into a single zip file for turning in. Your zip file’s name should include your abc123 ID using the format in the command below. <strong>You will do this for all assignments going forward.</strong></li>

</ol>

<h3>$ zip -r <em>abc123</em>.zip cs3423a0 a0Out.txt</h3>

<ol start="8">

 <li>Upload your results to <strong>Blackboard</strong>.</li>

</ol>

<ul>

 <li>Visit <a href="http://utsa.blackboard.com/">http://utsa.blackboard.com</a><a href="http://utsa.blackboard.com/">.</a></li>

 <li>Log in with your <strong>abc123 </strong>id and passphrase.</li>

 <li>Blackboard will show a list of courses. Select <strong>CS3423 </strong>(<em>not </em>the recitation).</li>

 <li>Locate <strong>Assignment 0 </strong>under <strong>Assignments</strong></li>

 <li>Follow the directions on the screen to upload your zip file.</li>

</ul>

<strong>Note: </strong>If you created your script and zip file remotely via ssh, you will need to use either an <strong>sftp </strong>client or the <strong>scp </strong>command to move the files from the remote machine to your local one.