# Edit URL Parameters on Popular Sites

#### Target Time +/- 15 minutes

## Summary

After this exercise, you may start to notice how websites use their URLs to get
the right data for the page that you are on.

## Setup

Pick one or two popular websites. For our example, we'll use `amazon.com` as a
site most students will have had some experience with.

- The site needs to have some sort of interactive nature; the ability to do a
  search is an easy win.

## Step 1

1. Interact with the page. For example, do a search.
1. Copy the URL.

> Amazon:
>
> - Original URL: `https://www.amazon.com/`
> - Search Results URL: `https://www.amazon.com/s?k=wingspan&ref=nb_sb_noss_1`

Do you see any changes in the url post search?

- Changes in the path are probably path parameters and/or new endpoitns
- Is there a `?` - any key value pairs after that are query string parameters

> Amazon:
>
> - `/s` this was added to the search URL; probably the search endpoint.
> - `?k=wingspan` this is what I searched for
> - `&ref=nb_sb_noss1` I have no idea what this is about, but I can play with it
>   if I want.

## Step 2

Play with the parameters you've found.

> Amazon
>
> 1. `?k=wingspan` let's change the keyword.
> 1. `https://www.amazon.com/?k=pandemic` and submit this...
>
> - Interesting; this takes me to the homepage with "pandemic" in the search
>   bar. Oh! I left of the `/s` endpoint!
>
> 1. `https://www.amazon.com/s?k=pandemic` and submit this...
>
> - That worked!

## Step 3

Consider the apps you've looked at and the path and query string parameters
you've changed.

- Could you try and break the site with this?
- Are there security risks you can think of?

This kind of practice and mindset is going to be a huge benefit for your team!
