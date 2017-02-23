# todoist-js
## The (un)official Todoist javascript API library
A Todoist API javascript client for full suite of endpoint resources.
This is a migration from Todoist official [Python lib](https://github.com/Doist/todoist-python).

## How to start
install the package
`npm install todoist-js --save`
into your project

## Usage
import the API
```javascript
import TodoistAPI from 'todoist-js'
```
Create an instance providing an access token
```javascript
const todoist = new TodoistAPI('xxxxxxxxxx');
```

Get productivity stats
```javascript
todoist.completed.get_stats().then(stats => {
  console.log(stats.karma_trend);
});
```
&#x1F680; You can see full list of capabilities in action into [tests folder](https://github.com/Cosmitar/todoist-js/tree/master/__tests__)

## Documentation
Official API [Docs](https://developer.todoist.com/?python#update-multiple-ordersindents) for developers

## What's next
- Implement a web oAuth2 process and document it.
- Test compatibility with Node.
- Test browsers compatibility.
- Implement a demo app using this library.

## Development / Testing
Clone this repo `git clone git@github.com:Cosmitar/todoist-js.git`.

This repo includes a Jest suite of tests, used for TDD.
Before start, make sure you create a `.env` file (you can use `.env-example` as template) and complete, as minimum requirement, the variable `ACCESS_TOKEN` with a valid user access token.
Then, install all dev dependencies by running `npm install`

&#x274C; Do not run all tests together with `npm run test` or you'll get a _max request limit per seconds_ error.

Run each suite independently like:

`npm run test -t api.spec.js`

`npm run test -t completed.spec.js`

`npm run test -t filter.spec.js`
and so on.

&#x2757; Some tests can fail due to restrictions in your account if you're not premium.

If you want to test `share.spec.js` you need first to include a 2nd access token (from a different user) into `.env` file, using variable `ALTERNATIVE_ACCOUNT_ACCESS_TOKEN`

## Contributing
Pull requests and issues are welcome. If you've found an bug, please open an issue.

## License
MIT

