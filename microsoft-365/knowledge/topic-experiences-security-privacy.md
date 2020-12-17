---
title: Tema experiencias de seguridad y privacidad
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye, cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre cómo planear la seguridad y privacidad de los temas en Microsoft 365
ms.openlocfilehash: b3c33a49b8273c5f7830f08de17af9757a858413
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698502"
---
# <a name="topic-experiences-security-and-privacy"></a>Tema experiencias de seguridad y privacidad

El tema experiencias usa las características de seguridad de contenido existentes en Microsoft 365, junto con los controles de red de conocimiento, para controlar el contenido generado por AI que se muestra a los usuarios de la organización. La combinación de la configuración de seguridad de Microsoft 365 (permisos para sitios, archivos y carpetas) y el tema experiencia de administración del tema que determinan lo que un usuario determinado puede ver en los temas.

La configuración de la red de conocimiento no modifica los controles de acceso existentes en el contenido de la organización. Los usuarios solo verán a lo que ya tienen acceso.

En este artículo se describe cómo funciona la experiencia del tema desde el punto de vista de la seguridad y las opciones que los administradores de conocimientos y los administradores del conocimiento tienen para controlar la visibilidad de los temas. Lea este artículo como parte de la [planeación de experiencias en el tema](plan-topic-experiences.md).

Debe estar familiarizado con las [experiencias](topic-experiences-overview.md)de temas, el [centro de temas](topic-center-overview.md)y la forma de [trabajar con temas en el centro de](manage-topics.md) temas antes de leer este artículo.

## <a name="what-users-can-see-in-topics"></a>Lo que los usuarios pueden ver en los temas

Para ver los temas, un usuario debe:

- Tener un tema de licencia de experiencia
- Ser un [visor de temas](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization), [colaborador o administrador de conocimiento](topic-experiences-user-permissions.md)

Estas dos cosas proporcionan a los usuarios acceso al centro de temas y les permiten ver los elementos destacados y las tarjetas de temas.

Además, los colaboradores del tema tienen permisos de [creación y edición](topic-experiences-user-permissions.md#change-who-has permissions-to-update-topic-details) para los temas, y los administradores del conocimiento pueden confirmar o quitar temas.

Cuando se descubre un tema por primera vez, los administradores de conocimiento pueden verlo en el centro de temas. En función de la integridad y relevancia del tema, los visores de temas pueden ver o no el tema que se presenta en las tarjetas de temas.

Los temas pueden contener información generada por AI e información agregada o modificada por los colaboradores de temas o los administradores de conocimientos.

- La información de un tema agregado por AI solo es visible para los usuarios que tienen acceso al contenido de origen.
- El texto que se ha agregado o editado manualmente por un colaborador de temas o por el administrador de conocimiento es visible para todos los usuarios que puedan ver el tema.

Los visores y colaboradores de temas pueden ver la lista de temas confirmados y publicados en el centro del tema, pero el tema detalles que puede ver una persona determinada depende de los permisos que tienen en el material de origen y de si el tema se ha editado manualmente.

En la tabla siguiente, se describen los visores de temas, los colaboradores y los administradores del conocimiento que pueden ver en un tema determinado en función de sus permisos.

|Elemento de tema|Qué pueden ver los usuarios|
|:---------|:------------------|
|Nombre del tema|Los usuarios pueden ver el nombre de tema de todos los temas del centro de temas. Es posible que algunos temas no estén visibles si tienen una importancia baja para el usuario.|
|Descripción del tema|Las descripciones generadas por AI solo son visibles para los usuarios que tienen permisos en el contenido de origen. Las descripciones especificadas o editadas manualmente son visibles para todos los usuarios.|
|Personas|Las personas ancladas son visibles para todos los usuarios. Los usuarios sugeridos solo son visibles para los usuarios que tienen permisos para el contenido de origen.|
|Archivos|Los archivos solo están visibles para los usuarios que tienen permisos para el contenido de origen.|
|Páginas|Las páginas solo están visibles para los usuarios que tienen permisos para el contenido de origen.|
|Sitios|Los sitios solo están visibles para los usuarios que tienen permisos para el contenido de origen.|

## <a name="best-practices"></a>Procedimientos recomendados

El tema experiencias presenta información a los usuarios en función de sus permisos existentes para el contenido. Microsoft 365 ofrece varias formas de garantizar que el contenido confidencial esté restringido a los usuarios apropiados. Más allá de los permisos estándar del equipo o del sitio, puede usar [etiquetas de confidencialidad](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) o [prevención de pérdida de datos](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) para restringir el acceso al contenido y [tener acceso](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) a las revisiones para revisar periódicamente el acceso del usuario a la información confidencial.

Le recomendamos que use estas herramientas para asegurarse de que los permisos de contenido están establecidos adecuadamente dentro de la organización. Las experiencias de los temas pueden proporcionar a los usuarios información útil y adecuada.

Si hay temas que desea excluir completamente de las experiencias de los temas, también puede:

- [Excluir sitios confidenciales de SharePoint del descubrimiento de temas](topic-experiences-discovery.md#select-sharepoint-topic-sources). El contenido de estos sitios no aparecerá en las experiencias del tema.

- [Excluir los temas por nombre](topic-experiences-discovery.md#exclude-topics-by-name). Los temas excluidos explícitamente no aparecerán en las experiencias del tema.

- Pida a los administradores de conocimientos que eliminen temas del centro de temas.

Además, recomendamos estos procedimientos recomendados:

- Reclutar administradores del conocimiento de diferentes áreas de la organización. El hecho de que los administradores de conocimientos con una amplia variedad de conocimientos y acceso al contenido subyacente que usa AI, puede ayudarle a Curate el conocimiento más útil para sus usuarios y quitar la información confidencial si se encuentra.

- Configurar un flujo de trabajo para solicitar cambios. Los administradores de conocimiento o los propietarios de los equipos o sitios deben tener un proceso mediante el cual puedan solicitar la exclusión de temas o sitios a medida que se inician nuevos proyectos dentro de la organización o si encuentran contenido con una configuración de permisos inadecuada.

- Tenga en cuenta la audiencia y la confidencialidad de la información al crear descripciones de temas. Estas descripciones pueden ser visibles para los usuarios que no tienen permisos para el contenido de origen del tema.

Aunque puede cambiar los permisos de las páginas de temas individuales para restringir el acceso a un grupo específico de usuarios, no se recomienda este enfoque debido al alto grado de esfuerzo administrativo necesario.

## <a name="see-also"></a>Vea también

[Configurar Teams con tres niveles de protección](../solutions/configure-teams-three-tiers-protection.md)

[Planeación de experiencias de temas](plan-topic-experiences.md)

[Configurar experiencias de tema](set-up-topic-experiences.md)
