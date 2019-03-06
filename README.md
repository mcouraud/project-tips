# Project tips


Voici un répertoire des atuces pour que les petits détails de votre projet rails ne soient plus un souci !


### Faire disparaître la barre d'alerte de manière automatique


```javascript
// app/javascript/pack/application.js

$(".alert" ).delay(2000).fadeOut(1000);
$(".alert-success" ).delay(2000).fadeOut(1000);
$(".alert-danger" ).delay(2000).fadeOut(1000);
```

### Faire en sorte que votre footer reste en bas de votre page peu importe la longueur du contenu

Il faut ajouter une div (id="section") autour de votre contenu (yield) et vérifer que navbar / alerts / footer restent à l'exterieur de cette nouvelle div. 

```html
<!-- app/views/layouts/application.html.erb -->

 <body>
  <%= render 'shared/navbar' %>
  <%= render 'shared/flashes' %>
  <div id="section">
    <%= yield %>
  </div>
  <%= render 'shared/footer' %>
 </body>
```
Puis ajouter la taille souhaitée à la div.
```css
/* app/assets/stylesheets/layouts/_section.scss */

#section {
  margin-top: 50px; /* Hauteur de la navbar */
  min-height: calc(100vh - 100px); /* Hauteur totale - (Hauteur navbar + Hauteur footer) */
}
```

### Stockez vos couleurs dans des variables css dès le départ

```scss
/* app/assets/stylesheets/config/_colors.scss */

$red:  #E0442C;
$green: #6AD8A5;
$gray: #3A4247;
$light-gray: #D3CFD5;
$white: #F9F8F8;
```
Ceci vous permettra de les utiliser dans tous les fichiers css de votre projet sans avoir à récuperer, toutes les 5 minutes, le code couleur dont vous avez besoin.
```css
/* app/assets/stylesheets/components/_buttons.scss */

.btn-green {
  text-align: center;
  color: $white !important;
  background-color: $green;
  padding : 8px;
  border-radius: 8px;
}
```
