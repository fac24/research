# Deployment

---

## What is deployment?

"Making your software available for use"

e.g. GitHub Pages, but that's very limited.

---

## What is Heroku?

A cloud Platform as a Service (**PaaS**)

Can do a lot more than GitHub Pages!

----

### A PaaS...
...runs server infrastructure for you:

<!-- <img src="https://i.imgur.com/OJFwPEY.png" height="400"> -->


<table style="font-size: 1rem;">
    <tr>
        <td rowspan="2" style="font-size: 4rem;">🤗</td>
        <td style="background-color: dodgerblue;">Applications</td>
        <td rowspan="2">You manage</td>
    </tr>
    <tr>
        <td style="background-color: dodgerblue;">Data</td>
    </tr>
    <tr>
        <td rowspan="7" style="font-size: 4rem;">😱</td>
        <td style="color: #aaa;">Runtime</td>
        <td rowspan="7">PaaS manages</td>
    </tr>
    <tr>
        <td style="color: #aaa;">Middleware</td>
    </tr>
    <tr>
        <td style="color: #aaa;">Operating System</td>
    </tr>
    <tr>
        <td style="color: #aaa;">Virtualisation</td>
    </tr>
    <tr>
        <td style="color: #aaa;">Servers</td>
    </tr>
    <tr>
        <td style="color: #aaa;">Storage</td>
    </tr>
    <tr>
        <td style="color: #aaa;">Networking</td>
    </tr>
</table>


https://dachou.github.io/2018/09/28/cloud-service-models.html

----

### Why use a PaaS?

It's (probably) easier, faster and cheaper than doing it yourself

## 😌⌛💰

<!-- (It's complicated, time consuming and expensive to build, configure and run all the infrastructure yourself.) -->

----

### In other words:

You can **deploy** software *(and scale it)* even if you don't know how to build servers, install operating systems, configure networking, etc., etc.

---

## Heroku VS other PaaS
- Supports many languages/environments (Java, Node.js, Scala, Clojure, Python, PHP, and Go)
- Designed to host dynamic websites and apps
- Comes with its own server --> can purchase hosting plan & deploy web apps easily

---

## What are environment variables? 

A single app often runs in multiple environments (i.e. development, production).
Enviroment variables: a way to configure your code to do different things.

---

![](https://i.imgur.com/EtzuCPf.png)

---

## Why might we want to hide environment variables? 

They can contain sensitive information (passwords, API keys) that should not be in the source control.

---

## How can we deploy our Node server to a cloud provider like Heroku?

---

## Manually
Using the Heroku Command Line Interface (CLI) and git to push to heroku.

---

![](https://i.imgur.com/HQV2ivY.png)

---

## Deploying Automatically Through GitHub

----

## Setup On GitHub

- Link your Heroku app to the GitHub repo (Requires allowing OAuth access)
- Enable 'Automatic Deploys' selecting the 'main' branch.

----

## Merge Pull Requests To Main

- Have pull requests reviewed carefully and tested
- Merge to main
- Main Branch automatically redeploys the merged main branch

----

## Careful When Merging

- Make sure the merging code is in a deployable state and tests have passed
- Main <--> Test <--> any-other branch

