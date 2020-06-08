---
title: "Go Web Camp"
date: 2020-06-01T15:01:06+05:30
draft: false
Description: "Golang web development"
Tags: ["go", "golang", "web", "tutorial"]
Categories: []
DisableComments: false
---

So I heard there is a new language in town. Thought I should give it a try.
Here the [link](https://github.com/campoy/go-web-workshop/) from where I started my journey

## Pre-requisite

- Go lang basics
- Google cloud account
- Google cloud sdk installed via [link](https://cloud.google.com/sdk/docs/downloads-interactive)

## Hello World

- Go lang installation
- GOPATH /Users/aniarya/trails/go/
- go get <package> is installed in \$GOPATH/bin folder
- go run hello.go is the command to invoke the compilation

## HTTP client and server

- "net/http" is module that helps in routing and http server development
- "github.com/gorilla/mux" is a template library for performing GET, POST, PUT etc

## IO hanlers

- "io/util" handles the input and output operations for golang
- form data handling or data passed as POST or GET request

## App Engine

- "google.golang.org/appengine" is used to run web app on Gcloud
- `go get -u google.golang.org/appengine/...` this downloads the app engine in local machine
- Along with go file an yaml config file is also added to same directory
- Then `dev_appserver.py .` is run in same directory
- For now I am facing issue `OSError: [Errno 2] No such file or directory: '/Users/aniarya/google-cloud-sdk/platform/google_appengine/goroot-1.9/pkg/tool'`

EOD : 01-07-2020

Yesterday's issue wasn't able to solve. I think this maybe because of the outdated version of tutorial I may be using.
The tutorial was made in 2017 and I am trying it in 2020. Golang has released many updates till now. So I will have to refer to latest document to make changes and make it work. For now I am continue with tutorial for the sake of understanding basics.

## Static HTML files

- Added html file in static folder.
- `app.yaml` has routes for pointing to static files.
- hosted this on Gcloud, works okay
- Implemented backend in go file but `dev_appserver.py .` script has an error `INFO 2020-06-02 09:23:47,095 admin_server.py:150] Starting admin server at: http://localhost:8000\nERROR 2020-06-02 09:23:50,391 instance.py:284] Cannot connect to the instance on localhost:18087`
- This is taking place whether backend go file is there or not. But before when go file wasn't added then this issue wasn't there

## JSON Encoding and Decoding

- Struct defined for decoder and encoder function
- Genric function for router, seperate from main func, helps in unit testing also
- The Google App Engine issue still persists so I hosting the app directly via go files can be hosted

## Storing Data in Datastore

- Go runtime on App Engine provides a suite of packages including Clound Datastore
- `google.golang.org/appengine/datastore` is the package used for the same
- Retrival of datastore via key methods

## Retriving remote resources with urlfetch

- Application communicate with external apps via POST requests
- App Engine limits `net/http` usage for scalling purposes
- `appengine/urlfetch` module will be used along with App Engine, as it is compatible with GCP
- Used [weather](https://openweathermap.org) to test `appengine/urlfetch` for application

EOD : 02-07-2020

## Memcache with App Engine

- `appengine/memcache` which provides setter and getter function to operate on cache memory
- Memcache keeps the data for a specified amount of time and then drops it once the time is passed
- Another section based on a module of App engine, this tutorial feel more on App engine
- And my earlier issue is also related to App engine

Ok so this was the end of workshop. In the end I realised it was more about App Engine and its compatibility with the software like [mail](https://cloud.google.com/appengine/docs/go/mail/),[sendgrid](https://cloud.google.com/appengine/docs/go/sendgrid/) or [mailgun](https://cloud.google.com/appengine/docs/go/mail/mailgun).

It not bad by my understanding, I will be super efficient for a person looking to develop an application and host it on App Engine. But I was not looking of this so it felt kinda boring for me to go through this workshop.

That all. It still feels good at the end of a workshop, it's a mental trick to feel contented after finishing something.
Next I will look for developing standalone application to be deployed anywhere I like.
