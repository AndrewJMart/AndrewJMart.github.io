---
layout: post
title: "The Great Visible Migration"
date: 2025-12-11
gif: /assets/gifs/VisibleMigration.gif
excerpt: Developing A Backend To Support The Newsletter.
featured: false
---

Because I got tired of texting my friends and girlfriend manual notifications about new posts I decided to create a backend and newsletter for this site. If you are not turning 30 second tasks into 4 hour tasks as a programmer, you are not a programmer. All it would take is 480 posts for this endeavor to break even....

# Backend Architecture

I built the backend using [Crow](https://crowcpp.org/master/) with C++ because I needed blazing speed for my site (and all of its 5 viewers). In reality I chose Crow because I am starting a compilers course and wanted to use C++ again in preparation. The backend is hosted locally on port 928. I configured NGINX to route requests for the `/newsletter` endpoint to localhost at 928. This setup means you do not need any additional HTTPS configuration because NGINX and certbot handle that for you.  When you click the subscribe button on the home page your browser sends a HTTPS POST request to my Oracle VM. NGINX then routes this request to my backend which processes your email. Your email will be sent with a python script, stored in a sqlite db, then my backend sends a 200 response if successful.  

# What's Next?

Once I add more newsletter functionality, I am thinking a webhook that detects new posts and sends an email notification, I will be continuing my low level adventure and starting with compilers as previously mentioned.

---