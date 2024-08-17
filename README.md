This is a reproduction for a Next.js issue

1. Run `pnpm install`
1. Run `pnpm dev`
1. Open `http://localhost:3000/`
1. Open browser devtools
1. open `src/app/page.tsx` and replace the content with

   ```tsx
   import { Alert, Button } from "@mui/material";

   export default function Home() {
     return (
       <div>
         <Button>foo</Button>
         <Alert severity="error">This is an error alert — check it out!</Alert>
       </div>
     );
   }
   ```

1. Save

The page reloads and a series of warnings and errors appears:

```
TypeError: Cannot read properties of undefined (reading 'call')
    at options.factory (webpack.js?v=1723876266036:713:31)
    at __webpack_require__ (webpack.js?v=1723876266036:37:33)
    at fn (webpack.js?v=1723876266036:369:21)
    at initializeModuleChunk (react-server-dom-webpack-client.browser.development.js:906:27)
    at readChunk (react-server-dom-webpack-client.browser.development.js:779:11)
    at react-stack-bottom-frame (react-dom-client.development.js:22220:18)
    at beginWork (react-dom-client.development.js:9348:24)
    at runWithFiberInDEV (react-dom-client.development.js:540:16)
    at performUnitOfWork (react-dom-client.development.js:14831:22)
    at workLoopConcurrent (react-dom-client.development.js:14825:9)
    at renderRootConcurrent (react-dom-client.development.js:14800:15)
    at performConcurrentWorkOnRoot (react-dom-client.development.js:14143:11)
    at MessagePort.performWorkUntilDeadline (scheduler.development.js:44:48)

The above error occurred in the <NotFoundErrorBoundary> component.

React will try to recreate this component tree from scratch using the error boundary you provided, ReactDevOverlay.
```

```
[Fast Refresh] performing full reload

Fast Refresh will perform a full reload when you edit a file that's imported by modules outside of the React rendering tree.
You might have a file which exports a React component but also exports a value that is imported by a non-React component file.
Consider migrating the non-React component export to a separate file and importing it into both files.

It is also possible the parent component of the component you edited is a class component, which disables Fast Refresh.
Fast Refresh requires at least one parent function component in your React tree.
```
