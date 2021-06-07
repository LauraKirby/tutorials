# Introduction to HTTP

This tutorial assumes that you have a directory called "fun-code", where you will store all of your super fun code.

We are going to get an idea of what it means to make an HTTP request via JS to get data from the internet. 

We will make an HTTP request to the Github API to retrieve data about our Github account.

## Making an HTTP GET request

1. within terminal:

- move into your directory titled "fun-code"
- create a directory called "my-github"
- move into "my-github"
- create two files: "index.html" and "http.js"
- open this directory in VSCode with "code ."

1. within VS Code:

- setup index.html with boilerplate html and include the "http.js" script.
- within "http.js", add the following code:

  ```javascript
    async function getMyRepos() {
      const response = await fetch(
        'https://api.github.com/users/MY-USERNAME/repos',
        {
          headers: {
            authorization: "token MY-TOKEN"
          }
        }
        
      );
      const movies = await response.json();
      return movies;
    }

    getMyRepos().then(responseData => {
      console.log(responseData); // fetched repos
    });

  ```

2. within the browser:

- login to your Github account.
- visit: https://github.com/settings/tokens/new
- add a description to the text box labeled "note"
- check all of the top level scopes (eg repo, workflow, write:package, etc)
- click "generate token"
- copy the token to your clipboard

3. within VS Code:

- replace "MY-TOKEN" with the value saved to your clipboard
- replace "MY-USERNAME" with your Github username

4. within the browser:

- open /fun-code/my-github/index.html
- open the developer tools
- within the console, you should see a response from Github that lists all of your repositories.

## That was magical

Now let's learn a bit of what "HTTP" means and how it allows us to get data from the internet.

The documents listed below will help us get a general idea of how HTTP requests are made and the various attributes they contain. Don't worry about memorizing every detail. Try to get a high level understanding of the following concepts:

- Purpose of HTTP
- HTTP request/response cycle
- HTTP request methods
- HTTP response codes

1. ["HTTP"](https://developer.mozilla.org/en-US/docs/Glossary/HTTP)
1. ["An overview of HTTP"](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview)
1. ["HTTP request methods"](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)
1. ["HTTP response status codes"](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)

## Additional resources

1. ["Github: Getting started with the reset API"](https://docs.github.com/en/rest/guides/getting-started-with-the-rest-api)
