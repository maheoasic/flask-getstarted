# flask-getstarted
Any App consists of Code + Config, which runs on a VM or Node/
VM with basic min oS services are available on Docker.
On top of that you need to install some packages as per your App.
Your App building consists of:
Have some Directory (structure) where your code, config, etc resides.
Have some software like pyhon which runs your python code.
You may have config files that, for example, exposes your Running Code or Service on a Port.
Your code serves your App on a Port which is "exposed".
Ultimately, you run that code endlessly (listening for a Client):
$ python ./app.py &
Steps to run this Docker image on your linux host:
$ git clone https://github.com/maheoasic/flask-getstarted.git
$ cd flask-getstarted
$ podman build .  # will build a local Docker image and print image name
Example:
--> d4cbc95e405
d4cbc95e405967ca53e883d47274128fd907425a825033a94deb75a43d2689a1
Run a Container from that Image: 1st few Char's of ImageID on STDOUT are enough
$ podman run -p 8888:5000 --> d4cbc95e405
Go to browser, type "<IP-of-fedoraVM>:8888" - you should see nice Cat GIF
You may need to open port 8888 on your Fedora VirtualBox VM by:
'# firewall-cmd --add-port=8888/tcp
'# firewall-cmd --runtime-to-permanent  ## firewall rule persist REBOOTs
