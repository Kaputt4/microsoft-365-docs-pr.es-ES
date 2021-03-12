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
- m365solution-ediscovery
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: En este artículo se describe cómo configurar la exhibición de documentos electrónicos avanzada para que pueda empezar a crear y administrar casos. También describe las suscripciones y licencias de Microsoft necesarias. Después de completar algunos pasos rápidos, la herramienta eDiscovery avanzada está lista para usarse.
ms.openlocfilehash: 29a220f36a55a04d1c1a24add03b2e013a5c60ba
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727415"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a>Configurar eDiscovery avanzada de Microsoft 365

La exhibición de documentos electrónicos avanzada [](overview-ediscovery-20.md#advanced-ediscovery-workflow) en Microsoft 365 proporciona un flujo de trabajo completo para conservar, recopilar, revisar, analizar y exportar datos que responden a las investigaciones internas y externas de la organización. No se necesita nada para implementar la exhibición de documentos electrónicos avanzada, pero hay algunas tareas previas que un administrador de TI y un administrador de exhibición de documentos electrónicos deben completar antes de que su organización pueda empezar a crear y usar casos de exhibición de documentos electrónicos avanzados para administrar las investigaciones.

En este artículo se analizan los pasos necesarios para configurar la exhibición de documentos electrónicos avanzada. Esto incluye garantizar la licencia adecuada necesaria para tener acceso a eDiscovery avanzada y agregar custodios a los casos, y asignar permisos al equipo legal e investigador para que puedan acceder y administrar casos.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Paso 1: Comprobar y asignar licencias adecuadas

Las licencias para exhibición de documentos electrónicos avanzados requieren la suscripción de la organización adecuada y las licencias por usuario.

- **Suscripción a la organización:** Para tener acceso a la exhibición de documentos electrónicos avanzada en el Centro de cumplimiento de Microsoft 365 o el Centro de seguridad y & cumplimiento, la organización debe tener uno de los siguientes elementos:

  - Suscripciones a Microsoft 365 E5 u Office 365 E5.
  
  - Suscripción a Microsoft 365 E3 con complemento de cumplimiento E5

  - Suscripción a Microsoft 365 E3 con el complemento E5 eDiscovery and Audit

  Si no tiene un plan de Microsoft 365 E5 existente y desea probar eDiscovery avanzado, puede agregar [Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) [a](https://www.microsoft.com/microsoft-365/enterprise) su suscripción existente o registrarse para una prueba de Microsoft 365 E5.

- **Licencias por usuario:** Para agregar un usuario como custodio en un caso de exhibición de documentos electrónicos avanzados, ese usuario debe tener asignada una de las siguientes licencias, según la suscripción de la organización:

  - Microsoft 365: a los usuarios se les debe asignar una licencia de Microsoft 365 E5, una licencia de complemento de cumplimiento de E5 o una licencia de complemento E5 eDiscovery and Audit.

  - Office 365: Los usuarios deben tener asignada una licencia de Office 365 E5.

   Para obtener información sobre cómo asignar licencias, vea [Asignar licencias a usuarios.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

> [!NOTE]
> Los usuarios solo necesitan una licencia E5 (o la licencia de complemento adecuada) para agregarse como custodios a un caso de exhibición de documentos electrónicos avanzada. Los administradores de TI, administradores de exhibición de documentos electrónicos, abogados, asistentes legales o investigadores que usan eDiscovery avanzado para administrar casos y revisar datos de casos no necesitan una licencia de E5 o complemento.

## <a name="step-2-assign-ediscovery-permissions"></a>Paso 2: Asignar permisos de exhibición de documentos electrónicos

Para obtener acceso a la exhibición de documentos electrónicos avanzada o agregarse como miembro de un caso de exhibición de documentos electrónicos avanzados, se deben asignar los permisos adecuados a un usuario. Específicamente, un usuario debe agregarse como miembro del grupo de roles administrador de exhibición de documentos electrónicos en el Centro de seguridad & cumplimiento. Los miembros de este grupo de roles pueden crear y administrar casos de exhibición de documentos electrónicos avanzados. Pueden agregar y quitar miembros, poner en espera a custodios y ubicaciones de contenido, administrar notificaciones de retención legal, crear y editar búsquedas asociadas en un caso, agregar resultados de búsqueda a un conjunto de revisión, analizar datos de un conjunto de revisión y exportar y descargar desde un caso de exhibición de documentos electrónicos avanzado.

Siga estos pasos para agregar usuarios al grupo de roles administrador de exhibición de documentos electrónicos:

1. Vaya a e inicie sesión con las credenciales de una cuenta de administrador en su organización de [https://protection.office.com/permissions](https://protection.office.com/permissions) Microsoft 365.

2. En la **página Permisos,** seleccione el grupo de **roles** Administrador de exhibición de documentos electrónicos.

3. En la página desplegable administrador de exhibición de documentos electrónicos, haga clic **en Editar** junto a la sección Administrador de **exhibición de documentos** electrónicos.

4. En la página **Elegir administrador de exhibición** de documentos electrónicos en el asistente para editar grupos de roles, haga clic **en Elegir administrador de exhibición de documentos electrónicos.**

5. Haga **clic en** Agregar y seleccione la casilla para todos los usuarios que desee agregar al grupo de roles.

6. Haga **clic en** Agregar para agregar los usuarios seleccionados y, a continuación, haga clic en **Listo**.

7. Haga **clic en** Guardar para agregar los usuarios al grupo de roles y, a continuación, haga clic **en** Cerrar para completar el paso.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Más información sobre el grupo de roles administrador de exhibición de documentos electrónicos

Hay dos subgrupos en el grupo de roles administrador de exhibición de documentos electrónicos. La diferencia entre estos subgrupos se basa en el ámbito.

- **Administrador de exhibición de documentos electrónicos:** Puede ver y administrar los casos de exhibición de documentos electrónicos avanzados de los que crean o son miembros. Si otro administrador de exhibición de documentos electrónicos crea un caso pero no agrega un segundo administrador de exhibición de documentos electrónicos como miembro de ese caso, el segundo administrador de exhibición de documentos electrónicos no podrá ver ni abrir el caso en la página Exhibición de documentos electrónicos avanzada en el centro de cumplimiento. En general, la mayoría de las personas de la organización se pueden agregar al subgrupo del Administrador de exhibición de documentos electrónicos.

- **Administrador de exhibición de documentos electrónicos:** Puede realizar todas las tareas de administración de casos que un administrador de exhibición de documentos electrónicos puede realizar. Además, un administrador de exhibición de documentos electrónicos puede:

  - Ver todos los casos que se enumeran en la página Exhibición de documentos electrónicos avanzada.
  
  - Administre cualquier caso de la organización después de agregarse como miembro del caso.

  - Obtener acceso y exportar datos de casos para cualquier caso de la organización.

  Debido al amplio ámbito de acceso, una organización debe tener solo unos pocos administradores que sean miembros del subgrupo administradores de exhibición de documentos electrónicos.

Para obtener más información acerca de los permisos de exhibición de documentos electrónicos y una descripción de cada función asignada al grupo de roles administrador de exhibición de documentos electrónicos, vea Asignar permisos de exhibición [de documentos electrónicos](assign-ediscovery-permissions.md).

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a>Paso 3: Configurar la configuración global para eDiscovery avanzada

El último paso que se debe completar antes de que los usuarios de la organización comiencen a crear y usar casos es configurar las opciones globales que se aplican a todos los casos de la organización. En este momento, la única configuración global es *la detección* de privilegios de abogado y cliente (habrá más opciones globales disponibles en el futuro). Esta configuración permite que el modelo de privilegios abogado-cliente se ejecute al analizar los datos de un conjunto de revisión. El modelo usa el aprendizaje automático para determinar la probabilidad de que un documento contenga contenido de naturaleza legal. También compara los participantes de los documentos con una lista de abogados (que envía al configurar el modelo) para determinar si un documento tiene al menos un participante que sea abogado.

Para obtener más información acerca de cómo configurar y usar el modelo de detección de privilegios abogado-cliente, vea Configurar la detección de privilegios de [abogado-cliente en eDiscovery avanzada.](attorney-privilege-detection.md)

> [!NOTE]
> Este es un paso opcional que puede realizar en cualquier momento. No implementar el modelo de detección de privilegios abogado-cliente no le impide crear y usar casos de exhibición de documentos electrónicos avanzados.

## <a name="next-steps"></a>Siguientes pasos

Después de configurar la exhibición de documentos electrónicos avanzada, está listo para [crear un caso](create-and-manage-advanced-ediscoveryv2-case.md).
