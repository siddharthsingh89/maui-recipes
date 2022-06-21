---
title: How to Get Started
author: Tao He
date: 2022-06-20
category: Jekyll
layout: post
---

## What is XAML?
XAML stands for eXtensible Application Markup Language.
It is the recommended way to create user interfaces for .NET MAUI Apps. 

XAML is XML. All XAML files are also valid XMLs.

In a way, XAML is similar to HTML as well. Both are markup languages. And both are used to create user interfaces. While HTML targets the browsers, XAML is used to create user interfaces for MAUI applications targeting multiple platforms.

Since most of you have already had experience creating web pages in HTML and must have worked on XML in some way, you will feel right at home working on XAML.

## So how does it work?

A modern Application consists of multiple screens and often there is a definite route to navigate between them. These screens have multiple controls like labels to display text,  an input box to take user input, buttons, sliders, etc.

Often these components are in a parent-child relationship. For example, below is how a tweet is displayed. You can notice the outer tweet card has many children such as profile pic, username handle, and tweet text. These are arranged in a definite layout and retain this UI when the screen orientation is changed or the tweet is viewed on a desktop.

![Tweet card](parent_child.jpg?raw=true "A Tweet Card UI")


XAML makes it easy to define the UI. It is often more readable.
It also provides pages and various layouts to arrange these user interface controls on the pages.  
It provides all the controls like Textbox, Labels, Scroll bars, combobox., alignment and styling options and ways to interact with the user controls.

The xml-like syntax makes it easy to visualise the parent child relationship.





For example, Below XML type representation makes it easy to visualise the User interface of the tweet card and parent child relationship between individual components as compared to Code.
```
<TweetCard>
	<TweetHeader>
		<Profile Pic/><Name/><Twitter Handle/>
   <TweetHeader>
   <Tweet Text> 
        XMAL is a very succinct.....
    </TweeText>
   <Tweet Buttons>
       <Comment/> <Retweet/> <Like/><Share/>
   </TweetButtons>
<TweetCard>
```

## Advantage of XAML 
1. It is more readable, succinct.
2. Easy to visualise the parent-child relationship.
3. Suits the MVVM Model better.
4. Separates the code from the User interface.


## Disadvantages of XAML
1. It can not contain code such as If-else or loops. 
2. There are some limitations on calling methods and instantiating objects in XAML.


## How to write XAML?
We write it by hand. There is no visual tool as of now. However, the hot reload feature makes it easy to quickly see our changes in our target device as we edit our UI in XAML.
