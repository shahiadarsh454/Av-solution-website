1. Create the Website
Step 1: Create the HTML File
Create a file named index.html. This will be the main page of your website.
Step 2: Create the CSS File
Create a file named styles.css to style your website.
Step 3: Create the JavaScript File
Create a file named script.js if you want to include any custom JavaScript. For now, you can leave it empty or add a simple script.
2. Deploy on an Ubuntu Server
Step 1: Set Up Your Server
1.Update your server:
Install Nginx:
sh
sudo apt install nginx
art and enable Nginx:
sh
sudo systemctl start nginx
sudo systemctl enable nginx
Step 2: Upload Your Website Files
Install scp (secure copy) if not already available:
Upload your files:
Use scp to upload your files from your local machine to your server.
Step 3: Configure Nginx
Create a new Nginx configuration file:
Add the following configuration:

nginx
Copy code
server {
    listen 80;
    server_name your_domain_or_ip;

    root /var/www/html;
    index index.html;

    location / {
        try_files $uri $uri/ =404;
    }
}
Enable the new configuration:

sh
Copy code
sudo ln -s /etc/nginx/sites-available/mysite /etc/nginx/sites-enabled/
Test Nginx configuration:

sh
Copy code
sudo nginx -t
Restart Nginx:

sh
Copy code
sudo systemctl restart nginx
Step 4: Access Your Website
Open a web browser and navigate to your server's domain name or IP address. You should see your website!

Summary
You’ve created a basic website with HTML, CSS, JavaScript, and Bootstrap, and deployed it on an Ubuntu server using Nginx. 