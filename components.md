# Components



## Component Tree Architecture

For components, we have established a pattern for you to use throughout your application. Each directory should consist of a single feature. That **does NOT** mean that you need to have a single file per component. You can have as many files as you'd like in a component directory. You should also feel at liberty to include multiple components in a file where you see fit. **It DOES** mean that you should organize all the pieces of your component into an `index.js` file and export out that single component to be used throughout your app.

**Rules to live by when approaching components**

* Your `components` should focus on solving a singular problem/performing some operation in order to allow users to interact with the data your application serves up.
* `Container` components are where you craft out your feature by combining some logic/UI/components together.
  * It's a good idea to use `common` \(reusable\) components inside your containers.
* Be sure to import/export your container component out of the `index.js` file so that you can easily import it throughout your application.

![example list component](https://tk-assets.lambdaschool.com/2f650085-d27c-47b6-a8ea-a5c4ee53d039_ScreenShot2020-06-25at8.18.47AM.png)

* A good example of what we're trying to achieve here can be found in the `ExampleListComponent` directory.
* The `RenderExampleList.js` file is used to operate on the iterator \(.map\) function and focuses on one singular issue, displaying data. \(Notice the use of `proptypes`\).
* The `ExampleListContainer.js` pieces everything together nicely and takes care of the formal logic.
* `index.js` simply imports and exports the component for easy use later.

## /pages

* This is the directory where all of your page-related components will live. We can classify a page as any container that is passed to a `Route` within our main app `index.js` file:

```javascript
// index.js

<Route path="/example-page" component={ExamplePage} />
```

* In the above example, we would classify the `ExamplePage` component as a page and create an `/ExamplePage` folder for it to live in.
* The basic structure of a page is made up of 3 files: a `Container` component, a `Render` component, and an `index` file. `Container` components are where all of your stateful logic and API request code related to the page should live. We use the `Container` component to calculate the data that we want the `Render` component to show on our UI. `Render` components are pure components that _only_ receive props and return JSX elements to be rendered to our UI. Our `index` file is what we use to configure the name of our page's export.

