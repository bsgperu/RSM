# RSM (Routing - Scheme - Manager)
Este repositorio presenta un nuevo patrón de diseño desarrollado por **Percy Alexander Caballero Lucano** con el patrocinio de **BSG Perú**.
**RSM** es un patron de diseño jerarquizado que prioriza la seguridad del software.

## 🚀 Descripción

El patrón RSM (Routing - Scheme - Manager / Enrutamiento - Esquema - Gestor), es una nueva forma de estructurar la logica de un proyecto sea Web o Escritorio en el cual busca implementar software en base a su funcionamiento y aumentar la seguridad y claridad de los mismos.​

En **RSM** se plantea que el codigo sea totalmente propio para evitar contaminacion externa de la aplicacion y con ello vulnerar la aplicacion o la infraestructura del negocio.

Por ello el patron de diseño cuenta con 3 tipos segun sus complementos, Propios **(a)**, De Terceros **(b)** y Mixto **(c)**.

Existe la posibilidad de reducir el Patron **RSM** y este se puede representar de 2 formas:
**RSM r1** : Variante que utiliza varios archivos los cuales cada uno cumple la funcion de un componente de **RSM**, pensado para Aplicaciones modulares y expandibles.

**RSM r2** : Variante que utiliza un unico archivo que cumple con todas las funciones de los componentes de **RSM**, pensado para Aplicaciones estaticas.

**RSM** fue desarrollado por Percy Alexander Caballero Lucano durante la inspeccion de un sistema en el cual la logica presentada era confusa y desordenada, para lo cual se procuro separar y jerarquizar la logica de la interfaz limitando el acceso a los recursos de la aplicacion solo a las clases de la misma aumentando la seguridad ya que solo existe una ruta de acceso al mismo. 

## 📝 Licencia

Este proyecto está licenciado bajo los términos de la [Licencia MIT](./LICENSE).

> El patrón de diseño descrito en este repositorio puede utilizarse, modificarse y distribuirse libremente, siempre que se otorgue el reconocimiento correspondiente al autor original: **Percy Alexander Caballero Lucano (2025)**, y se mencione el patrocinio de **BSG Perú**, cuando sea relevante.

## 📣 Reconocimiento

Agradecimientos a **BSG Perú** por el apoyo en el desarrollo de esta iniciativa.

---

© 2025 Percy Alexander Caballero Lucano
