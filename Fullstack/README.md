# Simplified app

## Brief explanation

This task consists of 2 parts:
1. Augmenting the existing API
2. Creating a front-end for the API

# Augmenting the existing API

You are provided with an API skeleton and we want you to add functionality to it.

## Getting started

1. Clone the [base repository](https://github.com/kalontech/api-test-task).
2. Install necessary dependencies and run it. To test, go to http://localhost:4000/development/graphql and run the following query
    ```
    query {
      users {
        username
      }
    }
    ```
3. Get familiar with [Prisma](https://www.prisma.io/docs/) and [Nexus](https://nexusjs.org/docs/plugins/prisma).
4. Explore existing models in [schema file](https://github.com/kalontech/api-test-task/blob/master/prisma/schema.prisma).

## Task 1

Currently there are 2 models in the database - User and Community. We want to add a connection between those models. Each community can have members and users should be able to join a community

### How to proceed/requirements

- In [schema](https://github.com/kalontech/api-test-task/blob/master/prisma/schema.prisma) add [many-to-many relation](https://www.prisma.io/docs/concepts/components/prisma-schema/relations) between User and Community. User can be member of many communities and Community can have many members
- Expose newly added fields in [types](https://github.com/kalontech/api-test-task/tree/master/src/graphql/types)
- Complete [joinCommunity](https://github.com/kalontech/api-test-task/blob/master/src/graphql/resolvers/join-community.ts) mutation, which should allow users to join a community

## Task 2

There is a requirement to add a new model to the database - Event. Communities can have events and users can register for events.

### How to proceed/requirements

- In [schema](https://github.com/kalontech/api-test-task/blob/master/prisma/schema.prisma) add Event model [many-to-many relation](https://www.prisma.io/docs/concepts/components/prisma-schema/relations) between User and Event and Community and Event. Communities can have events and users can register for events.
- Expose newly added fields in [types](https://github.com/kalontech/api-test-task/tree/master/src/graphql/types)
- Complete [registerForEvent](https://github.com/kalontech/api-test-task/blob/master/src/graphql/resolvers/register-for-event.ts) mutation, which should allow users to register for events.

## How to submit part 1

1. Complete a requirements to the best of your ability;
2. Commit your code into a **private** GitHub repository
3. Invite roman.tsegelskyi@kalon.tech, artem.kosiakevych@kalon.tech as collaborators to that repository.

# Creating a front-end for an existing API

We want to implement a very simplified version of one of our projects app to evaluate basic skills and ability to work with graphQL API. Designs can be found [here](https://www.figma.com/file/BOzAEEdWjbxFYSyzbtC6nM/Fullstack-Test-Task?node-id=1%3A674). Note that you can run a prototype in [this page](https://www.figma.com/file/gnXvPeCsz5wZhrUCEKWomG/WERZ-Test-Task?node-id=0%3A1). We only ask to implement a responsive version, for desktop, just center the screens.


## User stories

These user stories are a must for successful submission of the test task.

```
As a user,
I want to be able to login to WERZ app.
```

```
As an authenticated user,
I want to see the communities I am part of by swiping up the screen
```

```
As an authenticated user,
I want to be able to switch between communities by clicking on the community icon
```

## API

Staging API playground is available [here](https://23759erwg9.execute-api.eu-central-1.amazonaws.com/staging/graphql). You can find documentation on queries and mutations there. 

The following users are available to test:
- test_werz_1 / qwerty123
- test_werz_0 / qwerty123

Here is a sample mutation for login

```
mutation {
  login(
    identifier: "test_werz_1",
    password: "qwerty123") {
    token
    user {
      id
      username
    }
    communities {
      id
      name
      styleOverride
    }
    errors {
      ... on TranslatableError {
        path
      }
    }
  }
}
```

## Suggested stack

- Use latest version of React.
- Use Apollo Client or React Query for processing GraphQL requests.
- **Bonus** Use [Hooks](https://reactjs.org/docs/hooks-intro.html)
- **Bonus** Use TypeScript

## How to proceed with the test task

1. Complete a technical test task;
2. Commit your code into a **private** GitHub repository
3. Invite roman.tsegelskyi@kalon.tech, artem.kosiakevych@kalon.tech as collaborators to that repository.

## Must-haves

- All the code must be checked by [ESLint](https://github.com/eslint/eslint).
- Use Git for version control and split your work into meaningful commits.
- Ideally the app should be deployed to [Netlify](https://www.netlify.com/with/react/) or similar.
- Configuration and security credentials should not be stored in the code.
