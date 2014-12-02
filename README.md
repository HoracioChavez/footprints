# Footprints.

...I'm writing this Readme file.
Please come back on December 3rd, 2014...

Feel free to visit the live project [here](http://h6c5.com/footprints).

### What is this WebApp for?

Designed for mobile, this WebApp allows users to create trips while aggregates social media posts using Twitter and Instagram OAuth.

### Requirements.

This was builded over Ruby version 2.1.2 and Rails 4.1.6. It was not tested with any other version. Also, you need to have installed PostgreSQL, Redis and Sidekiq.

### How to install.  

To make this work, please:

1. Clone this repo.  
2. Install all the required gems.  
3. Create your database and required tables.

```
git clone git@github.com:HoracioChavez/footprints.git
bundle install
rake db:create db:schema:load
```

Now, you need to install Figaro.

```
figaro install
```

Figaro created `config/application.yml`there you have to include some tokens. For security reasons, I'm not sharing the tokens here, but you can create your owns. To do that, please go to [Instagram Developers](http://instagram.com/developer/) and [Twitter Application Managment](https://apps.twitter.com).

Once you have those tokens, just fill your `config/application.yml` to look like this. Of course, instead of the x's should be your tokens.
```
INSTAGRAM_ID: xxxxxxxxxxxxxxxxxxxxxxxxxx
INSTAGRAM_SECRET: xxxxxxxxxxxxxxxxxxxxxxxxxx
TWITTER_ID: xxxxxxxxxxxxxxxxxxxxxxxxxx
TWITTER_SECRET: xxxxxxxxxxxxxxxxxxxxxxxxxx
```
Now you're ready to go!

### Basics to use this app?

Please read the full "Ignition instructions" before start.

**Ignition instructions.**

To start, you have to run the server. I'm using `rails server`, but you can use your favourite server ( i.e. unicorn ). Just be sure you're using port 3000 ( i.e. `unicorn -p 3000` ).  

At the same time you should have running `sidekiq` and `redis-server`.

To achieve that, you can have three tabs in your terminal, and run the following commands in each of those.  

\* As a requirements reminder, you need to have redis and sideqik installed.

First tab: `rails server`  
Second tab: `redis-server`  
Third tab: `sideqik`  

![](http://h6c5.com//system/pictures/images/000/000/001/original/Screen_Shot_2014-12-02_at_2.13.13_PM.png?1417554849)

End of the Ignition instructions.  

**How to enjoy footprints**








### TL;DR
