# Footprints.

[![Code Climate](https://codeclimate.com/github/HoracioChavez/footprints/badges/gpa.svg)](https://codeclimate.com/github/HoracioChavez/footprints)

Feel free to visit the live project <a href="http://h6c5.com/footprints" target="_blank">here</a>.  
Please keep in mind this App was designed only for mobile.
### What is this WebApp for?

Designed for mobile, this WebApp allows users to create trips while aggregates social media posts using Twitter and Instagram OAuth.

<p align="center"><img src="http://h6c5.com//system/pictures/images/000/000/002/original/output_LPUJb3.gif?1418083569">
</p>
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

Please read the full "Ignition instructions" before start typing.

**Ignition instructions.**

To start, you have to run the server. I'm using `rails server`, but you can use your favourite server ( i.e. unicorn ). Just be sure you're using port 3000 ( i.e. `unicorn -p 3000` ).  

At the same time you should have running `sidekiq` and `redis-server`.

To achieve that, you can have three tabs in your terminal, and run the following commands in each of those.  

\* As a requirements reminder, you need to have redis and sidekiq installed.

First tab: `rails s`  

Second tab: `redis-server`  

Third tab: `sidekiq`

![](http://h6c5.com//system/pictures/images/000/000/001/original/Screen_Shot_2014-12-02_at_2.13.13_PM.png?1417554849)

End of the Ignition instructions.  

**How to enjoy footprints**

Go to `localhost:3000` in your browser, and click "Sign in with Instagram".  The first time is going to redirect you to instagram, and then to Footprints. You should have an Instagram account to use Footprints.

Congrats! Now you're in Footprints!

There are some cool features, like:

* Create (CRUD) trips.
  * A trip is created using your posts from Twitter and Instagram.
  * A trip is going to include every post inside the duration of the trip.
  * Footprints only pulls the latest 20 posts from your Instagram/Twitter accounts. Please consider this when you define your trip's duration.


* Add friends to your trips.
  * If you to one of your trips feed, and scroll a little, you're going to find the "Add a friend..." input.
  * You can add any footprints user into your trip.
  * You can add as many users as you want, but one by one.
  * After you add friends to your trip, their posts are going to be in this trip with your own posts.  
<br>
* Hide/Show posts.
  * If there is a post from your Twitter/Instagram accounts that you don't want to include in your trips, you can hide it.
  * To hide a post, go to the right post and then click on "Hide Your Post".
  * To revert this action, a.k.a. to show the post again, click on the gear in the top navigation bar, and the select "Hidden posts".
  * Once your founded the right post, just click on "Show your post". Now this post is going to be available again in all your trips.


### The Team.

We developed this project pairing extensively as part of the <a href="http://turing.io/" target="_blank">Turing School</a> curriculum based on this <a href="http://tutorials.jumpstartlab.com/projects/feed_engine/feed_engine.html" target="_blank">requirements</a>.
