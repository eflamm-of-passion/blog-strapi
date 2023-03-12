# Deploy Strapi to Render

This is a sample [Strapi](https://strapi.io/) app, configured for deployment to [Render](https://render.com). It uses a [managed PostgreSQL database](https://render.com/docs/databases) to store structured content and a [persistent disk](https://render.com/docs/disks) to store uploaded Media Library files.

See the guide at https://render.com/docs/deploy-strapi for more information.

I changed the render.yaml to start the instance on the free tier, as I didn't want to pay anything.

## Troubleshoot

### The create new content type does not appear

This button is not available on production mode because is modifies the code. So you have to launch the project on development mode to see it appear. But I was not able to launch it with this mode on Render, so I had to do that on local.

### Create table error while trying to add new content type

I had an error when I added a new content type and tried to deploy on Render. It said `error create table [...] duplicate constraint violated`. I didn't understand why it happened, but the solution was to connect on the Postgres database and execute the create table request myself, then redeploy.
