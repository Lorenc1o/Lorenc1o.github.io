---
layout: home
---

Hello, I think my name is already too many times in this website, so I will skip that part. Here you will find my [blog posts](/blog) and [projects](/projects).

You will find information and insights about different topics here, specially about data science, machine learning, mathematics, programming, and other topics that I find interesting, funny, or even both.

<script>
window.onload = function() {
    fetch('https://v2.jokeapi.dev/joke/Any?type=single')
        .then(response => response.json())
        .then(data => {
            document.getElementById('joke').textContent = data.joke;
        });
};
</script>

Now a joke for you[^1]:

<!-- Somewhere in your HTML body -->
<p id="joke"></p>

[^1]: Joke provided by [jokeAPI](https://sv443.net/jokeapi/v2/).