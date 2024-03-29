# Presterity Bookmarks app client

## Get started

**1. Install yarn:**
 Go to http://yarnpkg.com and follow the instructions for your OS.
 
**2. Install packages:**

```sh
yarn install
```
**NOTE**: Please don't use npm instead of yarn. Without yarn, you aren't guaranteed to be working with the same packages as everyone else.


> You're done installing! Now let's get started developing.

## Development Workflow

**4. Start a live-reload development server:**

```sh
yarn run dev
```

> This is a full web server nicely suited to your project. Any time you make changes within the `src` directory, it will rebuild and even refresh your browser.

**5. Testing with `mocha`, `karma`, `chai`, `sinon` via `phantomjs`:**

```sh
yarn test
```

> 🌟 This also instruments the code in `src/` using [isparta](https://github.com/douglasduteil/isparta), giving you pretty code coverage statistics at the end of your tests! If you want to see detailed coverage information, a full HTML report is placed into `coverage/`.

**6. Generate a production build in `./build`:**

```sh
yarn run build
```

> You can now deploy the contents of the `build` directory to production!

**5. Start local production server with [serve](https://github.com/zeit/serve):**

```sh
yarn start
```

> This is to simulate a production (CDN) server with gzip. It just serves up the contents of `./build`.



---


## Structure

Apps are built up from simple units of functionality called Components. A Component is responsible for rendering a small part of an application, given some input data called `props`, generally passed in as attributes in JSX. A component can be as simple as:

```js
class Link extends Component {
  render({ to, children }) {
    return <a href={ to }>{ children }</a>;
  }
}
// usage:
<Link to="/">Home</Link>
```


---


## CSS Modules

This project is set up to support [CSS Modules](https://github.com/css-modules/css-modules).  By default, styles in `src/style` are **global** (not using CSS Modules) to make global declarations, imports and helpers easy to declare.  Styles in `src/components` are loaded as CSS Modules via [Webpack's css-loader](https://github.com/webpack/css-loader#css-modules).  Modular CSS namespaces class names, and when imported into JavaScript returns a mapping of canonical (unmodified) CSS classes to their local (namespaced/suffixed) counterparts.

When imported, this LESS/CSS:

```css
.redText { color:red; }
.blueText { color:blue; }
```

... returns the following map:

```js
import styles from './style.css';
console.log(styles);
// {
//   redText: 'redText_local_9gt72',
//   blueText: 'blueText_local_9gt72'
// }
```

Note that the suffix for local classNames is generated based on an md5 hash of the file. Changing the file changes the hash.


---


## Handling URLS

:information_desk_person: This project contains a basic two-page app with [URL routing](http://git.io/preact-router).

Pages are just regular components that get mounted when you navigate to a certain URL. Any URL parameters get passed to the component as `props`.

Defining what component(s) to load for a given URL is easy and declarative. You can even mix-and-match URL parameters and normal props.

```js
<Router>
  <A path="/" />
  <B path="/b" id="42" />
  <C path="/c/:id" />
</Router>
```


---


## React Compatibility

This project includes [preact-compat] alias in as `react` and `react-dom` right out-of-the-box.  This means you can install and use third-party React components, and they will use Preact automatically!  It also means that if you _don't_ install third-party React components, `preact-compat` doesn't get included in your JavaScript bundle - it's free if you don't use it 👍

---


## License

MIT


[Preact]: https://github.com/developit/preact
[preact-compat]: https://github.com/developit/preact-compat
[webpack]: https://webpack.github.io
