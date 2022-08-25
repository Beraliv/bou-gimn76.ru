# bou-gimn76 backend

This is open-source headless CMS.

Link 🔗 – https://bou-gimn76.herokuapp.com/admin/

## Getting started

First, install all dependencies

```bash
yarn
```

To be able to run CMS, you need to create `.env` file based on the [`.env.example`](/backend/.env.example):

```bash
HOST=0.0.0.0
PORT=1337
APP_KEYS="toBeModified1,toBeModified2"
API_TOKEN_SALT=tobemodified
ADMIN_JWT_SECRET=tobemodified
JWT_SECRET=tobemodified
```

Then you need to run dev server:

```bash
yarn develop
```

## Technologies:

- [Strapi](https://github.com/strapi/strapi) – admin panel
- [sqlite](https://www.sqlite.org/index.html) - SQL DB for local development
- [Postgres](https://www.postgresql.org/about/) - Relative SQL DB for production
- [Heroku](https://www.heroku.com/about) - Deploy, manage and scale apps
