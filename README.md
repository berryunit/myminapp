# My Minimal Application (myminapp)

![logo](./myminapp/doc/image/logo.png "logo.png") 

- Documentation: /doc/myminapp-manual-de.pdf, /doc/myminapp-manual-en.pdf
- License: MIT
- Author: berryunit

'myminapp' is a minimal but complete Python application that exemplifies how small DIY home projects can be programmed with little effort.

It offers the following features out-of-the-box:

- Complete, transparent application structure with commands, logging and data storage
- Simple usage via Python shell and integration into scripts and programs
- Application server and web frontend for HTTP(S) requests
- Time-controlled automation
- Multilingual message texts
- Various commands that can be directly useful or serve as patterns
- Easy expandability for the implementation of individual tasks

A computer running Python version 3.10 or higher is required. A USB SSD is recommended for SBCs such as Raspberry Pi, as SD cards are not suitable for continuous operation.

To install the application and execute the 'helloworld' command in different ways, proceed as follows.

## Step 1 - Install myminapp

Download the release file 'myminapp-*version*.zip' from https://github.com/berryunit/myminapp and unzip it into a directory with read and write access.

The following assumes that the file was unpacked under Linux by user 'u1' to '/home/u1/myminapp'. It is also assumed that Python version 3 can be called up on the system with 'python3'.

## Step 2 - Execute command 'helloworld' via Python shell

1. Start the Python shell in the 'home/u1' directory (above myminapp). Enter:

	python3

2. Enter the following within the Python shell:

    - from myminapp.app import App
    - app1 = App(1)
    - app1.perform_command({'cmd':'helloworld', 'value':'Hello World'})
    - app1.close()

3. Exit the Python shell with:

	exit()

## Step 3 - Execute requests via application server

Start the application server in the 'home/u1' directory (above myminapp). Enter:

	python3 -m myminapp.appserver
 
### 3.1 - Execute command 'helloworld' via CURL

Open another terminal and enter the following:

	curl --get --data-urlencode '{"cmd": "helloworld", "value": "Hello World"}' http://localhost:8081

### 3.2 - Execute command 'helloworld' via browser URL line

Open a browser and enter it in the URL line:

	http://localhost:8081/{"cmd": "helloworld", "value": "Hello World"}

### 3.3 - Execute 'helloworld' command via web frontend

1. Open a browser and enter the URL in the URL line:

    - <div style="display: inline">http://localhost:8081/app.html</div>

2. Select the command 'helloworld' and press the command execution button.

Example image (Mozilla Firefox, myminapp language setting 'de'):

![web](./myminapp/doc/image/web.png "web.png")

Terminate the application server by entering the following in the terminal:

	Ctrl+C

## Step 4 - Execute command 'helloworld' via test class

In the 'home/u1' directory (above myminapp), enter:

	python3 -m myminapp.test.command.test_helloworld

**All further information can be found in the manual:**

- /doc/myminapp-manual-de.pdf
- /doc/myminapp-manual-en.pdf