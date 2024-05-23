# Dev Wave

## App Data:

- A Social media Web Application Developed using MERN Stack.
- A Social Network app for developers that includes authentication, profiles and forum posts.
- An user can create an account and develop their profile.
- User can also check the profiles and posts of the other developers who are on this network.
- This appilication contains 4 main Routes *Auth, User, Profile, Posts*.

## Technologies Used

- **Backend:** Node.js and Express.js
- **Database:** MongoDB
- **Frontend:** React.js, React-Redux

## Authors:

* **Uppalapati Suchith Chowdary**

# Quick Start 🚀

### Add a default.json file in config folder with the following

```json
{
  "mongoURI": "<your_mongoDB_Atlas_uri_with_credentials>",
  "jwtSecret": "secret",
  "githubToken": "<yoursecrectaccesstoken>"
}
```

### Install Server dependencies

```bash
npm install
```

### Install Client dependencies

```bash
cd client
npm install
```

### Run both Express & React in root

```bash
npm run dev
```

### Build for production

```bash
cd client
npm run build
```

### Test production before deploy

After running a build in the client 👆, cd to the **root** of the project.
And run...

**Linux/Unix**

```bash
NODE_ENV=production node server.js
```

**Windows** Cmd Prompt or Powershell

```bash
$env:NODE_ENV="production"
node server.js
```

Check in browser on [http://localhost:5000/](http://localhost:5000/)

### Deploy to Heroku

If you followed the sensible advice above and included `config/default.json` and `config/production.json` in your .gitignore file, then pushing to Heroku will omit your config files from the push.
However, Heroku needs these files for a successful build.
So how to get them to Heroku without commiting them to GitHub?

I suggest you to create a local only branch, let it be ***Production.***

**Move to the Branch - Production**

```bash
git checkout -b production
```

We can use this branch to deploy from, with our config files.

**Add config file**

```bash
git add -f config/production.json
```

This will track the file in git on this branch only. 

**DO NOT PUSH THE PRODUCTION BRANCH TO GITHUB**

**Commit**

```bash
git commit -m 'ready to deploy'
```

**Create Heroku Project**

```bash
heroku create
```

**Push *Local Production* Branch to Remote *Heroku Main* Branch.**

```bash
git push heroku production:main
```

Now Heroku will have the config it needs to build the project.

> **Don't forget to make sure your production database is not whitelisted in MongoDB Atlas, otherwise the database connection will fail and your app will crash.**

After the deployment you can delete the production branch if you like.

This is completely Optional.

```bash
git checkout main
git branch -D production
```

Or you can leave it to merge and push updates from another branch.

Make any changes you need on your main branch and merge those into your production branch.

```bash
git checkout production
git merge main
```

Once merged, **Push to Heroku** as above and the **site** will be **Rebuilt** and get **Updated.**

---
