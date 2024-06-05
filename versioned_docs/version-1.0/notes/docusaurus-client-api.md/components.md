---
sidebar_position: 1
---

# Components
# `<Error Boundary/>`
- Creates a react error boundary component that can create a fallback UI in case of server side rendering errors.
- The component should be wrapped around the component that may throw errors, ususally stateful react components

## Implementation
```javascript
import React from 'react';
import ErrorBoundary from '@docusaurus/ErrorBoundary';

const SafeComponent = () => (
  <ErrorBoundary
    fallback={({error, tryAgain}) => (
      <div>
        <p>This component crashed because of error: {error.message}.</p>
        <button onClick={tryAgain}>Try Again!</button>
      </div>
    )}>
    <SomeComponentThatMayThrowError />
  </ErrorBoundary>
);
```
## Props
- 'fallback': an optional render callback returning a JSX element. It will receive an object with 2 attributes: 
    - 'error', the error that was caught
    - 'tryAgain', a function (() => void) callback to reset the error in the component and try rendering it again.
    - If not present, '@theme/Error' will be rendered instead which is used for the error boundaries wrapping the site, above the layout.

# `<Head/>`
- [Ref](https://docusaurus.io/docs/docusaurus-core#head)
- creates head for the component
- head from children elements overwrite parent's head

## Implementation
```javascript
<Parent>
  <Head>
    <title>My Title</title>
    <meta name="description" content="Helmet application" />
  </Head>
  <Child>
    <Head>
      <title>Nested Title</title>
      <meta name="description" content="Nested component" />
    </Head>
  </Child>
</Parent>
```

# `<Link/>`
- [Ref](https://docusaurus.io/docs/docusaurus-core#link)
- Internal linking
- Pre-loading
    - Preloading is used to prefetch resources so that the resources are fetched by the time the user navigates with this component.
-  We use an IntersectionObserver to fetch a **low-priority request** when the `<Link/>` is in the viewport
- Then use an onMouseOver event to trigger a **high-priority** request when it is likely that a user will navigate to the requested resource.
- The component is a wrapper around **react-router’s** `<Link/>` component that adds useful enhancements specific to Docusaurus.All props are passed through to react-router’s `<Link/>` component.

- External links also work, and automatically have these props: 'target="_blank" rel="noopener noreferrer"'.

```javascript
import React from 'react';
import Link from '@docusaurus/Link';

const Page = () => (
  <div>
    <p>
      Check out my <Link to="/blog">blog</Link>!
    </p>
    <p>
      Follow me on <Link to="https://twitter.com/docusaurus">Twitter</Link>!
    </p>
  </div>
);
```

:::tip
    use this over `<a/>` tags because of the optimizations done by docusaurus
:::

# `<Redirect/>`
- Rendering a redirect navigates to a new location which overrides the current location in history stack like server side redirects

:::note
@docusaurus/router implements React Router and supports its features.
:::

```javascript
import React from 'react';
import {Redirect} from '@docusaurus/router';

const Home = () => {
  return <Redirect to="/docs/test" />;
};
```

# `<BrowserOnly/>`

- [Ref](https://docusaurus.io/docs/docusaurus-core#browseronly)
The `<BrowserOnly>` component permits to render React components only in the browser after the React app has hydrated.

```javascript
import BrowserOnly from '@docusaurus/BrowserOnly';

const MyComponent = () => {
  return (
    <BrowserOnly>
      {() => <span>page url = {window.location.href}</span>}
    </BrowserOnly>
  );
};
```

# `<Interpolate/>`
inteprolation componentt for text containing dynamic placeholders.
```javascript
import React from 'react';
import Link from '@docusaurus/Link';
import Interpolate from '@docusaurus/Interpolate';

export default function VisitMyWebsiteMessage() {
  return (
    <Interpolate
      values={{
        firstName: 'Sébastien',
        website: (
          <Link to="https://docusaurus.io" className="my-website-class">
            website
          </Link>
        ),
      }}>
      {'Hello, {firstName}! How are you? Take a look at my {website}'}
    </Interpolate>
  );
}
```
# `<Translate/>`
- supports interpolation
- provides localization
- [Ref](https://docusaurus.io/docs/docusaurus-core#translate)
## Props
- children: untranslated string in the default site locale (can contain interpolation placeholders)
- id: optional value to be used as the key in JSON translation files
- description: optional text to help the translator
- values: optional object containing interpolation placeholder values

