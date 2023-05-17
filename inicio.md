---
layout: home
lang: es
---

Hola, creo que mi nombre ya aparece demasiadas veces en esta página web, así que me lo voy a saltar. Aquí encontrarás mis [entradas de blog](/blog) y [proyectos](/projects).

Encontrarás información y reflexiones sobre diferentes temas aquí, especialmente sobre data science, machine learning, matemáticas, programación, y otros temas que me parecen interesantes, divertidos, o incluso ambos.

<script>
window.onload = function() {
    fetch('https://v2.jokeapi.dev/joke/Any?blacklistFlags=nsfw,religious,political,racist,sexist,explicit&type=single')
        .then(response => response.json())
        .then(data => {
            document.getElementById('joke').textContent = data.joke;
        });
};
</script>

Now a joke for you[^1]:

Aquí tienes un chiste[^1] (lo siento, está en inglés :():

<p id="joke"></p>

## About me

Mis estudios y experiencia están explicados en la sección [about](/about). Aquí hablaré sobre mí, mis hobbies, y mis intereses.

Soy de Cehegín, un pueblo pequeño en Murcia, en el sur de España. He vivido allí durante la mayor parte de mi vida, y tengo muy buenos recuerdos de mi infancia y adolescencia y la mayoría de las personas importantes en mi vida están allí. Me mudé a Murcia en 2017 para estudiar y actualmente estoy viviendo en diferentes lugares, ya que estoy estudiando un máster conjunto entre varias universidades europeas.

<img src="/assets/images/me/me.png" alt="A picture of me." width="100" class="centered-image">

Pero hay mucho más de mí que esto. Aquí comparto algunas fotos con personas importantes en mi vida. Esta soy yo con mi madre cuando era más joven:

<img src="/assets/images/me/me-and-mum.jpg" alt="A picture of me with my mother." width="300" class="centered-image">

Aquí estoy con mi padre y mi hermano, un día de nieve en 2016:

<img src="/assets/images/me/me-jp-dad.jpg" alt="A picture of me with my family." width="300" class="centered-image">

Esta es una foto reciente, con mi novia, Lorena, que es una persona muy importante en mi vida. Hicimos esta foto en el Parque de la Ciudadela, Barcelona:

<img src="/assets/images/me/me-lore.jpg" alt="A picture of me with my girlfriend." width="300" class="centered-image">

Por último, os presento a algunos de mis amigos. Este soy yo con mis amigos en una fiesta de Navidad en nuestro pueblo:

<img src="/assets/images/me/me-and-friends.jpg" alt="A picture of me with my friends." width="300" class="centered-image">

Y este soy yo con algunos de mis amigos de Murcia, que vinieron a visitarme a Bruselas cuando estaba estudiando allí:

<img src="/assets/images/me/me-friends-bruxelles.jpg" alt="A picture of me with my friends from Murcia." width="300" class="centered-image">

Se puede sentir el frío en la foto, ¿verdad?

[^1]: Exención de responsabilidad: Chiste proporcionado por [jokeAPI](https://sv443.net/jokeapi/v2/).
