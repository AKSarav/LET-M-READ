<b>LET-M-READ V1.0</b>

LET-M-READ is a Opensource Log file reader and Controller developed in Perl.
With letmread you can grant privilages to supportteams and endusers to read files 
who has basic login access to linux/unix servers, without changing the file ownership. 

<b>FEATURES</b>
<ul>
<li>UserBased Security</li>
<li>Event Log capture</li>
<li>Easy UserAddition</li>
</ul>

<b>HOW TO USE?</b>
<ul list-style-type: lower-alpha;>
<li>Add the User</li>
<li>Invoke LET-M-READ with Fully Qualified Directory Name</li>

</ul>

<i>AddUser</i>

<pre>
mwi@mwi-virtual-machine /opt/sara/perlscripts/letmread/gitrepo $ ./adduser.pl 
====================================================================================================
				LET-M-READ|WWW.MWINVENTORY.IN
====================================================================================================
	LET-M-READ is a Freeware Log file reader and Controller,
	With letmread you can grant privilages to supportteams and endusers to read files 
	who has basic login access to Server, without changing the file ownership. 
	For Additional Queries please write to us at admin@mwinventory.in
====================================================================================================

---LET-M-READ ADDUSER NAME TOOL---


Enter UserName:sara

Enter Password:
UserName sara has been successfully added 


</pre>

<i>Invoke letmread</i>

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
==================================================================================================================================
Enter the S.No of the file you want to read==> 

</pre>

<b>User Verification at Startup</b>

<pre>
mwi@mwi-virtual-machine /opt/sara/perlscripts/letmread/gitrepo $ ./letemread.pl /opt/sara/perlscripts/letmread/gitrepo/

__________________________________________________________________________  

			 LET-M-READ V1.0 	
__________________________________________________________________________
Enter UserName:sara
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




