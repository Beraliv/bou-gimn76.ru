# bou-gimn76 backend

This is open-source headless CMS.

Link 🔗 – https://bou-gimn76.herokuapp.com/admin/

## Getting started

1. Install dependencies

```bash
yarn
```

2. Create `.env` file based on the [`.env.example`](/backend/.env.example):

```bash
HOST=0.0.0.0
PORT=1337
APP_KEYS="toBeModified1,toBeModified2"
API_TOKEN_SALT=tobemodified
ADMIN_JWT_SECRET=tobemodified
JWT_SECRET=tobemodified
```

3. Run dev server

```bash
yarn develop
```

## Deployment

1. Create `.git` project with backend only:

```bash
cd backend
git init
git add .
git commit -m "Initial Commit"
```

2. Create Heroku project:

```bash
# New project
heroku create

# Connect to existing project
heroku git:remote -a <your-heroku-app-name>
```

3. Set up Postgres in Heroku:

```bash
heroku addons:create heroku-postgresql:hobby-dev
```

4. Set config data for Postgres:

```bash
# Use ./config/env/production/database.ts instead of ./config/database.ts
heroku config:set NODE_ENV=production

# Use your .env to set it in Heroku
heroku config:set MY_HEROKU_URL=$(heroku info -s | grep web_url | cut -d= -f2)
heroku config:set APP_KEYS=$(cat .env | grep APP_KEYS | cut -d= -f2-)
heroku config:set API_TOKEN_SALT=$(cat .env | grep API_TOKEN_SALT | cut -d= -f2)
heroku config:set ADMIN_JWT_SECRET=$(cat .env | grep ADMIN_JWT_SECRET | cut -d= -f2)
heroku config:set JWT_SECRET=$(cat .env | grep -w JWT_SECRET | cut -d= -f2)
```

5. Deploy

```bash
git push heroku HEAD:main
```

## Technologies:

- [Strapi](https://github.com/strapi/strapi) – admin panel
- [sqlite](https://www.sqlite.org/index.html) - SQL DB for local development
- [Postgres](https://www.postgresql.org/about/) - Relative SQL DB for production
- [Heroku](https://www.heroku.com/about) - Deploy, manage and scale apps
