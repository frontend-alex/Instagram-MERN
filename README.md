# Instagram MERN

An Instagram-style learning prototype combining a React interface with an Express authentication backend.

## Current status

Legacy learning prototype. This documentation describes the committed implementation, not a production-ready service.

## Features and implementation

- Feed/profile/sidebar interface components.
- Registration/sign-in backend with JWT helper code.
- MongoDB schemas for users, photos, and comments.
- A central server router that currently mounts the authentication controller.

## Technology

React/Create React App, JavaScript, Express, MongoDB/Mongoose, and JWT authentication.

## Repository map

| Path | Purpose |
| --- | --- |
| [client](<client>) | React browser application |
| [client/package.json](<client/package.json>) | Client scripts and dependencies |
| [server/index.js](<server/index.js>) | Express entry point |
| [server/src/router.js](<server/src/router.js>) | Mounted API routes |
| [server/src/config/db.js](<server/src/config/db.js>) | Database connection configuration |
| [server/package.json](<server/package.json>) | Server scripts and dependencies |

## Local setup

Use Node.js/npm compatible with the checked-in legacy dependencies and a local MongoDB instance. Install the server and client separately:

```bash
git clone https://github.com/frontend-alex/Instagram-MERN.git
cd Instagram-MERN/server
npm install
cd ../client
npm install
```

Create server/.env with PORT and the MongoDB variables read by the database module. The active connection uses MONGODBLOCAL_URL. Supply your own development database URI. Inspect authentication helpers for their secret configuration before testing sign-in. The server has no reliable implicit port configuration, so choose PORT to match the client's API URLs.

Start each process in a separate terminal from the repository root:

```bash
cd server
npm start
```

```bash
cd client
npm start
```

Create React App normally serves the client on http://localhost:3000. Review client API base URLs if the server port or hostname differs. 

## Verification

The client exposes the Create React App test command and a production build:

```bash
cd client
npm run build
npm test
```

The test command is interactive by default. Check whether the included tests cover application behavior rather than only the starter page. The server declares no automated test script. No build, database, authentication, or payment flow was executed during documentation work.

## Limitations and next steps

- Photo/comment schemas do not establish implemented post-management endpoints.
- Treat feed and social UI as prototype screens until backed by verified API behavior.
- Dependencies are committed under server/node_modules; install from the manifest.
- Add focused API and authentication tests before relying on behavior beyond a local demonstration.

## Code review starting points

- [server/index.js](<server/index.js>)
- [server/src/router.js](<server/src/router.js>)
- [server/src/config/db.js](<server/src/config/db.js>)
