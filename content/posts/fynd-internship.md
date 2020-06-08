---
title: "Fynd Internship"
date: 2018-08-26T10:34:08+05:30
draft: false
Description: ""
Tags: ["fynd", "internship", "summer", "web-development"]
Categories: []
DisableComments: false
---

So it was summer of 2018, I have been looking for internship in Mumbai, I got an offer from **Shopsense Retail Pvt. Ltd.**
I used to live in Malad West and the office of **Fynd** was in Andheri East. So everyday used to be catching a bus going South in the link road. Then changing there to hop into the East bound metro, which fortunately was right in front of the office building, with metro station a little of 5 min walk. There we no direct route bus so I had to take the break journey. It was and estimate of 40 minutes of journey. Sometime during return journey heavy traffic in link road made the journey more than an hour.

## Warming Up

So the first task I had was revamping the Refer and Earn page. My mentor was Jigar sir and I reported to Joseph sir. I was teamed up with a jolly fellow from ISM Dhanbad, a CS undergrade named Ravindra.

So for a initial few weeks we spent understanding the existing codebase, how things were running and noted down place we were expected to make the required changes. So broadly the entire platform was divided into couple of modules:

- _Orbis_: Backend API's
- _Megatron_ : Backend API's
- _Avis_ : Backend API's
- _Jetstorm_ : Mobile site
- _Optimus_ : Desktop site
- _Ramjet_ : Profile section

So the founders of Fynd were a big Transformers fan so the modules were named following the characters of Transformers. We didn't worm much with the backend part so _Orbis_, _Megatron_ and _Avis_ were like black box to us. Working with us on backend interns were Amit Nikam and Vijeet, both were Mubaikars. By there explaining Orbis was the big guy handling most of standard stuff as authentication, cart, etc. Megatron was responsible for inventory management while Avis was the new guy handling Machine Learning.

On the frontend _Optimus_ was loaded from all Desktop application, Optimus was developed for mobile site and tablet view. Ramjet was relatively new as the tech was planing on merging _Optimus_ and _Jetstrom_. So as of now only the profile section was merged. Refer and Earn was a component in the Profile secion itself. This part was already implement in the mobile app, which made out work easier to get in ready in web app.

The project repositories were in Gitlab and written mostly in javascript. **Markojs** was a new kind of javascript which I got used to working on the projects. Our day to day task was to meet up with Joseph sir at the start of day to update him of progress, that we used to divide the tasks between ourselves and meeting with the content team and design team to get the assets required by refer and earn page. Fify was the cutest, she was the virtual assistant on the Fynd platform.

Ramjet was build on KoaJs with Gulp to generate static files and configuration from webpack file. Similarly _Jetstorm_ was written in **MarkoJs** and **GruntJs**. Refer and Earn had two part:

- /referearn : Referral Code displayed here and options to share in on Facebook, Whatsapp, etc.
- /referearncredit : A history displaying amount you were provided by your friend or amount you shared with other along with transaction where this credit was utilised, along with a expiry date, it any

## /referearn

This part was relatively easy as it only consisted of placement of images and the unique code. Along with a modal for sharing this code with facebook or whatsapp. For _Ramjet_ the route files were itself included in the pages directory. Our first step was to add refer and earn pages into directory. Followed by it route files. These route files consisted of Router and Service to fetch relevant data for the specific page. Establishing the Routes was a little time consuming at first, but other component were present from where understood how to implement the Routes. Once the routes were setup next was task to put in the frontend components. Ramjet was using **MarkoJs** for frontend adn we spent few days to fool around and get comfortable with this new framework. The frontend part was already implemented in _Jetstrom_, so we had a place for reference whenever we got stuck. Next task was for modal box which shared code on facebook or mail. Now that we had the basics clear and did it pretty smoothly.

## /referearncredit

Similar design adaptation was required here too. Addition of new directory for credit history page consisting of route files, marko files and components. Credit page was meant to look at a user's referral credit usage along with cashback usage. We were to design two different pages and five different routes to render data in those pages. One page displayed a summary of credit/debit amound to referral and cashback. The second page was details page with breakdown of history.

