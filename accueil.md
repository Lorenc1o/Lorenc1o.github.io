---
layout: home
lang: fr
permalink: /accueil
es_link: /inicio
en_link: /
---

Bonjour, je pense que mon nom est déjà trop de fois sur ce site, donc je vais sauter cette partie. Ici vous trouverez mes [articles](/blog) et [projets](/projects).

Vous trouverez des informations et des idées sur différents sujets ici, en particulier sur la science des données, l'apprentissage automatique, les mathématiques, la programmation et d'autres sujets qui m'intéressent, qui me font rire, ou même les deux.

<script>
window.onload = function() {
    fetch('https://v2.jokeapi.dev/joke/Any?blacklistFlags=nsfw,religious,political,racist,sexist,explicit&type=single')
        .then(response => response.json())
        .then(data => {
            document.getElementById('joke').textContent = data.joke;
        });
};
</script>

Ici, une blague pour vous[^1] (an anglais, désolé):

<p id="joke"></p>

## À propos de moi

Mon éducation et mon expérience sont expliquées dans la section [about](/about). Ici, je vais parler de moi, de mes passe-temps et de mes intérêts.

Je viens de Cehegín, une petite ville de Murcie, dans le sud de l'Espagne. J'y ai vécu la plupart de ma vie, et j'ai de très bons souvenirs de mon enfance et de mon adolescence et la plupart des personnes importantes de ma vie sont là-bas. Je suis allé à Murcie en 2017 pour étudier et aujourd'hui je vis dans différents endroits, car mon Master actuel est un Master conjoint entre plusieurs universités européennes.

Normalement, j'utilise cette photo comme photo de profil, car elle a l'air professionnelle et je m'y trouve assez bien:

<img src="/assets/images/me/me.png" alt="A picture of me." width="100" class="centered-image">


Mais il y a beaucoup plus de moi que ça. Je partage ici quelques photos avec des personnes importantes de ma vie. C'est moi avec ma mère quand j'étais plus jeune:

<img src="/assets/images/me/me-and-mum.jpg" alt="A picture of me with my mother." width="300" class="centered-image">

C'est moi avec mon père et mon frère, un jour de neige en 2016:

<img src="/assets/images/me/me-jp-dad.jpg" alt="A picture of me with my family." width="300" class="centered-image">

Cette photo est plus récente, avec ma copine, Lorena, qui est une personne cruciale dans ma vie. Nous avons pris cette photo au Parque de la Ciudadela, à Barcelone:

<img src="/assets/images/me/me-lore.jpg" alt="A picture of me with my girlfriend." width="300" class="centered-image">

Finalement, laissez-moi vous présenter certains de mes amis. C'est moi avec mes amis lors d'une fête de Noël dans notre ville natale:

<img src="/assets/images/me/me-and-friends.jpg" alt="A picture of me with my friends." width="300" class="centered-image">

Et c'est moi avec certains de mes amis de Murcie, qui sont venus me rendre visite à Bruxelles quand j'étudiais là-bas:

<img src="/assets/images/me/me-friends-bruxelles.jpg" alt="A picture of me with my friends from Murcia." width="300" class="centered-image">

Vous pouvez vous sentir le froid sur la photo, non?

[^1]: Clause de non-responsabilité: Blague fournie par [jokeAPI](https://sv443.net/jokeapi/v2/).
