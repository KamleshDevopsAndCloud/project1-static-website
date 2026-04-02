# Project 1 – Static Website Hosting on AWS

## Live Website
[https://kamleshcloud.com](https://kamleshcloud.com)

## Project Summary

Built a modern static website locally using HTML, CSS, and JavaScript, and then deployed it on AWS.  
The goal of this project was not just to make a website live, but to understand how a real website is delivered on the internet using cloud services.

At the beginning, the website was just a few files on my laptop.  
By the end of the project, I had turned those files into a live website accessible through my own custom domain.

This project helped me understand:
- how static websites are hosted in the cloud
- how domain names connect to websites
- how HTTPS works
- how CloudFront sits in front of S3
- how different AWS services work together

---

## What Is a Static Website?

A static website is a website made of simple files such as:

- `index.html`
- `style.css`
- `script.js`

These files are already written and stored.  
When a user opens the website, the browser downloads these files and displays the page.

There is no backend server generating pages dynamically in this project.  
That is why it is called a **static website**.

This type of setup is commonly used for:
- personal portfolio websites
- landing pages
- documentation sites
- company information pages
- simple blogs

---

## Main Goal of This Project

The main goal of this project was:

> Take a website from my laptop and deploy it on AWS using a production-style architecture.

I wanted to understand not only **how to make a website live**, but also **how the request travels from the user to the website files**.

---

## Final Architecture

```text
User → kamleshcloud.com → Route 53 → CloudFront → S3
