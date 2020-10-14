# Harrison's Climbing App

This [live web application](https://harrisonized-climbing-app.herokuapp.com/) is a dashboard that executes SQL queries on data stored in a [Heroku Postgres](https://devcenter.heroku.com/articles/heroku-postgresql) database, then uses that data to create interactive visualizations using [Plotly](https://plotly.com/python/). If the data cannot be retrieved from the postgres database, this app will instead use data from [CSV](https://github.com/harrisonized/harrisonized-climbing-app/tree/master/data) files. Once the visualizations are created, this app caches them as JSON files saved in `/tmp`, which is Heroku's ephemeral file storage system. Refreshing the page will result in the figure being read directly from the saved files rather than being regenerated from the data. Everything takes place on the server side.

Note that Heroku may take up to 30 seconds to come out of a sleeping website state.

Here are some of the latest updates in reverse-chronological order:

1. Add logic to preferentially get data from Postgres database, then use the data from CSV files if Postgres is unavailable.
2. Create Heroku Postgres database and swap out datasource from CSV files to newly created database
3. Add an auth module to encrypt database URIs and unit test for database connections
4. Add figure caching

 Future goals I have for this app are:

1. Improve the look and feel of the Home page
3. Add drop-downs or menus for selecting figures on the Figure pages.
