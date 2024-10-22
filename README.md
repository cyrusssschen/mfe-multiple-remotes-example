# mfe-multiple-remotes-example

Example of setting multiple remote urls in MFE for some scenarios(ie. setting fallback urls/use multiple cdns to keep load balances).

## How to use

Run the following commands in the root directory.

```bash
yarn
yarn start
```

Navigate to:

- `http://localhost:3000` for the host app
- `http://localhost:5000` for the remote-1 app
- `http://localhost:5002` for the remote-2 app

## Host App

Pulls `<App/>` and `<Button />` from the remote app and renders them. Example:

```js
const RemoteApp = React.lazy(() => import("Remote/App"));
```

## Remote App

Exposes the modules in a `remoteEntry.js` file at:

- `http://localhost:5000/remoteEntry.js`
- `http://localhost:5002/remoteEntry.js`

`name: 'Remote'`

Exposes:

- `<App />`
- `<Button />`
