# Xepelin App

## App web-link (production):
- https://xepelin-app-7c1f38bd57c1.herokuapp.com/

## App Functionality

Xepelin App is an authentication-enabled application that includes an embedded Google Sheet. Users can edit the "Tasa" column within the Google Sheet. When a user makes an edit, it triggers a pull request containing all the relevant information for that row, such as idOp, the new rate, and the email. A webhook is configured to send an email from Xepelin to the email specified in the body, containing information about the idOp whose rate was modified, along with the corresponding changes.

- GoogleSheet Link:
https://docs.google.com/spreadsheets/d/1_6TgW-8cP3B-QdbkE0F3UJ3v9hdDw4cWXzgBu0Qt2zw

## Stack

- The app was built using Ruby on Rails with the command `rails new xepelin-app`.
- Authentication was implemented using the `devise` gem for Rails.
- To embed the Google Sheet, an `iframe` component was used for visualization within the app.
- To handle changes in the Google Sheet and send POST requests to the webhook, the AppScript extension, linked to the Google Sheet, was utilized. This code is external to the Rails application.
- Ruby version: 3.1.2
- Rails version: 7.0.1

## Development

To run the app locally, follow these steps:

1. Install dependencies: Run `bundle install`.
2. Run migrations: Execute `bin/rails db:migrate`.
3. Start the server: Run `bin/rails server` in the console to launch the server.

## Production

The deploy to production was made with heroku, follow this steps to update version:

1. Commit and push changes to master. `git commit, git push origin master`
2. Check if you have auth to access to the heroku pipeline. (Ask it to the admin: mcox5@uc.cl)
3. Login with `heroku login`
4. Upload changes with `git push heroku master`


## Commit Convention

To maintain a clean commit history, we follow the convention of using `git commit -m "feat(context): description"` for commits:

- `feat` is used for new features.
- `fix` is used for bug fixes.

## Example Commit:
- `git commit -m "feat(auth): Implement user authentication"`

## Work in differents branch
- When is doing a new feature or fix always work in a branch different to master, `git co -b branch_name` to create a new branch. Ask admin to pull request a merges.
