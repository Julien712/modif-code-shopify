## Mettre un hover sur la nav

Ajouter le code dessous dans `header.liquid` entre :

`</header> </{% if section.settings.sticky_header_type != 'none' %}sticky-header{% else %}div{% endif %}>`
```html
<script>
  let items = document.querySelector(".header__inline-menu").querySelectorAll("details");
  console.log(items)
  items.forEach(item => {
    item.addEventListener("mouseover", () => {
      item.setAttribute("open", true);
      item.querySelector("ul").addEventListener("mouseleave", () => {
        item.removeAttribute("open");
      });
    item.addEventListener("mouseleave", () => {
      item.removeAttribute("open");
    });
  });
  
  });
</script>
```
et :
`{%- if settings.cart_type == "notification" -%}`

## Désactiver la pause sur le carrousel

Supprimer ces lignes dans `global.js` en cherchant `SlideshowComponent` : 

![screenshot](https://github.com/Julien712/modif-code-shopify/screenshot.png)
