This repository is for a test automation task using a dummy API Rest.

## Tests
### Manual and planning

- Chosen resource: users.
- Postman strategies used: collection and local variables, pre-request script to make each test independent.

- Test strategies:
<br />

1) Cover basic happy path cases: GET / PATCH / POST / DELETE;
<br />
2) Cover possible security breaches: assert expected errors when token is missing;
<br />
3) Cover possible front-end missing implementation like missing inputs which could damage database records;
<br />
4) Cover possible database breach testing changing user id;
<br />
5) Cover possible user experience corner cases.
<br /><br />

- User test cases:

GET

List all users;
<br />
Get user details;
<br />
Try to get details from a non existent user;

POST

Create a new user;
<br />
Try to create a already existent user;
<br />
Try to create a new user without status;
<br />
Try to create a new user missing auth token;

PATCH

Update user information;
<br />
Try to update user id;
<br />
Try to update user missing auth token;

DELETE

Delete user;
<br />
Try to delete user missing auth token;
<br />
Try to delete non existent user.

<br />

### Automated and instructions

In order to run automated tests locally:
- `yarn add global newman && yarn add newman-reporter-html`
- `yarn test:api` and all api tests will be run using Postman collections through Newman;
- Test html reports will be stored at `reports` folder.

GitHub CI:
- `api.yml` will run all API tests with Newman in every push or pull request to master branch;
- After each run reports will be uploaded and available up to 7 days;
- All actions are available [here](https://github.com/lorainegarutti/newman-api-automation-tests/actions). And there is a PR opened to trigger the action, it's available [here](https://github.com/lorainegarutti/newman-api-automation-tests/actions/runs/4681402499?pr=1) with artifacts.
