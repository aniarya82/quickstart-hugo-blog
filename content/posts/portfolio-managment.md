---
title: "Portfolio Managment"
date: 2020-07-02T10:40:02+05:30
draft: false
Description: ""
Tags: []
Categories: []
DisableComments: false
---

Last semester Autumn 2019-2020, I took a subject Optimazation Methods in Finance. This subject was about defining risks associated with assets of the finance world. The subject covered topics as Value-at-Risk, Conditional Value-at-Risk, Markowitz Models, Two fund theorm, Geomory Cutting plane method, Integer Programming, Quadratic programing and Linear programming problems.

# Introduction

During semester I missed couple of classes which hindered my understanding of the subject. While preparing for mid sems it felt like a mix of financial world and operation research as it has simplex and modified simplex tables. I was bad at operation research itself and had zero financial understanding. So this mid semester exams was devestating for my marks. The classes used to be early morning ones so missed a lot of them as I was unable to wake up in time. This lead to my faliure in subject after the end semester examinations. Well this was the only elective remaining for my degree completion so I packed up from hostel and went back home in plans to come back in June for the supplementary exams of this subject. This was December and I got a job in Mastercard as a software developer, which I will be joining around July. So I had approximately six months of downtime with one subject preparations.

## Dec - Mar

Entire of December went away in relaxing and spending family time when I returned home. From January, I started preparing for exams little by little from reading the class notes itself. Giving the books chapters a little better reading go me interstered a little in stock markets and economy in general. I asked father to suscribe for Economic Times instead of The Times of India. I started spending my mornings reading the newspaper end to end and started picking up the financial jargons. For playing with stock market I started a account in money control website where I can virtual manage a portfolio. I got the understanding of index fund and mutual fund. In march there was an IPO of SBI Cards which had father's interest so he decided to open a DEMAT accound to get the IPO. He got an account open in Sharekhan, while I remember Gulshan had a kite account by zerodha, so I open an account for myself in Zerodha. Father gave me 20k to started investing in the markets, so I randomly invested in the stocks of well known complany. During holi brother visited us and he was also interest in the stock markets. He was a reading a book by Pranjal kamra about value investing. So knowing I have a accound in Zerodha, he also signed up to the same platform, and invested a initial 20k, seeing him father followed suit and invested 20k in his sharekhan account too. Little did we knew about investing when we did all this and little we did knew about what was about to his the world economy.

## April

Varsitiy by Zerodha had an amazing resource complied for reaading. So I started reading how to perform Fundamental Analysis, learnt about Technical Indicators, got introduced the Derivatives markets. I was an amazing learning experience for me, I got to know about the mistakes I did while investing early in March, know nothing of Fundamental Analysis. By April the entire country was in lockdown due to the pandemic Covid-19 and the markets took huge hits, I learned about lower circut in NSE and BSE, as it got triggered twice in month of April. As prices were so low, father bought in some more stocks at cheap prices. The SBI cards stock was a major loss in both mine and father's portfolio. He was keen on selling it away to cut losses, but I recommended against any selling in bearish markets. I got this much of understanding by reading Varsity.

## May

There was references from other books as "Fooled by Randomness" and "The Intelligent Investor". So I started with Fooled by Randomness, which was an amazing book which taught me about patience as a key for staying in markets. Entire month of May went into reading the second book "The Intelligent Investor" as it had 20 chapters so I kept one chaper per day pace and in meanwhile I was going through some Risk Managment techniques. During Risk Managment I found the intersection of my course content and was excited about testing these stuff out with Python scripts. After the book was complete I was feeling overwhelemed with so much of Finance knowledge, I thought of taking a break and letting all the things I learned in past couple of month settle in for good. I began with updating my static website and brushing up the blog.

## June

For the month of June I started revising my course work as the exam dates were getting closer. I tried to implement the risk management on my personal portfolio too. I initiated with google colab notebooks for my python scripts as I did use it for my subject's assignment submission, but the home internet was very bad and kept disconning very often. I started looking for broadband service provided at my place, but there were none players offering optical fiber connections. At last my neighbour got BSNL fiber plans so a few days later we also opted for the BSNL Fiber to the Home plans. Late June I was done with my supplementary exams, which took place online as pandemic still has the country in very in restricted movement across states. No international travel allowed by any country.

# Application Basics

Finally I planned to build a simple application were one can select couple of stocks from NSE (National Stock Exchange of India). After choosing stocks user will be promted to select the time duration to pull historical data. After these two parameters backend will crunch the Corelation matrix among the selected stocks. Later user will be asked to put in weigths for the respective stocks choosen. This will put backend to work to cruch the Expected return of the portfolio and Risk associated with the portfolio. Futher it will give option to minimize risk or maximize returns. It can even generate couple of combinations of risk and return for the Efficient Frontier curve.

## Architechture

I planned to learn a new language golang while developing this application, so I started with golang tutorials. To fetch historical data from NSE, I only found Yahoo Finance as relianbe source and no golang package support it. So I switched backend to Flask, based on python framework, and golang as frontend.

## Development

So I set out to start developing, I had bootstrap for making web page look decent and golang routing setup for processing information from flask API and present them to browser. I manually created a json of list of stocks, hoping to update them later on with entire list from NSE. First page had stocks listed along with time duration selection (1 year, 3 years, 5 years). Upon submission Post request processed data to golang which in turn process and sent to flask API, which returned correlation matrix. This correlation matrix was process in different page by golang. This page along with matrix/table also had a form to fill up weight for the respective stocks selected. Upon submission of form the golang will process the data on ping the flask API for return and risk data. Now there was an issue on the Flask side as data used for correlation matrix, return and risk calculation were same but they were being processed by different functions in python. Which should'nt be much issue as we have global variable for the purpose of sharing information. But this was supposed to be a API server, which will mix up data in global scope if multiple users will be requesting data of it. So I either have to store data in database of every user to prevent data inconsistency. But I was not planning on including database as it will as more complexing in deployment stage.

