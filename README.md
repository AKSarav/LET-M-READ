<b>LET-M-READ V1.0</b>

LET-M-READ is a Opensource Log file reader and Controller developed in Perl.
With letmread you can grant privilages to supportteams and endusers to read files 
who has basic login access to linux/unix servers, without changing the file ownership. 

Simply, LET-M-READ makes it possible for an Unprivilaged User to read files (i.e logs) using various system commands like 'more','tail','tail with f','less','cat'.

<b>FEATURES</b>
<ul>
<li>User Authentication</li>
<li>Event Log capture</li>
<li>Easy UserAddition</li>
<li>User Friendly</li>
<li>Provides more options to un privilaged user for reading files</li>
</ul>

<b>HOW TO USE?</b>
<ul list-style-type: lower-alpha;>
<li>Add the User in LET-M-READ</li>
<li>Update the Sudoers file</li>
<li>User can test it now!</li>
</ul>

<b>SOME RECOMMENDATIONS</b>
<ul list-style-type: lower-alpha;>
<li>LET-M-READ can be started as root user to make it eligible to serve most of the user needs</li>
<li>While Making Sudo Entry, If you would like to restrict the user to read only certain directories and its files. Just mention the path as a Startup Parameter (Example Given below)</li>
</ul>

For Instance, Let's say I have a user named "testuser" and I want to grant him an access to read files from the directory /opt/securedir using let-m-read. This is how it can be acheived.

<b>AddUser</b>

LET-M-READ comes with Additional Security. So its required to setup the userid.

Execute the adduser module as follows.

<pre>
./adduser
</pre>

<b>Update Sudoers File</b>

As per our requirement,  we should grant read access for only /opt/securedir to 'testuser'. 

Make sure the user "testuser" is present using 'id' command

<pre> 
id testuser
</pre>

First, you’ll need to use the visudo utility…

<pre>sudo visudo</pre>

Add the below line ( Please update the correct path of letmread)

<pre>testuser ALL=(ALL) NOPASSWD: /path/to/letemreadv1/letmread /opt/securedir</pre>

Here:

/path/to/letemreadv1/letmread -> Fully qualified location where you have uncompressed the letmread.
/opt/securedir 		      -> The Directory, for which you want to grant access to 'testuser'

Now you can communicate to the 'testuser', what is the command he has to execute and what is the let-m-read password he should use.

<b>Invoking LET-M-READ (by testuser)</b>

<pre> 
sudo /path/to/letemreadv1/letmread /opt/securedir
</pre>

That's it. Now the user can enjoy reading the file with many commands like more,tail,less etc... and as the Infrastrcuture Owner you no need to worry about changing the file permissions (or) ownership.

Note*: I presume. you have all the commands like less,more,tail,cat installled and have proper path precedence and defined environment variable $PATH. As LET-M-READ will invoke the commands without path (not like /usr/local/bin/more its just 'more')

<b>SNAPSHOTS</b>

<b>User Verification at Startup</b>

<pre>
mwi@mwi-virtual-machine$ ./letmread /opt/sara/perlscripts/letmread/gitrepo/

__________________________________________________________________________  

			 LET-M-READ V1.0 	
__________________________________________________________________________
Enter UserName:testuser
Enter Password:
Login Failed, Please ask your SystemAdmin to map your userID in LET-M-READ
system exitting

</pre>

<b>Multiple Options to read file</b>

<pre>
___________________________________________________________________________________________________________

   How do you want to read the file you have selected [ /opt/sara/perlscripts/letmread/gitrepo/adduser.pl ] ?
   For Instance: If you want to use 'more' to read the file, Type 'm' -or- 'M' 
___________________________________________________________________________________________________________

	[m/M] 'more' 		[t/T] 'tail without -f' 		[c/C] 'cat' 
	[l/L] 'less'		[tm/TM] 'tail with more'		[tf/TF] 'tail with f'

___________________________________________________________________________________________________________

Enter your option:t
</pre>

<b>The Complete TrailRun</b>

<pre> 
mwi@mwi-virtual-machine /opt/sara/perlscripts/letmread/gitrepo $ ./letemread.pl /opt/sara/perlscripts/letmread/gitrepo/

__________________________________________________________________________  

			 LET-M-READ V1.0 	
__________________________________________________________________________
Enter UserName:sara
Enter Password:
Login Successful
Performing Access Validation on /opt/sara/perlscripts/letmread/gitrepo/

INFO: Let-M-Read have proper permission to read this File (or) Directory 
 
==================================================================================================================================
S.No      LogFileName                                                                                              ModifiedDate 
==================================================================================================================================
1         /opt/sara/perlscripts/letmread/gitrepo/letemread.pl                                                      Apr12 14:45 
2         /opt/sara/perlscripts/letmread/gitrepo/adduser.pl                                                        Apr12 14:45 
3         /opt/sara/perlscripts/letmread/gitrepo/.pwfile                                                           Apr12 15:31 
4         /opt/sara/perlscripts/letmread/gitrepo/letmread.log                                                      Apr12 15:42 
==================================================================================================================================
Enter the S.No of the file you want to read==> 2

You have selected Option:'2'

Performing Access Validation on the File /opt/sara/perlscripts/letmread/gitrepo/adduser.pl 

Performing Access Validation on /opt/sara/perlscripts/letmread/gitrepo/adduser.pl

INFO: Let-M-Read have proper permission to read this File (or) Directory 
 

___________________________________________________________________________________________________________

   How do you want to read the file you have selected [ /opt/sara/perlscripts/letmread/gitrepo/adduser.pl ] ?
   For Instance: If you want to use 'more' to read the file, Type 'm' -or- 'M' 
___________________________________________________________________________________________________________

	[m/M] 'more' 		[t/T] 'tail without -f' 		[c/C] 'cat' 
	[l/L] 'less'		[tm/TM] 'tail with more'		[tf/TF] 'tail with f'

___________________________________________________________________________________________________________

Enter your option:t


How many lines you want to tail2

 
Opening the file, Please Wait !!


-FILENAME: /opt/sara/perlscripts/letmread/gitrepo/adduser.pl
-COMMAND: tail
-DATE:Tue Apr 12 15:43:20 IST 2016
 

print "\nUserName $uid has been successfully added \n\n";

</pre>


<b>EVENT LOGGING</b>

<pre>
mwi@mwi-virtual-machine /opt/sara/perlscripts/letmread/gitrepo $ cat letmread.log 
 [Apr 12 15:42:47:47]	'sara' Reading '/opt/sara/perlscripts/letmread/gitrepo/adduser.pl' with command 't'
 [Apr 12 15:43:18:18]	'sara' Reading '/opt/sara/perlscripts/letmread/gitrepo/adduser.pl' with command 't'
</pre>



For Additional Queries please write to us at admin@mwinventory.in




