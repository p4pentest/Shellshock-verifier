# Shellshock-verifier

Shellshock vulnerability: Shellshock is a bash vulnerability that could allow an attacker to
execute remote code on targeted computer if exploited successfully. This vulnerability affects
bash, a command language interpreter which is found in many Linux and Unix versions.

We normally check shellshock vulnerability	by logging in and running the following command:	
	
env x="(){ :;};	echo Vulnerable" bash -c "echo Test"	
	
System	 is not Vulnerable if output of above	command is:	

Test	
	
System	 is Vulnerable	to shellshock	if output of above command	is:	

Vulnerable

Test

Script	functions as follows:	

1. Obtain list of IP address for all the Linux	machine from	a file named 'ip_list'.	
2. 
2. Try	to check whether IP Address are live	or not using ping.	
3. 
3. Put	IP Address in separate file based on whether we can ping that particular IP or not.
4. 
4. Now from the list of IP Address that we can ping say 'pingable' we try to login using given credentails and check for shellshock vulnerability in one line command and save it in variable named "result"

5. If "result value is "Test", we put that particular IP address in 'Vulnerable_ip' file.
6. 
6. If "result value is "Vulnerable", we put that particular IP address in 'Not_Vulnerable_ip' file.
7. 
7. If "result value is "Vulnerable", we put that particular IP address in 'Not_Vulnerable_ip' file.
8. 
8. If "result value is none of them, we put that particular IP address in ' Cannt_login_ip file.


Steps to run the Script:

• Include 'ip_list' file as the list of IP addresses to be scanned as hardcoded. 'ip_list' file should be there in the folder where script is present.	

• Include username and password as	hardcoded.	

• Also install a utility named	'sshpass' which is a non interactive password provider.		

• Save	the file	say as 'shellshock' and make	it executable by using	command:	

  chmod 744 shellshock	
  
• Run script using command:	

	./shellshock	
