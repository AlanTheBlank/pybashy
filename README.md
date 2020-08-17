# pybashy

    - framework for leveraging python to run sets of shell commands for specific tasks. 
    
    - Command Sets are stored as dicts in seperate files and loaded dynamically.

Basic structure of an extension/script is as thus

    steps = { 'ls_user' : ["ls -la ~/", "[+] Command Sucessful", "[-]  Command Failed! Check the logfile!"],
		 'ls_root' : ["ls -la /", "[+] Command Sucessful!", "[-]  Command Failed! Check the logfile!"],
		 'ls_etc'  : ["ls -la /etc", "[+] Command Sucessful", "[-] ls -la Failed! Check the logfile!"]
        	}
    success_message = "[+] Test Sucessful!"
    failure_message = "[-] Test Failure!"
    
    
only one set of commands can be at the top level of a file
  - Multiple sets can be placed in thier own unique functions
  - functions MUST START with "function"
  - many of these allowed
  

    def function_test_function1(params):
      steps = { 'ls_user' : ["ls -la ~/", "[+] Command Sucessful", "[-]  Command Failed! Check the logfile!"],
		     'ls_root' : ["ls -la /", "[+] Command Sucessful!", "[-]  Command Failed! Check the logfile!"],
		     'ls_etc'  : ["ls -la /etc", "[+] Command Sucessful", "[-] ls -la Failed! Check the logfile!"]
			    }
	   success_message = "[+] Test Sucessful!"
	   failure_message = "[-] Test Failure!"
