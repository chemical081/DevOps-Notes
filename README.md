# Web Server


## Nginx 
- a web server
- a reverse proxy
- application load balancer


## using nginx:
Lets set up a web server with nginx:
1) going into the root user mode gives us access to all the files and folders in Linux. Another way to work as the root user would be typing "sudo" infront of every command which can be a hassle which is why we go into the root user mode by tying the command below and we proceed. Its like running as a administrator in windows.
going into the root user 
type `sudo su` <br>
![](https://github.com/chemical081/DevOps-Notes/blob/Day-5/sudo%20su.png)

2) after using user mode: <br>
The image below is what it looks like after we enter the root user mode. <br>
![](https://github.com/chemical081/DevOps-Notes/blob/Day-5/su%20mode.png)

3) get into /var/www/ :<br>
Files that we need to get it online will be saved in this directory (var/www/) like index.html, main.html, etc. For this example we are creating a index.html file where we will write a simple text make it live. First we go into the directory.<br>
![](https://github.com/chemical081/DevOps-Notes/blob/Day-5/cd%20www.png)

4) making a index.html file <br>
Below is a screenshot of making a index.html file and echoing a text written using `echo` command. another may to do this would be making a file using `touch` command and by using our `vim` editor we can write what we want to display in our website page. <br>
![](https://github.com/chemical081/DevOps-Notes/blob/Day-5/index.png)

5) We have just created a website page and we now we can move on to the next step that is deploying the website. The next steps reads the file that we just created. <br>

6) go to configure in sites-avaliable   <br>
all the configruation files are stored in etc and for the server configuration part we got to the etc directory > inside  we can find nginx > sites-avaliable <br>
![](https://github.com/chemical081/DevOps-Notes/blob/Day-5/sitees-av.png)

7) make a file > make all the configuration for the server file<br>
Now we have found where to configure, we can figure out what to configure. The image below shows what we can write to make the listen to port 80 and what to display once the request is made. <br>
![](https://github.com/chemical081/DevOps-Notes/blob/Day-5/server.png)

8) link it to the sites enabled file > restart nginx and we are good to go. <br>
We made the server configuration file in a folder that is only for storing the configuration but to sites-enabled is where the real magic happens so instead of making a same ffile in the sites-enabled, we create alink that file. <br>
`ln -sf /etc/nginx/sites-avaliable/myapp.com /etc/nginx/sites-enabled`

9) restarting nginx is required. use the following command to restart: 
`systemctl restart nginx`








Brief Overview of Commands:<br>
- `sudo apt update`
- `apt list --upgradabl`

- `sudo apt install nginx lynx`
- `cd /var/www/`
- `mkdir -p xyz`
- `cd xyz/`
- `pwd`
- `echo "This is my first app" > index.html`
- `cat index.html`
- `cd /etc/nginx/sites-available/`
- `cp default xyz.local.com`
- `vim xyz.local.com`

- `nginx -t`


- `ln -sf /etc/nginx/sites-available/xyz.local.com /etc/nginx/sites-enabled/`


- `systemctl restart nginx`
- `systemctl status nginx`




Server Configuration : <br>

```
server {
        listen 80;
        listen [::]:80;

        root /var/www/xyz;

        index index.html;

        server_name xyz.local.com;

        location / {
                try_files $uri $uri/ =404;
        }
} 
