# Project 1 – Static Website Hosting on AWS with Custom Domain, HTTPS, CloudFront, and WAF

## Live Website
[https://kamleshcloud.com](https://kamleshcloud.com)

---

# 1. Introduction

This project is my first end-to-end cloud project on AWS.

The purpose of this project was not only to make a website live, but to deeply understand how a real static website is hosted and delivered through cloud infrastructure.

At the beginning of this project, my website existed only as a few files on my laptop.  
By the end of the project, I had transformed those files into a publicly accessible website running on AWS, connected to my own custom domain, delivered through CloudFront, secured with HTTPS, and protected with AWS WAF.

This project helped me understand the relationship between multiple AWS services and how they work together in a real request flow.

Instead of thinking of cloud as “just uploading files somewhere,” I started understanding that a website on the internet usually involves:

- a storage layer
- a delivery layer
- a DNS layer
- a security layer
- a certificate layer

This project was the first time I saw all of those pieces come together in one working setup.

---

# 2. Project Goal

The goal of this project was:

> To take a static website built locally and deploy it on AWS using a more production-style architecture.

I wanted to learn:

- how website files are stored in the cloud
- how users access a website through a custom domain
- how HTTPS is enabled
- how CloudFront sits in front of S3
- how DNS connects a domain name to cloud infrastructure
- how AWS WAF adds an extra security layer
- how web requests move from the user to the actual website files

This project is simple enough for a beginner, but it also teaches many real cloud concepts that are useful in interviews and in real-world architecture discussions.

---

# 3. What Is a Static Website?

A static website is a website made of files that are already written and stored.

Typical files in a static website include:

- `index.html`
- `style.css`
- `script.js`
- images
- icons
- fonts

There is no backend server generating pages dynamically in this project.

The browser simply downloads these files and renders the website.

For example:

- `index.html` contains the structure of the page
- `style.css` controls how the page looks
- `script.js` controls small interactions or behavior

This type of architecture is commonly used for:

- portfolio websites
- landing pages
- company information pages
- documentation websites
- simple blogs
- marketing websites

Before doing this project, I did not fully understand that a static website can be hosted without using a traditional server.  
This project showed me that in many cases, a website can simply be served from cloud storage with the right services in front of it.

---

# 4. Final Architecture

The final architecture of this project is:

```text
User → kamleshcloud.com → Route 53 → AWS WAF → CloudFront → S3
                                     ↘ ACM Certificate used by CloudFront

## Author
Kamlesh