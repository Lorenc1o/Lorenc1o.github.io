---
layout: home
lang: fr
permalink: /accueil
en_link: /
es_link: /inicio
---

<style>
.main-content {
  display: flex;
  align-items: flex-start;      /* pin to top so text height won’t shift avatar */
  justify-content: center;      /* center the whole block */
  padding: 40px 20px;
}

/* ⬇️ Center avatar + button under one another */
.main-content > div:first-child {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.profile-image {
  border-radius: 50%;
  width: 200px;                 /* smaller and balanced */
  height: auto;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  margin: 0 auto;
}

.download-cv {
  margin-top: 15px;
  display: inline-block;
  white-space: nowrap;
  padding: 10px 30px;
  background-color: #fff9e5;
  color: #000;
  border-radius: 6px;
  border: 1px solid #d0ac27;
  text-decoration: none;
  font-weight: bold;
  text-align: center;
}

.download-cv:hover {
  background-color: #d0ac27;
  color: #fff;
}

.profile-text {
  flex: 1;                      /* fill remaining space */
  max-width: 700px;             /* limit line-length */
  margin: 0 20px;               /* gap from avatar */
  font-size: 1.15em;
  line-height: 1.6;
  color: #333;
}

@media (max-width: 768px) {
  .main-content {
    flex-direction: column;
    align-items: center;
    text-align: center;
  }
  .profile-text {
    margin: 20px 10px 0;
    padding: 0;
  }
}
</style>

<div class="main-content">
  <div>
    <img src="/assets/images/me/me.png" alt="Photo de moi" class="profile-image">
    <a href="/assets/files/cv_JoseAntonioLorencio.pdf" class="download-cv" target="_blank">Télécharger le CV</a>
  </div>
  <div class="profile-text">
    <p><strong>Chercheur quantitatif</strong> diplômé en Mathématiques et Informatique, avec un master Erasmus Mundus en Big Data (moyenne : 18,5/20, Prix du Meilleur Dossier Académique).</p>
    <ul style="padding-left: 20px; list-style-type: disc; line-height: 1.6;">
      <li>Développement de modèles haute performance en Python et C++ pour la prévision, la simulation et la robustesse en apprentissage automatique.</li>
      <li>Expertise en séries temporelles, apprentissage fédéré et attaques adversariales.</li>
      <li>Actuellement à la recherche d’un poste en finance quantitative alliant modélisation mathématique, optimisation et apprentissage statistique.</li>
    </ul>
  </div>
</div>
