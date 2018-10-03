# Eleken technical test task for full-stack developers

## Brief explanation

Create an application that allows a user to subscribe to Facebook/Twitter publications matching the keywords that can be added/removed manually for each social network separately. Think of this as a very simplified version of TweetBot or similar software.

## User stories

```
As a visitor,
I want to log in using my Facebook/Twitter account
so that my app settings will be stored at the back-end.
```

```
As a logged in user,
I want to see a feed of posts matching the keywords I've added.
```

```
As a logged in user,
I want to manage (add and remove) keywords.
```

```
As a logged in user,
I want to be able to log out.
```

## Wireframes

[Wireframes.pdf](Wireframes.pdf)

## Detailed explanation

### Front-end

- Uses Auth0 to allow users to authorize using Facebook/Twitter;
- Allows authorized users to manage (add/remove) keywords;
- Uses WebSockets/Socket.IO to listen for new posts in a real-time.

### Back-end

- Stores user's settings (keywords);
- Uses both Facebook and Twitter APIs to retrieve posts by keywords;
- Uses WebSockets/Socket.IO to stream consolidated feed to the users.

### Stack

Use React for front-end and Node.js for back-end + any libraries you're comfortable with.

## How to proceed with the test task

1. Complete a technical test task;
2. Commit your code into a repository;
3. Send us links to your repository (should be public) in addition to deployed and fully working app preview.

## Must-haves

- All the code must be checked by [ESLint](https://github.com/eslint/eslint) or [xo](https://github.com/xojs/xo).
- Use Git for version control and split your work into meaningful commits.
- Both apps must be deployed so that everyone can check it out. You can use [Now](https://zeit.co/now) + [pronto](https://github.com/vadimdemedes/pronto).
- Configuration and security credentials should not be stored in the code.
- Front-end must be built using UI frameworks with no custom styles. Use [Ant Design](https://ant.design/) (more preferable) or [Material UI](https://material-ui.com/) (less preferable).

## Nice-to-haves

- PWA.
- Documentation.
- The code is typed with a Flow.
- The code is covered with tests.
- React Native app instead of the web app as a front-end.
