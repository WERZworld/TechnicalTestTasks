# Simplified WERZ app

## Brief explanation

We want to implement a very simplified version of WERZ app to evaluate basic skills and ability to work with graphQL API. Designs can be found [here](https://www.figma.com/file/865BdldmrRAk8OLtrEZLFU/WERZ-take-home?type=design&node-id=1-674&t=ayBW8HrrSQJydbcx-0).

## User stories

These user stories are a must for successful submission of the test task.

```
As a user,
I want to be able to login to WERZ app.
```

```
As an authenticated user,
I want to see the communities I am part of.
```

```
As an authenticated user,
I want to be able to enter community screen to see the event
```

## API

Staging API playground is available [here](https://23759erwg9.execute-api.eu-central-1.amazonaws.com/staging/graphql). You can find documentation on queries and mutations there. 

The following users are available to test:
- demo / qwerty123

Note that you can also use the same credentials on [WERZ app](https://apps.apple.com/us/app/werz-the-good-life/id1425626243) to explore and see the interactions

Here is a sample mutation for login

```
mutation {
  login(
    identifier: "demo",
    password: "qwerty123") {
    token
    user {
      id
      username
    }
    communities {
      id
      name
    }
    errors {
      ... on TranslatableError {
        path
      }
    }
  }
}
```

To get events, please use `events` graphql query, you can find documentation in Apollo Playground.

### FAQ about API:
- Events should be filtered by community id

## Requirements

### Stack

- Use latest version of React Native CLI or Expo.
- Preferably use React Query for processing GraphQL requests.
- **Bonus** Use [Hooks](https://reactjs.org/docs/hooks-intro.html)
- **Bonus** Use TypeScript

## How to proceed with the test task

1. Check out [existing app](https://apps.apple.com/ma/app/werz-the-good-life/id1425626243) (demo / qwerty123)  
2. Complete a technical test task;
2. Commit your code into a **private** GitHub repository
3. Invite roman@werz.at as collaborators to that repository.

## Must-haves

- All the code must be checked by [ESLint](https://github.com/eslint/eslint).
- Use Git for version control and split your work into meaningful commits.
- Ideally the app should be deployed to Expo and available to test through Expo Go.
- Configuration and security credentials should not be stored in the code.
