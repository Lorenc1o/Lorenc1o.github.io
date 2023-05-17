---
layout: home
---

Hello, I think my name is already too many times in this website, so I will skip that part. Here you will find my [blog posts](/blog) and [projects](/projects).

You will find information and insights about different topics here, specially about data science, machine learning, mathematics, programming, and other topics that I find interesting, funny, or even both.

<script>
window.onload = function() {
    fetch('https://v2.jokeapi.dev/joke/Any?type=single?blacklistFlags=nsfw,racist,sexist,explicit')
        .then(response => response.json())
        .then(data => {
            document.getElementById('joke').textContent = data.joke;
        });
};
</script>

Now a joke for you[^1]:

<p id="joke"></p>

## About me

My education and experience are explained in the [about](/about) section. Here I will talk about myself, my hobbies, and my interests.

I come from Cehegín, a small town in Murcia, in the south of Spain. I have lived there for most of my life, and I have very good memories from my childhood and teenage years and most of the important people in my life are there. I moved to Murcia in 2017 to study and nowadays I am living in different places, since my current Master's degree is a joint degree between several european universities.

Usually, I use this photo as my profile picture, since it looks professional and I look good enough in it:

<img src="/assets/images/me/me.png" alt="A picture of me." width="100" class="centered-image">

But there is much more of me than this. I am sharing here some pictures with important people in my life. This is me with my mother when I was younger:

<img src="/assets/images/me/me-and-mum.jpg" alt="A picture of me with my mother." width="300" class="centered-image">

This is me with my father and my brother, a snow day in 2016:

<img src="/assets/images/me/me-jp-dad.jpg" alt="A picture of me with my family." width="300" class="centered-image">

This one is a recent one, with my girlfriend, Lorena, who is a very important person in my life. We took this picture in Parque de la Ciudadela, Barcelona:

<img src="/assets/images/me/me-lore.jpg" alt="A picture of me with my girlfriend." width="300" class="centered-image">

Finally, this is me with my friends at a Christmas party in our home town:

<img src="/assets/images/me/me-and-friends.jpg" alt="A picture of me with my friends." width="300" class="centered-image">

[^1]: Disclaimer: Joke provided by [jokeAPI](https://sv443.net/jokeapi/v2/).
