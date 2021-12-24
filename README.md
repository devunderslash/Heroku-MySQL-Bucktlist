# Simple REST API for Deployment to Heroku with MSQL

The following web-app was built following guidance from the following article: [Deploying a Java Rest API to Heroku](https://dzone.com/articles/create-and-publish-your-rest-api-using-spring-boot). To test locally follow the instructions in the article.

You will need a Heroku account to run the web-app and you can create one here: [https://www.heroku.com/signup](https://www.heroku.com/signup). Once you have created the app you can run the following commands to log into Heroku and deploy the web-app:
```
    heroku login
    heroku create
```
You will need to have a credit/debit card linked to Heroku to avail of the free add-ons for this. To start up the DB on Heroku:
```
    heroku addons:create cleardb:ignite
```
To get your connection string and update the `spring.datasource.url` in application properties with the value that is returned from the command:
```heroku config```

You can then push it to Heroku with the following command:
```
    git push heroku master
```

Once it has been deployed you will need to run the following to run your app `heroku ps:scale web=1` to scale the web-app to 1 instance. Then you can access and update it via commands to Postman or a similar tool.

Accessing the URL provided by Heroku will perform a GET request to the root of the web-app.