- /referral/credit
- /referral/debit
- /cashback/credit
- /cashback/debit
  One the application was ready and we presented it to the team, we realised we didn't get the latest designs. Still we being interns were appreciated for the hard work. So next task was to do the design implementation again. This was like a little downtime for us as the work was already done and re doing it was a no brainer task.

## Fynterns

These times was used in getting to know other people of the company. From the very first day I knew Ketan, Moksh and Iram from marketing team. They were interns from local mumbai college working with Puneet sir. They were rarely in office and mostly out in fields doing well marketing. Later I got know Rudra, Ashwin, Akash and Manpreet working as brand interns, were also from IIT Kharagpur. Later Ishita and Xavier (she was from XLRI, real name unknown as she joined very late and was full time but used to hang with us interns) also joined the brand team. There was Ajay and Yatarth in the customer support team. Ajay used to refer to my xcode as `dark web`, he was a funny guy. There were also Rachit and Vaibhav which did join as intern but due to some reasons left after few days. All us interns used to have lunch together and were first to pantry for the same purpose. It was our aim to finish lunch early so that while others, including all our mentors are having their lunch, we used to go downstairs and roam around a little. We were interns after all, so were excited to explore around. My mentor's motto was _Sitting is the new smoking_, so I used to take a walk downstairs a lot. I was accompanied mostly with Ketan, Akash, Shubham (intern directly under Farooq Adam, one of the co-founder) and Rachit. Office culture was really good. As it was open space, so common in corporate these days, interaction with other employees gave us a unique depth about the company operations. We used to have fruits daily at 4pm and friday's were biryani specials. We use to have fruit box in pantry as a reason to step away from task. There one day we came up with the name _Fynterns_ as group of Fynd interns. A unique thing I remember was the caroom board in the pantry. Among us interns Ajay was awesome at caroom board, rest of us used to spend lot of evening at it brusing our caroom board skills. After a successful reaching of target by Puneet sir, tech did had an awesome lunch at the Leela. Well there are so many stories that I may not be able to covered in the blog.

## Products page revamp

Amidst all these Jigar used to take updates from me as Joseph was taking a few days off. The refer and earn work was smoothly handled by ravindra. So Jigar assignment to new project. I got to implement small changes in product display page, like changing filter checkbox design, adding breadcrumbs on top according to the active filters and option to remove them. Indivial product details page got a new discount info tag in top right cornor, add images scroll arrow buttons to revolve in circular manner, show the price in bottom of the card of product to make it easier for user to look at product and simultaneously look at the price too. Then I was adding seo content update for the `google-crawler-bot`. This task was assigned by Puneet sir. He used to take daily update at EOD. This development made me learn a lot about how to used Chrome developer tools and how bot crawlers work.

But the time these task was completed, Joseph was back and I got assignment to add auto scrolling sidebar feature to display active coupons. This was seeming to a little difficult task as React was a little new for me. I worked closely with Joseph to complete this task. In middle there were a few issue in refer earn module deployment. So some effort was involved in its issue fixing by me. By this time ravindra's internship period was over and he left. After the scrolling coupon task was over, Joseph released me. Still I had two week left in my internship. So Jigar assigned me to develop a demo portal with all Open Fynd API integrated. This demo was designed with purpose to help up and coming startup use Fynd platform to make their offline retail to online retail. With two week I impleted a demo application using Nodejs. That was the wrap up of my internship.

## Thank you notes

All the amazing interns and employees at fynd we essential part of my internship and I had lot of fun working alongside them. Among few were :

- Jigar Dafda
- Joseph Chirayath
- Fahim Sakri
- Puneet Sachdev
- Sarika Khaire, Head HR
- Ragini
- Ravi
- Ekwinder Saini
- Pooja Das
- Pratik Patel
- Debajit Sardar
- Karandeep Singh
- Sherya