## Future work

So either I need to fix this issue of mixing up of multiple user data in flask or take all three information i.e. stocks, durations and weights, all in first page and create a single request. Later option feels a little easier as it will require simple javascript implementation. Further how will Python solve quadratic programming problems is still undiscovered by me. While reading for Optimization Methods of Finance I learnt about a few direct formulae to calcualte Minimum risk of portfolio and to calculate expected return given a fixed level of risk one can take. So I can implement direct formulae for making computations faster than actually solving quadratic programming problems.

### EOD 02/07/2020

Today we did complete the second part of the project. I simply wrote the JS code to handle the weights too in the same page. Upon form submission the golang sent a POST request to flask API consisting of three paraments `stocks`,`duration` and `weights`. The API did some number crunching and returns the portfolio's `Return` and `Risk` statistics. This is then displayed in a differnt page by golang.

## EOD 03/07/2020

Today I am planning to get this basic applicatin hosted on the Lightsail and get my work out there. I started with creating github repository for both the application.

- (PortfolioAPI)[https://github.com/aniarya82/portfolioAPI.git]
- (Portfolio-management)[https://github.com/aniarya82/portfolio-managment.git]

## AWS Lightsail deployment

I have a very bad memory, so I'll be writing down the steps in as detail as possible as it will act as a recap for myself when something goes wrong, or when I need to replicate it somewhere else.

### Amazon Linux instance

- Logged into the AWS Console, launched an lightsail instance the first month free one.
- SSH into the Amazon Linux instance created just now.
- Very first issue faced is the LC_LOCALE. This issue was resolve by editing the `/etc/environment` file. I added following lines there `LANG=en_US.utf-8 LC_ALL=en_US.utf-8`. After this logged out and logged back in to find it was fixed. Yay
- Ran the update command `sudo yum update`.
- Next up is to install the golang onto the instance `sudo yum install -y golang`.
- Next I looked up Go environment variable `GOROOT='/usr/lib/golang/`,`GOPATH=/home/ec-user/go`.
- As the go directory didn't exist I created the directory `mkdir go` and then `mkdir go/src`.
- I cloned the portfolio-management app in the src folder and ran the `go run main.go` command, which gave error `main.go:12:2: cannot find package "github.com/gorilla/mux"`
- To install the mux router `go get -u github.com/gorilla/mux`. I should also include this installation command in the repository's README.
- After installation I tried to run again`go run main.go`. This time nothing happened, no error but the program exited.
- Disappointed now in golang's persepective. Looking into nginx and golang digitalocean (docs)[https://www.digitalocean.com/community/tutorials/how-to-deploy-a-go-web-application-using-nginx-on-ubuntu-18-04]
- This digital ocean tutorial had some prerequisite `Ubuntu serve (check)`,`go lang installed (check)`,`Nginx installed`.Tried to install nginx then `sudo yum install -y nginx`. Followed by uncomplicated firewall setup `sudo ufw app list`. But AMI failed to recognice any `ufw` installed even. DOUBLE Disappointement.
- Well Amazon Linux was too much for me so I destroyed the Lightsail instance.

### Ubuntu 18.04 instance

- Created the instance and logged into it.
- Will follow the DigitalOcean doc line by line now.
- Step 1 was done of getting a ubuntu instance.
- Step 2 was to get golang in ubuntu.(link)[https://www.digitalocean.com/community/tutorials/how-to-install-go-and-set-up-a-local-programming-environment-on-ubuntu-18-04]
- Step 3 was to install Nginx in ubuntu. (link)[https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-18-04]

So while setting up nginx server it required a domain to be setup. So I went with portfolio.hiten.io. This domain of mine till today was simply hosting a github pages website so Namecheap had the Nameserer access of it. So I contacted my brother for this. He recomended to shift to Cloudfare free service. So we added Nameserver to Cloudfare and then I explained him the app. He told me we don't actually require the Nginx reverse proxy as golang itself runs on port 80. We do reverse proxy setup when the application by default doesnt runs on port 80, so we setup nginx to listen on port 80 and then redirect traffic to port 5000 as in case of flask. Then I was directly importing everything of the github for golang. He suggested to create a build locally and just scp the build file and not the entire project.
`dpkg --print-architecture` gives the architecture of ubuntu server
`env GOOS=linux GOARCH=amd64 go build main.go` This creates a build file for remote server.
Then we can scp this file to server and run over there.
We did all this but still golang application was facing some issues.
`sudo netstat -plunt` This give all service running on various ports
`sudo service portfolio-api start` created a systemd file for this
So after looking at other examples online I figures out to `log.Fatal(http.ListenAndServe(":80", r))` which will log the error
I build it locally and then scp to the ubuntu server. Upon executing error was `listen tcp :80: bind: permission denied`.
Well then I created the `sudo nano /lib/systemd/system/goweb.service` and pointed it at `/home/ubuntu/go/portfolio-managment/main`. And started it as a service, then it ran properly. Now I need to go through its logs to figure out why it is failing. So journalctl provides log for the systemd services. `journalctl -u goweb -n 25` gives last 25 lines of the log file.
Now the issue is there about static files not getting proper path.

### EOD 04/07/2020
