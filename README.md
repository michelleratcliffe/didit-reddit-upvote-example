## Upvote

Upvote is a Reddit-esque web application that allows users to create posts, upvote and downvote posts, and comment on posts in a multi-threaded, nested list.

The project is built using Next.js with the /app router and [Tailwind CSS](https://tailwindcss.com/), and uses [Auth.js (formerly Next Auth)](https://authjs.dev/) for user authentication. The data is stored in a Postgres database, which is created and accessed with raw SQL queries using the `pg` package.

The project is a work in progress and is not yet complete.

## Features

- [x] View a list of posts
- [x] View a single post
- [x] Create a post
- [x] Upvote and downvote posts
- [x] Pagination of posts
- [x] Comment on posts
- [x] Nested comments (recursive lists)
- [x] User authentication

## Setup instructions

1. Fork the repository (check "copy the main branch only") and clone your fork to your local machine
2. Run `npm install`
3. Create a `.env.local` file in the root directory and add the following environment variables:
   - `DATABASE_URL` - the URL of your Postgres database (eg. the Supabase connection string)
   - `AUTH_SECRET` - the Next Auth secret string (this can be anything at all like a password, but keep it secret!)
   - `AUTH_GITHUB_ID` - the GitHub OAuth client ID (create yours in [Github developer settings](https://github.com/settings/developers)
   - `AUTH_GITHUB_SECRET` - the GitHub OAuth client secret (create this in [Github developer settings](https://github.com/settings/developers))
4. Create the database schema by running the SQL commands in `schema.sql` in your database (eg. by running the commands in Supabase Query Editor)
5. Run `npm run dev` to start the development server
6. Open [http://localhost:3000](http://localhost:3000) with your browser to see the site

## Potential future features

- [ ] User profiles
- [ ] Sorting posts by recent (date posted), top (most upvotes), and most controversial (most upvotes _and_ downvotes)
- [ ] User karma scores
- [ ] User badges / trophies (awards for achievements like number of posts, years on the site, etc.)
- [ ] User settings (eg. number of posts per page, theme, etc.)
- [ ] Moderation tools / reporting or flagging objectionable comments for removable by admins
- [ ] Searching posts (possibly using simple SQL LIKE '%some search%', or [Postgres text search](https://www.crunchydata.com/blog/postgres-full-text-search-a-search-engine-in-a-database))
- [ ] Subreddits (separate communities, that isn't just one big list of posts, that can be created by users)
- [ ] User notifications
- [ ] User private messaging
- [ ] User blocking
- [ ] User following
- [ ] User feed (posts from users you follow)
- [ ] User flair

## (Required)

🎯 Please mention the requirements you met and which goals you achieved for this assignment.
🎯 Were there any requirements or goals that you were not quite able to achieve?
🎯 If so, could you please tell us what was it that you found difficult about these tasks?

## (Optional)

🏹 Feel free to add any other reflections you would like to share about your submission e.g.

What went really well and what could have gone better?
Detailing useful external sources that helped you complete the assignment (e.g Youtube tutorials).
Describing errors or bugs you encountered while completing your assignment.
Requesting feedback about a specific part of your submission.

## Fixes & Feature Requests (Stretch goals)

- [x] Fix page titles on post pages to match the post title
- [x] Handle the error when you click to vote while not logged in to show a nice error message
- [ ] Try to make it so I can't vote more than once (Fix could be done in the SQL with the constraints (ideally), or in-app code to check the db before adding a new row to the votes table)
- [ ] Users would like a richer editing experience we'd like to incorporate TipTap (based on Prosemirror)
      TipTap introduction
      TipTap Next.js setup guide
- [ ] Users can vote an infinite number of times on the same post. We'd like to prevent this happening. It should be enforced at the Schema level with the UNIQUE constraint but it isn't working. We'd like you to try and fix this, either by correcting the schema (preferable) or if not by implementing the restriction in the application code when the user tries to upvote.

## My Experience

- I struggled to connect to Git, I had to try it a few different ways until it eventually worked
- I then redid the project a few times becuase of it and undid some changes and confused myself
- Then after deploying to Vercel I forgot to redeploy after changing my env variables.
- oh and I didnt notice env.example _how embarrassing - crawls into hole and hides_
