---
title: Configurar eDiscovery avanzado en Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: En este artículo se describe cómo configurar eDiscovery avanzado para que pueda empezar a crear y administrar casos. También describe las suscripciones y licencias de Microsoft necesarias. Después de completar algunos pasos rápidos, la herramienta eDiscovery avanzado está lista para usarse.
ms.openlocfilehash: aef5cd2e465306b4401cda66d4ba30c97b9fc8cd
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841181"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a>Configurar eDiscovery avanzado de Microsoft 365

EDiscovery avanzado en Microsoft 365 proporciona un flujo de trabajo completo para conservar, recopilar, revisar, analizar y exportar datos que responden a las investigaciones internas y externas de su organización. [](overview-ediscovery-20.md#advanced-ediscovery-workflow) No se necesita nada para implementar eDiscovery avanzado, pero hay algunas tareas de requisitos previos que un administrador de TI y un administrador de exhibición de documentos electrónicos deben completar antes de que su organización pueda empezar a crear y usar casos de eDiscovery avanzados para administrar sus investigaciones.

Este artículo describe los pasos necesarios para configurar eDiscovery avanzado. Esto incluye garantizar la licencia adecuada necesaria para acceder a eDiscovery avanzado y agregar administradores a los casos, y asignar permisos a su equipo legal e investigación para que puedan acceder a los casos y administrarlos.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Paso 1: Comprobar y asignar las licencias adecuadas

Las licencias para eDiscovery avanzado requieren la suscripción de la organización y las licencias por usuario adecuadas.

- **Suscripción a la organización:** Para obtener acceso a eDiscovery avanzado en el Centro de cumplimiento de Microsoft 365 o en el Centro de seguridad & cumplimiento, su organización debe tener uno de los siguientes elementos:

  - Suscripciones a Microsoft 365 E5 u Office 365 E5.
  
  - Suscripción a Microsoft 365 E3 con complemento de cumplimiento E5

  - Suscripción a Microsoft 365 E3 con el complemento E5 eDiscovery y Auditoría

  Si no tiene un plan de Microsoft 365 E5 existente y quiere probar eDiscovery avanzado, puede agregar [Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) [a](https://www.microsoft.com/microsoft-365/enterprise) su suscripción existente o registrarse para una prueba de Microsoft 365 E5.

- **Licencias por usuario:** Para agregar un usuario como administrador en un caso de eDiscovery avanzado, se le debe asignar una de las siguientes licencias, según la suscripción de su organización:

  - Microsoft 365: Los usuarios deben tener asignada una licencia de Microsoft 365 E5, una licencia de complemento de cumplimiento de E5 o una licencia de complemento de auditoría y exhibición de documentos electrónicos de E5.

  - Office 365: Los usuarios deben tener asignada una licencia de Office 365 E5.

   Para obtener información acerca de cómo asignar licencias, vea [Asignar licencias a los usuarios.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

> [!NOTE]
> Los usuarios solo necesitan una licencia E5 (o la licencia de complemento adecuada) para agregarse como administradores a un caso de eDiscovery avanzado. Los administradores de TI, administradores de exhibición de documentos electrónicos, abogados, asistentes legales o investigadores que usan eDiscovery avanzado para administrar casos y revisar datos de casos no necesitan una licencia de complemento o E5.

## <a name="step-2-assign-ediscovery-permissions"></a>Paso 2: Asignar permisos de exhibición de documentos electrónicos

Para obtener acceso a eDiscovery avanzado o agregarlo como miembro de un caso de eDiscovery avanzado, se deben asignar a un usuario los permisos adecuados. Específicamente, un usuario debe agregarse como miembro del grupo de roles administrador de exhibición de documentos electrónicos en el Centro de & cumplimiento. Los miembros de este grupo de roles pueden crear y administrar casos de eDiscovery avanzado. Pueden agregar y quitar miembros, colocar administradores y ubicaciones de contenido en espera, administrar notificaciones de retención legal, crear y editar búsquedas asociadas en un caso, agregar resultados de búsqueda a un conjunto de revisión, analizar datos en un conjunto de revisión y exportar y descargar desde un caso de eDiscovery avanzado.

Complete los siguientes pasos para agregar usuarios al grupo de roles administrador de exhibición de documentos electrónicos:

1. Vaya e inicie sesión con las credenciales de una cuenta [https://protection.office.com/permissions](https://protection.office.com/permissions) de administrador de su organización de Microsoft 365.

2. En la **página Permisos,** seleccione el grupo de roles administrador de **exhibición** de documentos electrónicos.

3. En la página desplegable del Administrador de exhibición de documentos electrónicos, haga clic en **Editar** junto a la sección **Administrador de exhibición de documentos** electrónicos.

4. En la página **Elegir administrador de exhibición** de documentos electrónicos en el asistente para editar grupo de roles, haga clic **en Elegir administrador de exhibición de documentos electrónicos.**

5. Haga **clic en** Agregar y, a continuación, active la casilla para todos los usuarios que desee agregar al grupo de roles.

6. Haga **clic en** Agregar para agregar los usuarios seleccionados y, a continuación, haga clic en **Listo.**

7. Haga **clic en** Guardar para agregar los usuarios al grupo de roles y, a continuación, haga clic en Cerrar para completar el paso. 

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Más información sobre el grupo de roles administrador de exhibición de documentos electrónicos

Hay dos subgrupos en el grupo de roles administrador de exhibición de documentos electrónicos. La diferencia entre estos subgrupos se basa en el ámbito.

- **Administrador de exhibición de documentos electrónicos:** Puede ver y administrar los casos de eDiscovery avanzados que crean o de los que son miembros. Si otro administrador de exhibición de documentos electrónicos crea un caso pero no agrega un segundo administrador de exhibición de documentos electrónicos como miembro de ese caso, el segundo administrador de exhibición de documentos electrónicos no podrá ver ni abrir el caso en la página eDiscovery avanzado en el centro de cumplimiento. En general, la mayoría de las personas de su organización se pueden agregar al subgrupo administrador de exhibición de documentos electrónicos.

- **Administrador de exhibición de documentos electrónicos:** Puede realizar todas las tareas de administración de casos que un administrador de exhibición de documentos electrónicos puede realizar. Además, un administrador de exhibición de documentos electrónicos puede:

  - Ver todos los casos que aparecen en la página eDiscovery avanzado.
  
  - Administrar cualquier caso de la organización después de agregarse a sí mismos como miembro del caso.

  - Obtener acceso a los datos de casos y exportarlos en cualquier caso de la organización.

  Debido al amplio ámbito de acceso, una organización debe tener solo unos pocos administradores que sean miembros del subgrupo administradores de exhibición de documentos electrónicos.

Para obtener más información acerca de los permisos de exhibición de documentos electrónicos y una descripción de cada rol asignado al grupo de roles administrador de exhibición de documentos electrónicos, vea Asignar permisos de [exhibición de documentos electrónicos.](assign-ediscovery-permissions.md)

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a>Paso 3: Configurar las opciones globales para eDiscovery avanzado

El último paso que debe completarse antes de que los usuarios de su organización empiecen a crear y usar casos es configurar las opciones globales que se aplican a todos los casos de la organización. En este momento, la única configuración global es la detección de privilegios *abogado-cliente* (habrá más configuraciones globales disponibles en el futuro). Esta configuración permite que el modelo de privilegios abogado-cliente se ejecute al analizar los datos de un conjunto de revisión. El modelo usa el aprendizaje automático para determinar la probabilidad de que un documento contenga contenido de naturaleza legal. También compara los participantes de los documentos con una lista de abogados (que envía al configurar el modelo) para determinar si un documento tiene al menos un participante que es abogado.

Para obtener más información acerca de cómo configurar y usar el modelo de detección de privilegios abogado-cliente, vea Configurar la detección de privilegios [abogado-cliente en eDiscovery avanzado.](attorney-privilege-detection.md)

> [!NOTE]
> Este es un paso opcional que puede realizar en cualquier momento. No implementar el modelo de detección de privilegios abogado-cliente no le impide crear y usar casos de eDiscovery avanzado.

## <a name="next-steps"></a>Siguientes pasos

Después de configurar eDiscovery avanzado, está listo para [crear un caso.](create-and-manage-advanced-ediscoveryv2-case.md)
