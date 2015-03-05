---
layout: post
title:  "SQL Injection--It Hurts"
date:   2014-09-21
categories: jekyll update
<!-- tags: featured -->
image: /assets/article_images/2014-08-29-welcome-to-jekyll/desktop.jpg
---

So, what about this SQL injection?  Is it as painful as it sounds?  Well, yes.  It is a technique of inserting SQL statements into an entry field to maliciously gain access to content that was not intended for the attacker.  It is an unfortunate vulnerability of SQL.

Say I have an Netflix account (I do, and it's great, by the way).  In order to sign in, I must input my email and password. That information is submitted into the database, and if the email/password combination is valid, then I am able to access my account and the content that comes with it.

With SQL injection, though, someone could write malicious code into one of those input fields to gain access to and steal data. Not only is this bad because sensitive information might be taken, but the attacked database may also be at risk for changes or modifications by the attacker, like dropping an entire table!

here are a few things you can do to prevent SQL injection.  One is prepared statements (or parameterized queries).  These statements make the developer define all of the SQL code and then passing in each parameter to the query.  This lets the database differentiate between the code and th data.

Another defense is stored procedure, which is stored code that you can use over and over again.  This is helpful because it's stored instead of having a user input anything.

A third defense is escaping all user supplied data, because if you escape all user supplied input, then the database won't think any input is the code.

There are more ways to prevent SQL injection, but these are the primary defenses.