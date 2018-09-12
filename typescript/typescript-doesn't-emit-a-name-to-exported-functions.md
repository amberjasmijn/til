# TypeScript doesn't emit a name to exported functions

When developing an application with React and TypeScript you sometimes see `<Unknown>` components showing up in React DevTools. It turns out that TypeScript doesn't name exported functions. So when writing functional stateless components, they will be exported as anonymous functions, unless you define it as a default export.