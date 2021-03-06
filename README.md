# Reactive programing workshop

## Presentation

- [Sliders A](https://es.slideshare.net/alexandermostovenko/odessa-rx)
- [Sliders B](https://es.slideshare.net/MarianoGermnVillarre/rx-js-82776674)

## Challenge

Get real-time monitoring of the feedback received by social networks.

So that every time you get data from social networks, the real-time report is updated showing the number of happy users and not happy users

For each new event broadcast by social networks the report has to be updated

## Result

```javascript
{
    happyUsers: 1000,
    unhappyUsers: 2
}
```

## Providers data structure

facebook:

```javascript
{
    user             : 'Ahmad',
    picture          : 'http://lorempixel.com/640/480/people',
    post             : 'Mollitia doloribus maxime.',
    positiveFeedback : false,
    provider         : 'facebook'
}
```

twitter:

```javascript
{
    user_name         : 'Boris',
    profile_image     : 'http://lorempixel.com/640/480/people',
    twit              : 'Quaerat dicta iusto consequatur ex repellendus necessitatibus.',
    positive_feedback : true,
    provider          : 'twitter'

}
```

instagram

```javascript
{
    name      : 'Alivia',
    portfolio : [
        'http://lorempixel.com/640/480/cats',
        'http://lorempixel.com/640/480/people',
        'http://lorempixel.com/640/480/fashion',
        'http://lorempixel.com/640/480/food'
    ],
    lifeStyle : 'Dolore aut unde aut recusandae facilis consequatur.',
    feedback  : true,
    provider  : 'instagram'
}
```

## Providers interface

```javascript
const providers = require("../src/providers")

const facebook = providers.facebook({ rate: 300 })
const twitter = providers.twitter({ rate: 300 })
const instagram = providers.instagram({ rate: 300 })

facebook.on("post", console.log)
twitter.on("twit", console.log)
instagram.on("hipster", console.log)

setTimeout(() => facebook.close(), 2000)
setTimeout(() => twitter.close(), 2000)
setTimeout(() => instagram.close(), 2000)
```
