# Project tips


Voici un répertoire des atuces pour que les petits détails de votre projet ne soient plus un souci !


**1. Faire disparaître la barre d'alerte au bout de 3 secondes automatiquement**


```javascript
// app/javascript/pack/application.js

$(".alert" ).delay(2000).fadeOut(1000);
$(".alert-success" ).delay(2000).fadeOut(1000);
$(".alert-danger" ).delay(2000).fadeOut(1000);
```

**2. Faire en sorte que votre footer reste en bas de votre page peu importe la longueur du contenu**


```html
<!-- app/views/layouts/application.html.erb -->

 <body>
  <%= render 'shared/navbar' %>
  <%= render 'shared/flashes' %>
  <div class="section">
    <%= yield %>
  </div>
  <%= render 'shared/footer' %>
 </body>
```

```css
/* app/assets/stylesheets/ */

.section {
  margin-top: 50px; /* Hauteur de la navbar */
  min-height: calc(100vh - 100px); /* Hauteur totale - (Hauteur navbar + Hauteur footer) */
}
```
