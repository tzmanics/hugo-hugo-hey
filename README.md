 [![hugo + netlify](https://res.cloudinary.com/dzkoxrsdj/image/upload/v1656562989/template_1_edyp8b.png)](https://ntl.fyi/3P9w1mr)

# Hugo Quickstart Template   

This is a bare-bones Hugo project that has everything you need to quickly deploy it to [Netlify](https://netlify.com). 

Hate reading, here's a video: 

Love reading, here's blog post: 

## Table of Contents:

- [Quick Setup + Deploy Option](#quick-setup--deploy-option)
- [Regular Setup](#regular-setup)
  - [Cloning + Install Packages](#1-cloning--install-packages)
  - [Deploying](#2-deploying)
- [Hugo + Netlify Resources](#hugo--netlify-resources)
- [Testing](#testing)
  - [Included Default Testing](#included-default-testing)
  - [Removing Renovate](#removing-renovate)
  - [Removing Cypress](#removing-cypress)
- [Want to learn more?](#want-to-learn-more)

## Quick Setup + Deploy Option

Click this button and it will help you create a new repo, create a new Netlify project, and deploy!

[![Deploy to Netlify Button](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/netlify-templates/hugo-quickstart)

## Regular Setup

 ### 1. Cloning + Running Locally

  - Clone this repo with one of these options:

    - Click the 'Use this template' button at the top of the page
    - Or via the command line `git clone https://github.com/netlify-templates/hugo-quickstart`

 - Start the Hugo sever & check it out:

   - `hugo server -D`
   - go to [http://localhost:1313/](http://localhost:1313/)

  > Alternatively, you can run this locally with [the Netlify CLI](https://docs.netlify.com/cli/get-started/)'s by running the `netlify dev` command for more options like receiving a live preview to share (`netlify dev --live`) and the ability to test [Netlify Functions](https://www.netlify.com/products/functions) and [redirects](https://docs.netlify.com/routing/redirects/). 

  ### 2. Deploying
  - Install the Netlify CLI globally `npm install netlify-cli -g`
    
  - Run `hugo`

  - Then use the `netlify deploy` for a deploy preview link or `netlify deploy --prod` to deploy to production

  Here are a few other ways you can deploy this template:
    
  - Use the Netlify CLI's create from template command `netlify sites:create-template hugo-quickstart` which will create a repo, Netlify project, and deploy it
    
  - If you want to utilize continuous deployment through GitHub webhooks, run the Netlify command `netlify init` to create a new project based on your repo or `netlify link` to connect your repo to an existing project

## Hugo + Netlify Resources

Here are some resources to help you on your Hugo + Netlify coding fun!

- [Hugo on Netlify Integration Page](https://ntl.fyi/3P9w1mr)


Hope this template helps :) Happy coding 👩🏻‍💻!

---

## Testing

### Included Default Testing

We’ve included some tooling that helps us maintain these templates. This template currently uses:

- [Renovate](https://www.mend.io/free-developer-tools/renovate/) - to regularly update our dependencies
- [Cypress](https://www.cypress.io/) - to run tests against how the template runs in the browser
- [Cypress Netlify Build Plugin](https://github.com/cypress-io/netlify-plugin-cypress) - to run our tests during our build process

If your team is not interested in this tooling, you can remove them with ease!

### Removing Renovate

In order to keep our project up-to-date with dependencies we use a tool called [Renovate](https://github.com/marketplace/renovate). If you’re not interested in this tooling, delete the `renovate.json` file and commit that onto your main branch.

### Removing Cypress

For our testing, we use [Cypress](https://www.cypress.io/) for end-to-end testing. This makes sure that we can validate that our templates are rendering and displaying as we’d expect. By default, we have Cypress not generate deploy links if our tests don’t pass. If you’d like to keep Cypress and still generate the deploy links, go into your `netlify.toml` and delete the plugin configuration lines:

```diff
[[plugins]]
  package = "netlify-plugin-cypress"
-  [plugins.inputs.postBuild]
-    enable = true
-
-  [plugins.inputs]
-    enable = false 
```

If you’d like to remove the `netlify-plugin-cypress` build plugin entirely, you’d need to delete the entire block above instead. And then make sure sure to remove the package from the dependencies using:

```bash
npm uninstall -D netlify-plugin-cypress
```

And lastly if you’d like to remove Cypress entirely, delete the entire `cypress` folder and the `cypress.config.ts` file. Then remove the dependency using:

```bash
npm uninstall cypress
```
