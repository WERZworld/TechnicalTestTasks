# Simplified WERZ app

## Brief explanation

We want to implement a very simplified version of WERZ app to evaluate basic skills and ability to work with graphQL API. Designs can be found [here](https://www.figma.com/file/gnXvPeCsz5wZhrUCEKWomG/WERZ-Test-Task?node-id=1%3A674). Note that you can run a prototype in [this page](https://www.figma.com/file/gnXvPeCsz5wZhrUCEKWomG/WERZ-Test-Task?node-id=0%3A1)

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

## Requirements

### Stack

- Use latest version of React Native.
- Use Apollo Client or React Query for processing GraphQL requests.
- **Bonus** Use [Hooks](https://reactjs.org/docs/hooks-intro.html)
- **Bonus** Use TypeScript

## How to proceed with the test task

1. Check out [existing app](https://apps.apple.com/ma/app/werz-the-good-life/id1425626243) (demo / qwerty123)  
2. Complete a technical test task;
2. Commit your code into a **private** GitHub repository
3. Invite roman@werz.at, danylo@werz.at as collaborators to that repository.

## Must-haves

- All the code must be checked by [ESLint](https://github.com/eslint/eslint).
- Use Git for version control and split your work into meaningful commits.
- Ideally the app should be deployed to Expo and available to test through Expo Go.
- Configuration and security credentials should not be stored in the code.
