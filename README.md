# Data versioning in R

## The problem:

*How do you provide data to users?*

Canonical way is to [package the data](http://r-pkgs.had.co.nz/data.html)
  - updating data requires new package; difficult to have multiple versions coexisting, especially within one R session
  - github repo can become large quickly

Alternative is to wrap the data with an API
  - many examples, e.g., [the plant list](http://theplantlist.org)
  - hard to download *all* the data
  - hard to use offline (though things like [vcr](https://github.com/vcr/vcr) might help)
  - can be slow, especially in Australia
  - requires a lot of effort (and money) to set up

## Our approach

  - github releases
  - semantic versioning
  - local caching

Advantages:

  - can link data explicitly to generating / cleaning scripts (though not for baad)
  - downloaded only once per computer
  - offline access
  - fast
  - easy to port to other platforms (releases provide target)
  - can use any hosting service, e.g. could upload to figshare
  - doi when desired (i.e. when it's used for a publication)

Possible extensions:

  -  automate uploading of new releases with commit hooks, e.g. via Travis CI
  
  -  
