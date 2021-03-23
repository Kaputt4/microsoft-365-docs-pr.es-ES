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
description: Obtenga información sobre cómo planear la seguridad y privacidad de Microsoft Viva Topics
ms.openlocfilehash: 91d0d5c25502a1938976b9457f8a5dafc6ab957b
ms.sourcegitcommit: 3d3c446d5e2e90369be1339dd0a33e71432fbc36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2021
ms.locfileid: "50994551"
---
# <a name="microsoft-viva-topics-security-and-privacy"></a>Seguridad y privacidad de Microsoft Viva Topics

Los temas usan las características de seguridad de contenido existentes en Microsoft 365, junto con los controles administrativos, para controlar lo que el contenido generado por IA se muestra a los usuarios de la organización. Es la combinación de la configuración de seguridad de Microsoft 365 (permisos para sitios, archivos y carpetas) y la configuración de administración temas que determinan lo que un usuario determinado puede ver en los temas.

La configuración de temas no modifica ningún control de acceso existente en el contenido de la organización. Los usuarios solo verán a lo que ya tienen acceso.

En este artículo se describe cómo funcionan los temas desde una perspectiva de seguridad y las opciones que los administradores de conocimientos y los administradores de conocimientos tienen para controlar la visibilidad del tema. Lea este artículo como parte de la [planeación de temas](plan-topic-experiences.md).

Debe estar familiarizado con los [](topic-center-overview.md) [temas](topic-experiences-overview.md), el centro de temas y cómo trabajar con los temas del centro de temas [antes](manage-topics.md) de leer este artículo.

## <a name="what-users-can-see-in-topics"></a>Lo que los usuarios pueden ver en los temas

Para ver temas, un usuario debe:

- Tener una licencia de Viva Topics
- Ser un [visor de temas,](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization) [colaborador o administrador de conocimientos](topic-experiences-user-permissions.md)

Estas dos cosas permiten a los usuarios ver el acceso al centro de temas y permitirles ver los resaltados y las tarjetas de tema.

Los colaboradores de temas también tienen permisos para crear [y](topic-experiences-user-permissions.md) editar temas, y los administradores de conocimientos pueden confirmar o quitar temas.

Cuando se detecta un tema por primera vez, los administradores de conocimientos pueden verlo en el centro de temas. Según la integridad y relevancia del tema, los visores de temas pueden ver o no el tema presentado en las tarjetas de tema.

Los temas pueden contener información generada por la inteligencia artificial y la información agregada o editada por colaboradores de temas o administradores de conocimientos.

- La información de un tema que AI agregó solo es visible para las personas que tienen acceso al contenido de origen.
- El texto que un colaborador o un administrador de conocimientos ha agregado o editado manualmente es visible para todos los usuarios que pueden ver el tema.

Los visores y colaboradores del tema pueden ver la lista de temas confirmados y publicados en el centro de temas, pero los detalles del tema que una persona determinada puede ver dependen de los permisos que tienen para el material de origen y de si el tema se ha editado manualmente.

En la tabla siguiente se describe lo que los usuarios (visores de temas, colaboradores y administradores de conocimientos) pueden ver en un tema determinado en función de sus permisos.

|Elemento de tema|Qué pueden ver los usuarios|
|:---------|:------------------|
|Nombre del tema|Los usuarios pueden ver el nombre del tema de los temas en el centro de temas. Es posible que algunos temas no sean visibles si los usuarios no tienen permisos para el contenido de origen o tienen una relevancia baja para el usuario.|
|Descripción del tema|Las descripciones generadas por IA solo son visibles para los usuarios que tienen permisos para el contenido de origen. Todas las descripciones introducidas o editadas manualmente son visibles para todos los usuarios.|
|Contactos|Las personas ancladas son visibles para todos los usuarios. Las personas sugeridas solo son visibles para los usuarios que tienen permisos para el contenido de origen.|
|Archivos|Los archivos solo son visibles para los usuarios que tienen permisos para el contenido de origen.|
|Páginas|Las páginas solo son visibles para los usuarios que tienen permisos para el contenido de origen.|
|Sitios|Los sitios solo son visibles para los usuarios que tienen permisos para el contenido de origen.|

## <a name="best-practices"></a>Procedimientos recomendados

Los temas presentan información a los usuarios en función de sus permisos existentes para el contenido. Microsoft 365 proporciona varias formas de garantizar que el contenido confidencial esté restringido a los usuarios adecuados. Además de los permisos estándar de [](../compliance/sensitivity-labels.md) grupo [](../compliance/data-loss-prevention-policies.md) o sitio, puede usar etiquetas de confidencialidad o prevención de pérdida de datos para restringir el acceso al contenido y las revisiones de acceso para revisar periódicamente el acceso de los usuarios a la información confidencial. [](/azure/active-directory/governance/access-reviews-overview)

Se recomienda usar estas herramientas para asegurarse de que los permisos de contenido se establecen correctamente dentro de la organización. A continuación, las experiencias temáticas pueden proporcionar información útil y adecuada a los usuarios.

Si hay temas que desea excluir por completo de las experiencias de temas, también puede:

- [Excluir sitios confidenciales de SharePoint de la detección de temas](topic-experiences-discovery.md#select-sharepoint-topic-sources). El contenido de estos sitios no aparecerá en las experiencias del tema.

- [Excluir temas por nombre](topic-experiences-discovery.md#exclude-topics-by-name). Los temas excluidos explícitamente no aparecerán en las experiencias del tema.

- Hacer que los administradores de conocimientos quiten los temas del centro de temas.

Además, se recomiendan estos procedimientos recomendados:

- Reclute administradores de conocimientos de diferentes áreas de la organización. Tener administradores de conocimientos con una variedad de conocimientos (y acceso al contenido subyacente usado por AI) puede ayudarle a curar los conocimientos más útiles para los usuarios y quitar información confidencial si se encuentra.

- Configurar un flujo de trabajo para solicitar cambios. Los administradores de conocimientos o los propietarios de equipos o sitios deben tener un proceso mediante el cual puedan solicitar la exclusión de temas o sitios a medida que se inician nuevos proyectos en su organización o si encuentran contenido con configuraciones de permisos inadecuadas.

- Tenga en cuenta la audiencia y la confidencialidad de la información al crear descripciones de temas. Estas descripciones pueden ser visibles para los usuarios que no tienen permisos para el contenido de origen del tema.

Aunque puede cambiar los permisos de las páginas de temas individuales para restringir el acceso a un grupo específico de usuarios, no se recomienda este enfoque debido al alto grado de esfuerzo administrativo necesario.

## <a name="see-also"></a>Consulte también

[Configurar Teams con tres niveles de protección](../solutions/configure-teams-three-tiers-protection.md)

[Plan de las experiencias temáticas](plan-topic-experiences.md)

[Configurar las experiencias temáticas](set-up-topic-experiences.md)
