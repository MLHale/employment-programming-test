# employment-programming-test
This test is intended to check your basic competency with Ember.js and Django.

## Part 1 - Github usage
* Using your own account, fork the ember client repo  here: `https://github.com/MLHale/8470-demo-client`
* then fork the server-side code repo: `https://github.com/MLHale/8470-demo-server-side`
* modify each of their readme.md files to include your name as a new header with a 1 paragraph description under it that describes your understanding of how the combined app works (you can do this last, after you are done)
* once the readmes are complete, make a new commit and push it to each repo that your forked - add a reasonable commit message
* now create a new branch in each of your github forked repos
* clone the code in each repo to your local development environment (your PC/MAC/VM) such that the files are located side by side as: `../8470-demo-client/` and `../8470-demo-server-side`

## Part 2 - Server-side test
* follow the installation instructions in `https://github.com/MLHale/8470-demo-server-side` to install and configure django to host the demo server-side-api
* Once installed, run django following the instructions in the server-side repo
* (optional - will demonstrate you have some server-side python skills) Add a new API endpoint to the API by adding a model, serializer, viewset, and router urls.py entry for your new model
* When you are done with part 3 below, make a git commit and push your changes to your forked repo

## Part 3 - Client-side test
This is the most important part of the test - given that I am hiring someone to focus their efforts in ember. Using your forked client-side repo:
* cd into your ember client directory, e.g. `cd ~/8470-demo-client/`
* install ember dependencies following the installation directions in `https://github.com/MLHale/8470-demo-client`
* once installed, build your ember directory into the django server using the following command, `ember build --watch -o ../8470-demo-server-side/static/ember`
* This will build your ember app to be served up by django
* For the rest of the test you will work with ember files to create a new small component that displays profile information

### Creating a profile page
* First create a new route in ember: at command line `ember generate route profile` 
* Next add the profile age to the nav-bar (figure out how to do that)
* Modify the route in the router.js file to point to a dynamic segment: e.g. `this.route('profile', {path: "/profiles/:profile_id"});`
* Next in the route (e.g. /app/routes/profile, specify a model handle that gets a particular profile using an id: e.g. 
    `model: function(params){
        return this.store.findRecord('profile', params.profile_id);
    }`
* Make a new git commit with the message 'added profile route'
* Push the commit to your branch
* Now using the template for the route, display each of the profile elements using handlebars (note that the model data should live under the name 'content', so you might want to reference each field as {{content.field}}
* Make another git commit with the message 'displays profile fields' when you are done
* Push the commit to your branch on github

### Making a pull request
* On github, make a new pull request to pull your changes from the branch into your own master branch.
* Accept the pull request, but DO NOT delete your branch
* Now make a pull request on `https://github.com/MLHale/8470-demo-client` to pull in your client-side changes (by adding the related commits that you've made)
