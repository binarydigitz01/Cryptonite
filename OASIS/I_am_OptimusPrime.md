# I am Optimus Prime
We were hardstuck on this problem because we thought initially the problem was related to sql query injection and the likes. However in our hurry we forgot to check for robots.txt. We later found the irony in the fact that Optimus Prime is a hint to robots.txt.

The robots.txt gave the /hiddenFlag url, which when we accessed first, told us that it was not going to be easy. That's because instead of using GET request, we had to use PATCH, another hint that was given in the blog post. Here is the curl command that gave us the flag:
```sh
$ curl -X PATCH https://blogpost.oasis.cryptonite.live/hiddenFlag -d "title=he&content=he"
    --cookie "user_token=ce702fb4-2d3b-4da6-ba70-ce51654ec7"```

this is assuming the fact that there was a blog post with title "he" and content "he", which my user_token had.
