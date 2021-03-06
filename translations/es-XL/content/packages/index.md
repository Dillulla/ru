---
title: Documentación de GitHub Packages
shortTitle: Paquetes de GitHub
intro: 'Aprende a publicar y consumir paquetes de forma segura, almacena tus paquetes junto con tu código y comparte tus paquetes de forma privada con tu equipo o de manera pública con la comunidad de código abierto. También puedes automatizar tus paquetes con {% data variables.product.prodname_actions %}.'
featuredLinks:
  guides:
    - /packages/learn-github-packages
    - /packages/managing-github-packages-using-github-actions-workflows
    - /packages/learn-github-packages/installing-a-package
  popular:
    - /packages/working-with-a-github-packages-registry/working-with-the-npm-registry
    - '{% ifversion fpt %}/packages/working-with-a-github-packages-registry/working-with-the-container-registry{% else %}/packages/working-with-a-github-packages-registry/working-with-the-docker-registry{% endif %}'
    - /packages/learn-github-packages
    - /packages/working-with-a-github-packages-registry/working-with-the-apache-maven-registry
  guideCards:
    - '{% ifversion fpt %}/packages/working-with-a-github-packages-registry/working-with-the-container-registry{% else %}/packages/working-with-a-github-packages-registry/working-with-the-docker-registry{% endif %}'
    - /packages/working-with-a-github-packages-registry/working-with-the-rubygems-registry
redirect_from:
  - /github/managing-packages-with-github-packages
  - /categories/managing-packages-with-github-package-registry
  - /github/managing-packages-with-github-package-registry
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
introLinks:
  quickstart: /packages/quickstart
  reference: /packages/manage-packages
changelog:
  label: packages
  prefix: 'Packages: '
layout: product-landing
children:
  - /quickstart
  - /learn-github-packages
  - /working-with-a-github-packages-registry
  - /managing-github-packages-using-github-actions-workflows
---
{% data reusables.package_registry.packages-ghes-release-stage %}
