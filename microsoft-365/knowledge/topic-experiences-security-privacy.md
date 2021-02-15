---
title: Seguridad y privacidad de Microsoft Viva Topics
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye, cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Obtenga información sobre cómo planear la seguridad y privacidad de Los temas de Microsoft Viva
ms.openlocfilehash: be5be01bce117a80bd95ee268c193889eccea67f
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107797"
---
# <a name="microsoft-viva-topics-security-and-privacy"></a>Seguridad y privacidad de Microsoft Viva Topics

Los temas usan las características de seguridad de contenido existentes en Microsoft 365, junto con los controles administrativos, para controlar qué contenido generado por IA se muestra a los usuarios de su organización. Es la combinación de la configuración de seguridad de Microsoft 365 (permisos para sitios, archivos y carpetas) y la configuración de administración de temas que determinan lo que un usuario determinado puede ver en los temas.

La configuración de temas no modifica ningún control de acceso existente en el contenido de la organización. Los usuarios solo verán a lo que ya tienen acceso.

En este artículo se describe cómo funcionan los temas desde una perspectiva de seguridad y las opciones que los administradores de conocimientos y los administradores de conocimientos tienen para controlar la visibilidad de los temas. Lea este artículo como parte de la [planeación de temas.](plan-topic-experiences.md)

Debe estar familiarizado con [los](topic-experiences-overview.md) [](topic-center-overview.md)temas que son, el centro de temas y cómo trabajar con los temas del centro de temas [antes](manage-topics.md) de leer este artículo.

## <a name="what-users-can-see-in-topics"></a>Lo que los usuarios pueden ver en los temas

Para ver temas, un usuario debe:

- Tener una licencia de Temas de Viva
- Ser un visor [de temas,](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization) [colaborador o administrador de conocimientos](topic-experiences-user-permissions.md)

Estos dos aspectos permiten a los usuarios ver el acceso al centro de temas y permitirles ver las tarjetas de tema y los resaltados.

Además, los colaboradores de [temas](topic-experiences-user-permissions.md) tienen permisos de creación y edición para los temas, y los administradores de conocimientos pueden confirmar o quitar temas.

Cuando se detecta un tema por primera vez, los administradores de conocimientos pueden verlo en el centro de temas. Según la integridad y relevancia del tema, los visores de temas pueden o no ver el tema presentado en las tarjetas de tema.

Los temas pueden contener información generada por IA e información agregada o editada por colaboradores de temas o administradores de conocimientos.

- La información de un tema que AI agregó solo es visible para las personas que tienen acceso al contenido de origen.
- El texto que un colaborador o un administrador de conocimientos ha agregado o editado manualmente es visible para todos los usuarios que puedan ver el tema.

Los lectores y colaboradores del tema pueden ver la lista de temas confirmados y publicados en el centro de temas, pero los detalles del tema que una persona determinada puede ver dependen de los permisos que tienen para el material de origen y de si el tema se ha editado manualmente.

En la tabla siguiente se describe lo que los usuarios (visores de temas, colaboradores y administradores de conocimientos) pueden ver en un tema determinado en función de sus permisos.

|Elemento de tema|Qué pueden ver los usuarios|
|:---------|:------------------|
|Nombre del tema|Los usuarios pueden ver el nombre del tema de todos los temas en el centro de temas. Es posible que algunos temas no sean visibles si tienen una relevancia baja para el usuario.|
|Descripción del tema|Las descripciones generadas por IA solo son visibles para los usuarios que tienen permisos para el contenido de origen. Todas las descripciones introducidas o editadas manualmente son visibles para todos los usuarios.|
|Contactos|Los usuarios anclados son visibles para todos los usuarios. Las personas sugeridas solo son visibles para los usuarios que tienen permisos para el contenido de origen.|
|Archivos|Los archivos solo son visibles para los usuarios que tienen permisos para el contenido de origen.|
|Páginas|Las páginas solo son visibles para los usuarios que tienen permisos para el contenido de origen.|
|Sitios|Los sitios solo son visibles para los usuarios que tienen permisos para el contenido de origen.|

## <a name="best-practices"></a>Procedimientos recomendados

Los temas presentan información a los usuarios en función de sus permisos existentes para el contenido. Microsoft 365 ofrece varias formas de garantizar que el contenido confidencial esté restringido a los usuarios adecuados. Además de los permisos estándar de [](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) equipo o sitio, puede usar [etiquetas](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) de confidencialidad o prevención de pérdida de datos para restringir el acceso al contenido y las revisiones de acceso para revisar periódicamente el acceso de los usuarios a información confidencial. [](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

Se recomienda usar estas herramientas para asegurarse de que los permisos de contenido se establecen correctamente dentro de la organización. Las experiencias de tema pueden proporcionar información útil y adecuada a los usuarios.

Si hay temas que desea excluir completamente de las experiencias de tema, también puede:

- [Excluir sitios confidenciales de SharePoint de la detección de temas.](topic-experiences-discovery.md#select-sharepoint-topic-sources) El contenido de estos sitios no aparecerá en las experiencias del tema.

- [Excluir temas por nombre.](topic-experiences-discovery.md#exclude-topics-by-name) Los temas excluidos explícitamente no aparecerán en las experiencias del tema.

- Hacer que los administradores de conocimientos quiten los temas del centro de temas.

Además, se recomiendan estos procedimientos recomendados:

- Contratar administradores de conocimientos de diferentes áreas de la organización. Tener administradores de conocimientos con una variedad de experiencia (y acceso al contenido subyacente usado por AI) puede ayudarte a proteger los conocimientos más útiles para los usuarios y a quitar información confidencial si se encuentra.

- Configurar un flujo de trabajo para solicitar cambios. Los administradores de conocimientos o los propietarios de equipos o sitios deben tener un proceso mediante el cual pueden solicitar la exclusión de temas o sitios a medida que se inician nuevos proyectos dentro de la organización o si encuentran contenido con configuraciones de permisos inadecuadas.

- Tenga en cuenta la audiencia y la confidencialidad de la información al crear descripciones de temas. Estas descripciones pueden ser visibles para los usuarios que no tienen permisos para el contenido de origen del tema.

Aunque puede cambiar los permisos en páginas de temas individuales para restringir el acceso a un grupo específico de usuarios, no se recomienda este enfoque debido al alto grado de esfuerzo administrativo necesario.

## <a name="see-also"></a>Vea también

[Configurar Teams con tres niveles de protección](../solutions/configure-teams-three-tiers-protection.md)

[Plan de las experiencias temáticas](plan-topic-experiences.md)

[Configurar las experiencias temáticas](set-up-topic-experiences.md)
