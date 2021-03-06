---
title: Crear una insignia personalizada para tu GitHub App
intro: '{% data reusables.shortdesc.creating_custom_badges_github_apps %}'
redirect_from:
  - /apps/building-github-apps/creating-custom-badges-for-github-apps
  - /developers/apps/creating-a-custom-badge-for-your-github-app
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
topics:
  - GitHub Apps
shortTitle: Insignias personalizadas
---

Predeterminadamente, una GitHUb App tendrá un [identicon](https://github.com/blog/1586-identicons) generado automáticamente. Una insignia de identicon se ve más o menos así:

![Identicon](/assets/images/identicon.png)

Después de crear una GitHub App, puedes personalizar la insignia de tu app si subes un logo y seleccionas un color de fondo. Una insignia es una imagen de logo cuadrado dentro de una insignia circular. Puedes escoger un color de fondo para la insignia, el cual puede distinguir visualmente a tu app.

Tu logo debe ser un archivo en PNG, JPG, o GIF de menos de 1 MB de tamaño. Para obtener la mejor calidad, te recomendamos un tamaño de por lo menos 200px x 200px. {% ifversion fpt %}Consulta la sección "[Tips para las imagenes de logos e insignias](/marketplace/listing-on-github-marketplace/writing-github-marketplace-listing-descriptions/#guidelines-for-logos)" para obtener lineamientos adicionales sobre la personalización de insignias.{% endif %}

{% ifversion fpt %}

Puedes cambiar una insignia personalizada para una GitHub App que ya tenga una lista de Marketplace aprobada si navegas a https://github.com/marketplace/manage.

{% endif %}

Para crear una insignia personalizada:

{% data reusables.user-settings.access_settings %}
{% data reusables.user-settings.developer_settings %}
{% data reusables.user-settings.github_apps %}
{% data reusables.user-settings.modify_github_app %}
5. En "Mostrar información", arrastra y suelta una imagen de una carpeta local, o da clic en **Cargar un logo** para seleccionar una imagen de tu ordenador. ![Cargar un logo](/assets/images/github-apps/github_apps_upload_logo.png)
6. Recorta tu imagen. Cuando termines, da clic en **Confirmar avatar nuevo**. ![Cortar y confirmar logo ](/assets/images/github-apps/github_apps_crop_and_set_avatar.png)
7. En "Color de fondo de la insignia", teclea el [código hexadecimal de color](http://www.color-hex.com/) para el color de fondo de tu insignia. {% ifversion fpt %}**Nota:** El campo de ingreso para el "Color de fondo de la insignia" únicamente aparecerá después de que cargues un logo para la aplicación.{% endif %} ![Color de fondo de la insignia](/assets/images/github-apps/github_apps_badge_background_color.png)

{% ifversion fpt %}

## Pasos siguientes

Para obtener más información acerca de cómo crear un listado de Marketplace para esta app, consulta la sección "[Listados en GitHub Marketplace](/marketplace/listing-on-github-marketplace/)".

{% endif %}
