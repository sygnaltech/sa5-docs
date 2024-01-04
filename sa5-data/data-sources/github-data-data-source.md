# GitHub Data Data Source ⛔

{% hint style="danger" %}
**CURRENTLY SA4 ONLY**\
This datasource will be completely redesigned for SA5.
{% endhint %}

This module wraps the unsecured Github API to extract basic tag information about the specified public repository.

## Use Cases

1. Determine the tags that have been published
2. Identifying the most recent tag details, for reference in documentation

## Sample Data <a href="#results" id="results"></a>

Here's an example output of the APIs JSON.

With this, we can identify that the most recent version is `v3.371`.

```json
[
  {
    "name": "v3.371",
    "zipball_url": "https://api.github.com/repos/sygnaltech/webflow-util/zipball/refs/tags/v3.371",
    "tarball_url": "https://api.github.com/repos/sygnaltech/webflow-util/tarball/refs/tags/v3.371",
    "commit": {
      "sha": "268930f65a6bcb6a4d165b810a9807c61db2c9dc",
      "url": "https://api.github.com/repos/sygnaltech/webflow-util/commits/268930f65a6bcb6a4d165b810a9807c61db2c9dc"
    },
    "node_id": "MDM6UmVmMjA0MjgzNjk2OnJlZnMvdGFncy92My4zNzE="
  },
  {
    "name": "v3.361",
    "zipball_url": "https://api.github.com/repos/sygnaltech/webflow-util/zipball/refs/tags/v3.361",
    "tarball_url": "https://api.github.com/repos/sygnaltech/webflow-util/tarball/refs/tags/v3.361",
    "commit": {
      "sha": "7bc30227ea2582a373961d3c412c9589deaaa109",
      "url": "https://api.github.com/repos/sygnaltech/webflow-util/commits/7bc30227ea2582a373961d3c412c9589deaaa109"
    },
    "node_id": "MDM6UmVmMjA0MjgzNjk2OnJlZnMvdGFncy92My4zNjE="
  },
  {
    "name": "v3.39",
    "zipball_url": "https://api.github.com/repos/sygnaltech/webflow-util/zipball/refs/tags/v3.39",
    "tarball_url": "https://api.github.com/repos/sygnaltech/webflow-util/tarball/refs/tags/v3.39",
    "commit": {
      "sha": "fe55cf180c88131253b8ba69ad8f5b06540a16ce",
      "url": "https://api.github.com/repos/sygnaltech/webflow-util/commits/fe55cf180c88131253b8ba69ad8f5b06540a16ce"
    },
    "node_id": "MDM6UmVmMjA0MjgzNjk2OnJlZnMvdGFncy92My4zOQ=="
  },
  {
    "name": "v3.38",
    "zipball_url": "https://api.github.com/repos/sygnaltech/webflow-util/zipball/refs/tags/v3.38",
    "tarball_url": "https://api.github.com/repos/sygnaltech/webflow-util/tarball/refs/tags/v3.38",
    "commit": {
      "sha": "145eb58e7d6c9e3efe1df582fd62adf745a1fd28",
      "url": "https://api.github.com/repos/sygnaltech/webflow-util/commits/145eb58e7d6c9e3efe1df582fd62adf745a1fd28"
    },
    "node_id": "MDM6UmVmMjA0MjgzNjk2OnJlZnMvdGFncy92My4zOA=="
  },
  {
    "name": "v3.37",
    "zipball_url": "https://api.github.com/repos/sygnaltech/webflow-util/zipball/refs/tags/v3.37",
    "tarball_url": "https://api.github.com/repos/sygnaltech/webflow-util/tarball/refs/tags/v3.37",
    "commit": {
      "sha": "0d69313f817bdae03645ed849740f5fb4e3cce0a",
      "url": "https://api.github.com/repos/sygnaltech/webflow-util/commits/0d69313f817bdae03645ed849740f5fb4e3cce0a"
    },
    "node_id": "MDM6UmVmMjA0MjgzNjk2OnJlZnMvdGFncy92My4zNw=="
  },
  {
    "name": "v3.36",
    "zipball_url": "https://api.github.com/repos/sygnaltech/webflow-util/zipball/refs/tags/v3.36",
    "tarball_url": "https://api.github.com/repos/sygnaltech/webflow-util/tarball/refs/tags/v3.36",
    "commit": {
      "sha": "fe696accae699bc85102781371bb9cd74b15139c",
      "url": "https://api.github.com/repos/sygnaltech/webflow-util/commits/fe696accae699bc85102781371bb9cd74b15139c"
    },
    "node_id": "MDM6UmVmMjA0MjgzNjk2OnJlZnMvdGFncy92My4zNg=="
  },
  {
    "name": "v3.35",
    "zipball_url": "https://api.github.com/repos/sygnaltech/webflow-util/zipball/refs/tags/v3.35",
    "tarball_url": "https://api.github.com/repos/sygnaltech/webflow-util/tarball/refs/tags/v3.35",
    "commit": {
      "sha": "039822120a6561556ffe789d74e3289ab474ff6f",
      "url": "https://api.github.com/repos/sygnaltech/webflow-util/commits/039822120a6561556ffe789d74e3289ab474ff6f"
    },
    "node_id": "MDM6UmVmMjA0MjgzNjk2OnJlZnMvdGFncy92My4zNQ=="
  }
]
```

## Code example

Here's an example that loads the userOrg and repo from HTML inputs, retrieves the Github data and then displays it.

{% code overflow="wrap" %}
```html
<script type="module">
import { getGithubRepoTagsUrl, getGithubRepoTags, getGithubRepoTagLatest } from 'https://cdn.jsdelivr.net/gh/sygnaltech/webflow-util@4.11/src/datasources/github-data.min.js'; 

// On page load, load the github info
$(function () { 

  // Show the raw JSON response
  getGithubRepoTags($("#userOrg").val(), $("#repo").val()) 
    .then((res) => { 
      $("#json1").text( JSON.stringify( res, null, 2 // pretty print ) ); 
    }, (err) => { 
      console.log(err); 
    }); 
    
  // Show the latest tag version only
  getGithubRepoTagLatest($("#userOrg").val(), $("#repo").val()) 
    .then((res) => { 
      $("#latest1").text( res ); 
    }, (err) => { 
      console.log(err); }); 
    }); 
    
});
</script>
```
{% endcode %}

