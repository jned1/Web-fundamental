# How the Website Works  
**TryHackMe – How The Web Works**

## Introduction

A website is not just a page on the internet. It is a system made of multiple components working together: a browser, a network, a server, and often a database. What the user sees is only the final result of many invisible steps.

A simple website might only display information, while a web application allows users to interact, submit data, log in, or change content. From a security perspective, this distinction matters because applications process user input, store data, and make decisions. Each of those steps introduces risk.

Understanding how a website actually works is essential for web security because vulnerabilities do not exist in isolation. They appear when data moves between components and trust is placed in the wrong place.

---

## The Client–Server Model

The browser acts as the client. Its job is to request resources, display content, and execute code that is sent to it. It runs on the user’s machine and is fully under the user’s control.

The server hosts the website or application. It receives requests, processes logic, accesses databases, and sends responses back to the client. The server is where sensitive decisions should happen.

The boundary between client and server is one of the most important trust boundaries in web security. Anything coming from the client can be modified, replayed, or faked. Secure systems are designed with the assumption that the client cannot be trusted.

---

## From URL to Website

A URL is more than a location. It contains structured information that tells the browser how and where to connect.

The protocol defines how communication happens. The domain identifies the server. The path and parameters indicate what resource or action is being requested. Even at a high level, URLs often reveal how an application is organized internally.

Before the browser can connect, DNS resolves the domain name into an IP address. This step translates human-readable names into network-level destinations.

URLs can leak application structure because developers often map internal logic directly to paths and parameters. From a security mindset, URLs are an early source of reconnaissance.

---

## HTTP Request and Response Cycle

An HTTP request is a message sent by the client to the server asking for something. It includes a method, a path, headers, and sometimes data.

An HTTP response is the server’s reply. It includes a status code, headers, and usually a body containing content or data.

Methods like GET and POST signal intent. GET generally retrieves data, while POST usually sends data for processing. The distinction matters because it reflects how developers expect the application to be used.

Status codes are signals. They indicate success, redirection, client errors, or server errors. From a security perspective, these signals often reveal how the server handled a request, even when the response content looks harmless.

---

## Front-End vs Back-End

The front-end runs in the browser. It includes HTML for structure, CSS for appearance, and JavaScript for interaction. All of this code is visible and modifiable by the user.

The back-end runs on the server. It handles business logic, authentication, authorization, and database access. This is where security controls must live.

A common beginner misconception is assuming that front-end logic can enforce security. Any checks done in the browser exist for usability, not protection. The server must always validate and enforce rules, regardless of what the front-end does.

---

## How Dynamic Websites Work

Static content is served as-is. The server sends the same file to every user, and no decision-making happens during the request.

Dynamic websites generate responses on demand. The server runs code, processes user input, queries databases, and builds a response based on context.

User input flows from the browser to the server, through application logic, and often into storage systems. Each step in this flow is a potential failure point if assumptions are wrong or validation is missing.

Most serious web vulnerabilities exist somewhere along this data flow.

---

## Sessions, Cookies, and State (High-Level)

HTTP is stateless by design. Each request is independent and does not remember previous ones.

Websites solve this by using cookies and sessions. A cookie stored in the browser allows the server to recognize a returning client and associate it with server-side state.

This mechanism is critical for authentication. If session handling is weak, attackers can impersonate users or escalate privileges. Even at a high level, understanding that identity is maintained indirectly is key to understanding many attacks.

---

## Common Beginner Misunderstandings

Hiding elements in HTML does not protect them. Hidden fields and invisible buttons still exist in the browser and can be manipulated.

Front-end validation improves user experience but does not secure the application. Any validation that matters must happen on the server.

Appearance is often confused with behavior. A page that looks simple may trigger complex server-side logic. Security issues usually exist in what the server does, not what the page looks like.

---

## Security Mindset Takeaways

Thinking in terms of data flow is more useful than thinking in terms of pages. Data moves from user to server, through logic, and back again.

Trust boundaries define where assumptions change. The most important boundary is between the client and the server.

Most web vulnerabilities come from misunderstanding how the web actually works. When developers or testers focus only on what they see, they miss what really happens underneath.

---

## Summary

Understanding how websites work forms the foundation of web hacking and web security. Before finding vulnerabilities, it is necessary to understand how browsers, servers, protocols, and applications interact.

This knowledge turns the web from a collection of pages into a system with data flows, trust boundaries, and decision points. Every later security concept builds on this foundation.
