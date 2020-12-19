# White Hat Hacker

## Summary

Many of the skills you've learned about APIs are the same skills (at least at
their core) that hackers will use to try and gain access to information
remotely, or to crash target servers.

We, however, try to use our abilities effectively to find holes ahead of
release, before they can negatively impact our customers.

---

## Step 1 - Postman "Hacking"

1. Take a request in Postman that you have working.
1. Change the type of request to something different:
   1. GET
   1. POST
   1. PUT
   1. DELETE
   1. etc.
1. If there are parameters, change their values, and see if the request still
   works.
1. If there is authentication required, attempt the request _without_
   authentication.

We try to be fairly intelligent, following patterns we recognize, but much of
the time this sort of guess work IS what testing an API looks like; because
finding out that "it works in a way that it _shouldn't_" is usually worse than
realizing "it doesn't work when it _should_."

---

## Step 2 - JMeter "DDOS" Attacks

DDOS stands for "Distributed Denial of Service".

- This is when multiple resources target a server/service/endpoint, and try to
  hog so much bandwidth, so many resources, that there is nothing left for
  legitimate use, or that the server even crashes. Consider, you know how to do
  this now.

In
<a href="https://github.com/DevMountain/swapi-json-server/blob/master/API_documentation.md" target="\_blank">SWAPI</a>,
we have a safe resource to practice on. \* Docs exist at
<a href="https://github.com/DevMountain/swapi-json-server/blob/master/API_documentation.md" target="\_blank">https://github.com/DevMountain/swapi-json-server/blob/master/API_documentation.md</a>

1. Using the docs listed there to find different endpoints to test, let's try
   and bring down the server.
1. Instead of testing for just ONE person, or ONE planet, request all of each of
   the endpoint's resources.
1. <a href="https://github.com/DevMountain/swapi-json-server/blob/master/API_documentation.md#images" target="\_blank">Images</a>
   in particular are resource intensive.
   - Note: to get their filenames, you'll need to look through OTHER records
     first.
1. Add threads 100 at a time to your runs.
1. Make your runs last longer.
1. Coordinate with classmates to see if more of you can get on!

If you are comfortable with your assertions, some of your tests starting to fail
while most succeed is your first indication that you might be making headway!

Otherwise, you can use the
<a href="https://github.com/DevMountain/swapi-json-server/blob/master/API_documentation.md#get-server-uptime" target="\_blank">"runtime"
endpoint</a>.

- `https://swapi.devmountain.com/meta/runtime` If you see this number set back,
  you can know that you crashed the SWAPI server and it had to reboot!

---

## Summary

Like with all of our processes; you don't want to crash something you shouldn't,
delete things that should not be deleted, just to prove that there is a problem.
Or just for fun. But darn it if you can't have a bit of fun running some tests
to try and break something and break it well!

---

## Solution

Check out the JMeter test plan
<a href="https://github.com/DevMountain/qa_playground/blob/2.10/src/solutions/2.10/SWAPI_Load.jmx" download>here</a>,
in the `2.10` branch of `qa_playground`. It has a great start towards trying to
bring down SWAPI that you can build on!
