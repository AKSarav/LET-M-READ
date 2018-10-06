# LET-M-READ V1.0

An Open Source tool to grant controlled read access to unprivileged users on unix based OS. With LET-M-READ  system admins can give read access to unprivileged users without changing the file permissions.

Simply, LET-M-READ makes it possible for an Unprivilaged User to read files (i.e logs) using various system commands like 'more','tail','tail with f','less','cat'.

## Features
<ul>
<li>User Authentication</li>
<li>Event Log capture</li>
<li>Easy UserAddition</li>
<li>User Friendly</li>
<li>Provides more options to un privilaged user for reading files</li>
</ul>

<b>Supported Opearating System</b></br>
Unix based OS with Perl 5.10 and above with Switch module.
https://stackoverflow.com/questions/23314652/cant-locate-switch-pm


## Execution Outputs

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


## EVENT LOGGING

<pre>
mwi@mwi-virtual-machine /opt/sara/perlscripts/letmread/gitrepo $ cat letmread.log 
 [Apr 12 15:42:47:47]	'sara' Reading '/opt/sara/perlscripts/letmread/gitrepo/adduser.pl' with command 't'
 [Apr 12 15:43:18:18]	'sara' Reading '/opt/sara/perlscripts/letmread/gitrepo/adduser.pl' with command 't'
</pre>

<b>Installation and Configuration</b>
Please refer http://www.mwinventory.in/2016/04/letmread.html


