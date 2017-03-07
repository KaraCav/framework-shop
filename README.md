# Framework Shop

### Project Summary

In this project we will be building an ecommerce shop for the sale of JavaScript libraries. Using React Router we'll set up and navigate between the various views required. Take some time to familiarize yourself with the provided components. 

* App will be the container component for our application
* Nav is the top navigation bar
* Landing will be the home page displayed when the application first loads
* Shop will be the main shop page, displaying the items available
* Details will be the view in which a user views a single product's information
* Cart will be the user's cart

Several of these have child components, used to display products in different ways.

### Setup

Get started with the usual steps: 

* Fork and clone this repository
* `cd` into the project directory
* `npm i` to download the included dependencies
* `npm test` to start the test suite
* `npm start` to spin up the development server

### Step 1

**Summary**

In step 1 we will be installing the required dependencies, configuring the router, and rendering our application through the router.

**Instructions**

* Install React Router
* Create a new file in `src/` named `router.js`
* Configure a router in the new file
* Render the router in `src/index.js`

**Detailed Instructions**

Start out by running `npm i react-router --save` to install and save React Router to the `package.json`.  Once that installs, create a new file in `src/` named `router.js`. This file will be where we create and configure our router.

In `src/router.js` we need to import the following

* `React` from React - Because we will be using JSX to declare our routes, React must be defined in the file.
* From React Router we'll need
	* `browserHistory` - The router will need to know which [history option](https://github.com/ReactTraining/react-router/blob/master/docs/guides/Histories.md) we want to use. `browserHistory` is the native History API built into the browser.
	* `IndexRoute` - This is a special type of route, used to make sure that child routes are rendered on a base path (i.e `/`)
	* `Route` - The default component used for defining a new route
	* `Router` - The base component that will be containing all of our route configuration
* Several of the provided project components will serve as an individual view/route. We'll need the following
	* `App` from `src/components/App.js`
	* `Cart` from `src/components/Cart/Cart.js`
	* `Details` from `src/components/Details/Details.js`
	* `Landing` from `src/components/Landing/Landing.js`
	* `Shop` from `src/components/Shop/Shop.js`

Underneath the imports, we're going to export default the JSX representing our router. You probably haven't seen this elsewhere, but you can export raw JSX just fine! The top level element of the router will be the `Router` component. The `Router` component needs to know what kind of history to use, so give it a `history` prop set equal to `browserHistory`.

Now that we have an empty router, let's supply it with some routes. Place a `Route` component inside of `Router`. Each `Route` component requires two props:

* `path` - This is the path when the route will be active. For example this repo lives at `https://github.com/DevMountain/framework-shop`. The `path` for this URL would be `/DevMountain/framework-shop`
* `component` - The React component we wish to render when this route is active

Because this first route will be a wrapper of our other routes, we want its `path` to be `"/"`. Because this is a base path (you can't go any lower than `"/"`), this component will always be displayed. Why would we want a base component that is always displayed? Sometimes you have something you want on the screen regardless of where a user is in your application, like a header, footer, or info bar. Rather than including those components in every single view component, we can just have a single top level component display them!

For the `component` prop, we'll pass `App`. The `App` component renders the `Nav` component, so we can now have that top nav bar visible on every view! Inside this base route, we'll have four more routes:

* An `IndexRoute` with a `component` prop set equal to the `Landing` component. Because the `IndexRoute` is rendered as the default child of their parent, they don't need a `path` prop.
* A `Route` with a `path` of `"shop"` and a `component` of `Shop`
* A `Route` with a path of `"details/:name"` and a component of `Details`. Note that we are using a route parameter here! That means that inside of the handle component we can access the `name` parameter.
* A `Route` with a `path` of `"cart"` and a component of `Cart`

With out router configured, we can now head over to `src/index.js`. Go ahead and delete the `App` import and element, as we'll be rendering them through the router. Import `router` from `src/router.js` and display it inside of the `Provider` element like so `{ router }`.

<details>

<summary>**Code Solution**</summary>

<details>

<summary>`src/router.js`</summary>

```jsx

```

</details>

<details>

<summary>`src/index.js`</summary>

```jsx

```

</details>


</details>

## Contributions

### Contributions

#### 
 
If you see a problem or a typo, please fork, make the necessary changes, and create a pull request so we can review your changes and merge them into the master repo and branch.

## Copyright

### Copyright

#### 

© DevMountain LLC, 2017. Unauthorized use and/or duplication of this material without express and written permission from DevMountain, LLC is strictly prohibited. Excerpts and links may be used, provided that full and clear credit is given to DevMountain with appropriate and specific direction to the original content.

<img src="https://devmounta.in/img/logowhiteblue.png" width="250">