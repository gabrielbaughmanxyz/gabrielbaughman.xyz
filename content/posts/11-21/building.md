---
title: "Building gabrielbaughman.xyz"
date: 2021-11-7T12:28:16-05:00
author: "Gabriel"
description: "This is how I went about creating gabrielbaughman.xyz and how you can do the same."
tags: ["Guides", "Tech", "Website"]
ShowReadingTime: true
ShowToc: true
TocOpen: true
cover:
    image: "images/building-cover.jpg" # image path/url
    alt: "abstract cover image" # alt text
    caption: "Photographer - Anni Roenkae" # display caption under cover
    relative: true # when using page bundles set this to true
    hidden: false # only hide on current single page
draft: false
---
## Why Should You Have A Website?
Well, having a website is cool and awesome. However, having your ***own*** platform to speak and present on is what the internet was all about when the .com explosion happened. In the present it seems there are a few sites that all the speaking is done on, which is making the internet more centralized. Having your own place makes you independent of these few sites.

# Getting Started
There are a lot of different ways you can create a website, but the way I did it is probably cheaper and more hands on. So, if this isn't what you are looking for then I suggest you look elsewere.

Here is what required to run a site: 
* Domain name
* Server or hardware to host on
* Software to run the site
* Creating the site

## 1. Domain Name
Some of you might not know what a domain name is, so I will explain it briefly.
A domain name is an alphabetic string that references an actual IP address. e.g example.com -> 192.123.456.789

I use [Epik](https://www.epik.com) to register mine, however there are other registers you can use.

## 2. Hosting
Once you have obtained your desired domain name you are going to want to have a place to host your site.
You can either use a VPS provider to host on, or use your own hardware and internet. Both have their benefits and downsides, but VPS hosting takes the responsibility of having hardware and good internet away so that is the one I went with. 

For my provider I went with [Vultr](https://www.vultr.com/?ref=8966022-8H) (My referral code gives you $100 and me $35 credit, which helps me keep posting). For VPS hosting the bare minimum instance available is all you really need to host a basic site and services.

If you are on Vultr click **"Deploy New Server"**
 ![vultr-deploy](../images/VultrDeploy.png)
 
For hosting a website the cheapest option is more than enough. So choose:   
1. **Cloud Compute**
2. Location
3. Operating System (It chooses Debain by default)
4. Make sure IPv6 is enabled.
![vutlr-specs](../images/vultr-specs.png)
Then you deploy.

It will take just a few moments before the server is up and running.

# Getting Up and Running

## 1. Software
When your instantance is up you will want to get it's IP address and head over to your domain register. Mine is Epik, so I will head over there.

Click the hamber menu next to your domain and in the **DNS & WHOIS** tab click **SET DNS HOST RECORDS**.
![epik-menu](../images/epik-menu.png)

Once in there click the **EXTERNAL HOSTS** tab and clear any premade records. **Make** three records for IPv4 and IPv6. in the **Host** box for IPv4 and IPv6 have one with nothing, *www*, and *. In the points to tab for the IPv4 record put the IPv4 address Vultr gives you, and the same for IPv6.
![epik-records](../images/epik-records.png)

Head back to Vultr or your provider and in the IPv6 settings add a **Reverse DNS** with your IPv6 address and your domain name.
![vultr-reversedns](../images/vultr-reversedns.png)

Now you will want to connect to your instantance either through Vultr's console interface, or use an **SSH** client to connect to it (windows has it built into CMD but you can use [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)). To connect over SSH, in your client put in your IPv4 address and the port is by default 22. The username and password is `root` with Vultr's generated password.

Once in you will want to update the system, so run (if logged in as root and on Debain or Ubuntu):

`apt update && apt upgrade`

The web server that is mainly used now is [nginx](https://nginx.org/en/), and is what I use as well. Altough, you could look into alternitives like [Apache](http://www.apache.org/).
So, you want to make sure `nginx` is installed:

`apt install nginx`

## 2. Creating the Site
You will want to navigate to `/etc/nginx`
![nginx-folders](../images/nginx-folders.png)
From here we want want to create a site that nginx will load.

**You will want to type:**

`cp sites-available/default sites-available/<yoursitename>`

Nginx has a premade template for configuring sites to load. The command we just ran will allow us to create our site based off of this template.
Now we will want to edit our copy of the template.
Debain has `nano` and `vim` installed by default, but for this example I am going to use `nano`.

**Type:** 

`nano sites-available/<yoursitename>`
![nginx-templateedit](../images/nginx-templateedit.png)
Now in this file:
- **Remove** the two lines that have `listen`. They will be replaced later.
- `root` is the location of your website's files. You can set this to whatever you want, but in this guide you will **replace** `/var/www/html` to `/var/www/<yoursitename>`.
- `server_name` is the name of your site. **Replace** `server_name _;` to       
`server_name yoursitename.com www.yoursitename.com ;`
- `location` is the location of the page that will be displayed if someone navigates to a page on your site that does not exist. You can leave this as default or have your own custom one.

Since we want this site to be ran you will need to run this command:

`ln -s sites-available/<yoursitename> sites-enabled/`

This creates a symbolic link to the `sites-enabled` folder which tells `nginx` to run the site configuration.

If you wrote a folder location that doesn't exist you will want to create it. In my example the folder location is `/var/www/<yoursitename>`
In this case, 

**Type:**

`mkdir /var/www/<yoursitename>`

To make sure our site is secure will want to enable `https` on our site. This is important because it can make a site more legit and search engines like Google will more likely display a secured website.

The tool we are going to use to do this is [Certbot](https://certbot.eff.org/).
To install **Type:**

`apt install python3-certbot-nginx`

After installing certbot **run:**

`certbot --nginx`

Go through the setup by selecting all names to activate `https`. If everything works it should do tests on the domain names and enable it.

# What Now?
Well, you can completely write your website from scratch or use a framework to build your site. In my case I am using [Hugo](https://www.gohugo.io/) to make my site. It allows me to write posts in simple Markdown files with ease, and they have plenty of nice themes to choose from.

# What's Next
This is my first post, but I plan to whenever I can write and add to this site.
