# Simplified WERZ Admin panel

## Brief explanation

We are asking to implement a simplified version of WERZ admin panel to evaluate basic skills and ability to work with graphQL API. Admin panel should be based on [ReactAdmin](https://marmelab.com/react-admin/) and [ra-data-prisma](https://github.com/panter/ra-data-prisma) for connection to backend API.

### API & Staging Admin

Staging API playground is available [here](https://23759erwg9.execute-api.eu-central-1.amazonaws.com/staging/graphql). You can find documentation on queries and mutations there. Note that all admin routes are prefixed with `admin`. For example - `adminEvents`.

Also, you can use existing [staging admin panel](https://staging.admin.werz.at/) (admin / admin) as a reference.

### Functionality requirements

- Standup basic admin panel with authentication
- CRUD for User resource
- CRUD for Communities resource
- CRUD for Events resource

## How to proceed with the test task

1. Complete a technical test task;
2. Commit your code into a **private** GitHub repository
3. Invite roman.tsegelskyi@kalon.tech as collaborator to that repository.

## Must-haves

- All the code must be checked by [ESLint](https://github.com/eslint/eslint).
- Use Git for version control and split your work into meaningful commits.
- Configuration and security credentials should not be stored in the code.
