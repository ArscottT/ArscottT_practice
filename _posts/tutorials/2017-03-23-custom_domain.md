---
layout: default
title: Custom Domain
categories: Tutorials
---
<h1>Using a custom domain with github pages</h1>

So I thought I would also post a tutorial on how to use a custom domain with Github pages. It's not difficult, but sometimes can be confusing.

The initial step of cause is to buy the domain. I bought mine through namecheap because, well, they were the cheapest.

From there you have two options;

The simple option is to go to the settings tab of the project on GitHub. Scroll down untill you see the GitHub pages tab and add in your domain to the box labeled custom domain and hit save. This should create a CNAME file in your project with the custom domain inside.

The second option is to add the CNAME file manually to the project. This needs to be added to the root directory. The option I went for was to create the file through Github.

The next section differs based on where you bought your domain but the same principals apply.
Head over to your provider and find the domain, then the DNS settings. Then where your option to add a new record is.
Inside Namecheap the route follows: Advanced DNS tab > Host records section >  Add New Record
Here you will need to add two A records (Make sure it's an A record) each with the host @. One should point to: 192.30.252.153 the other to: 192.30.252.154.
Both of these are Gihubs IP addresses.

<h2>Tips:</h2>

If you add the CNAME file through github (either by adding the file manually or going to the settings tab) then remember that you will have to pull that file down to local afterwards. Otherwise your next push will erase it (I made that mistake and spent way too long trying to find out).

Inside your host records section. Make sure ou have to conflicting records. I.e. if you have more records pointing to @ than the two we added, delete them.

<h2>Additional Reading:</h2>

- For those that don't know (I didn't): [What is an A record?](https://support.dnsimple.com/articles/a-record/)
- [Namecheap guide with pictures:](https://www.namecheap.com/support/knowledgebase/article.aspx/9645/2208/how-do-i-link-my-domain-to-github-pages)
