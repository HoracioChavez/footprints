# Footprints.
### A social media aggregator to create trips with your friends.

[![Code Climate](https://codeclimate.com/github/HoracioChavez/footprints/badges/gpa.svg)](https://codeclimate.com/github/HoracioChavez/footprints) 

You can visit the [live app here](http://h6c5.com/footprints) and also this content as part of my [portfolio](http://h6c5.com/horaciochavez).

### What is this web app for?
#### Get posts from social media to create albums by dates range.

Footprints synchronizes posts across your/your friends' tweets and instagram posts to create trips/albums by a date range. It's much better than having those posts in every network, because it's easiest for users to keep their memories in one place. Footprints is kind of like taking the best elements from iPhoto, Twitter, Instagram and GoogleMaps. People have access to these tools, but they need to make an extra big effort to achieve it. 

## Technical requirements.
#### Rails + PostgreSQL + Redis + Sidekiq.

This was builded over Ruby version 2.1.2 and Rails 4.1.6. It was never tested with any other version. You will need to have installed PostgreSQL, Redis and Sidekiq.

Also, you will require an [instagram](http://instagram.com) account to use footprints.

## How to install.
#### Git Clone + Bundle + Rake + Figaro + Tokens.

To start, you need to clone the project to your local machine, install all the required gems and create the database and tables.

```bash
git clone git@github.com:HoracioChavez/footprints.git
bundle install
rake db:create db:schema:load
```

Now you have figaro in your system, but you need to install it.

```bash
figaro install
```

Figaro created a `config/application.yml` file. There you have to include some social network tokens. For security reasons, I'm not sharing my personal tokens here, and neither should you . To do create your own tokens, please go to [Instagram Developers](http://instagram.com/developer/) and [Twitter Application Managment](https://apps.twitter.com).

Once you have the tokens, fill your `config/application.yml` file to look like this. 
Of course, instead of the x's should be your tokens.

```ruby
INSTAGRAM_ID: 'xxxxxx'
INSTAGRAM_SECRET: 'xxxxxx'
TWITTER_ID: 'xxxxxx'
TWITTER_SECRET: 'xxxxxx'
```
Congrats! Now you have footprints completely installed in your system.

## How to run the app.
#### Server + Redis + Sidekiq.

To start, you have to run the server. Here, I'm using `rails server`, but you can use your favourite server ( i.e. unicorn ). Just be sure you're using port 3000 ( i.e. `unicorn -p 3000` ).  

At the same time you should have running `sidekiq` and `redis-server`.

To achieve that, you can have three tabs in your terminal, and run the following commands in each of those.  

\* As a requirements reminder, you need to have redis and sidekiq previously installed.

First tab: `rails s`, second tab: `redis-server` and third tab: `sidekiq`.

![](http://h6c5.com//system/pictures/images/000/000/001/original/Screen_Shot_2014-12-02_at_2.13.13_PM.png?1417554849)

## How to enjoy footprints.
#### Have friends and travel a lot!

In your mobile browser, go to `localhost:3000`, and click "Sign in with Instagram".  Footprints is going to redirect you to instagram, and then back to Footprints. **You should have an Instagram account to use Footprints.**

##### Congrats! Now you're in Footprints!

These are some cool features.

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

##The team.
#### Cool people build cool products.

Developed during almost 3 weeks and in team of four, footprints was a communication and pair programming success. I really enjoyed working with [Marc Garreau](https://github.com/MarcGarreau), [Emily Davis](https://github.com/emilyadavis303) and [Tim Proctor](https://github.com/timproctor). 

##### Great communication and daily stand-up meetings were key to the success of this project. 
