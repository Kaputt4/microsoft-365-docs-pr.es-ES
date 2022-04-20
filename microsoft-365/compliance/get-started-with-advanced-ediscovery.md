---
title: Configuración de eDiscovery (Premium) en Microsoft Purview
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-scenario
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MOE150
- MET150
description: En este artículo se describe cómo configurar eDiscovery (Premium) para que pueda empezar a crear y administrar casos. También describe las suscripciones y licencias de Microsoft necesarias. Después de completar algunos pasos rápidos, la herramienta eDiscovery (Premium) está lista para usarse.
ms.openlocfilehash: 29805066c2db26aca6992dc34ad8bf8c0966ceb7
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64939925"
---
# <a name="set-up-microsoft-purview-ediscovery-premium"></a>Configuración de microsoft Purview eDiscovery (Premium)

Microsoft Purview eDiscovery (Premium) proporciona un flujo de trabajo de un extremo a otro para conservar, recopilar, revisar, analizar y exportar datos que respondan a las investigaciones internas y externas de su organización. No se necesita nada para implementar eDiscovery (Premium), pero hay algunas tareas de requisitos previos que un administrador de TI y un administrador de eDiscovery deben completar antes de que la organización pueda empezar a crear y usar casos de eDiscovery (Premium) para administrar las investigaciones.

En este artículo se describen los pasos siguientes necesarios para configurar eDiscovery (Premium).

![Pasos para configurar eDiscovery (Premium).](../media/set-up-advanced-ediscovery.png)

Esto incluye garantizar las licencias adecuadas necesarias para acceder a eDiscovery (Premium) y agregar custodios a los casos, y asignar permisos al equipo legal y de investigación para que puedan acceder a los casos y administrarlos.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Paso 1: Comprobar y asignar las licencias adecuadas

Las licencias para eDiscovery (Premium) requieren la suscripción de la organización adecuada y las licencias por usuario. Para obtener una lista de los requisitos de licencia para eDiscovery (Premium), consulte [Suscripciones y licencias](overview-ediscovery-20.md#subscriptions-and-licensing).

## <a name="step-2-assign-ediscovery-permissions"></a>Paso 2: Asignar permisos de exhibición de documentos electrónicos

Para acceder a eDiscovery (Premium) o agregarse como miembro de un caso de exhibición de documentos electrónicos (Premium), se deben asignar a un usuario los permisos adecuados. En concreto, se debe agregar un usuario como miembro del grupo de roles administrador de exhibición de documentos electrónicos en el portal de cumplimiento de Microsoft Purview. Los miembros de este grupo de roles pueden crear y administrar casos de exhibición de documentos electrónicos (Premium). Pueden agregar y quitar miembros, colocar custodios y ubicaciones de contenido en espera, administrar notificaciones de suspensión legal, crear y editar búsquedas asociadas en un caso, agregar resultados de búsqueda a un conjunto de revisión, analizar datos en un conjunto de revisión y exportar y descargar desde un caso de exhibición de documentos electrónicos (Premium).

Complete los pasos siguientes para agregar usuarios al grupo de roles del Administrador de exhibición de documentos electrónicos:

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2173597" target="_blank">portal de cumplimiento</a> e inicie sesión con las credenciales de una cuenta de administrador en la organización Microsoft 365.

2. En la página **Permisos** , seleccione el grupo **de roles administrador de exhibición de documentos electrónicos** .

3. En la página desplegable Administrador de exhibición de documentos electrónicos, haga clic en **Editar** junto a la sección **Administrador de exhibición de documentos electrónicos** .

4. En la página **Elegir administrador de exhibición de documentos electrónicos** del Asistente para editar grupos de roles, haga clic en **Elegir administrador de exhibición de documentos electrónicos**.

5. Haga clic en **Agregar** y seleccione la casilla para todos los usuarios que quiera agregar al grupo de roles.

6. Haga clic en **Agregar** para agregar los usuarios seleccionados y, a continuación, haga clic en **Listo**.

7. Haga clic en **Guardar** para agregar los usuarios al grupo de roles y, a continuación, haga clic en **Cerrar** para completar el paso.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Más información sobre el grupo de roles del Administrador de exhibición de documentos electrónicos

Hay dos subgrupos en el grupo de roles del Administrador de exhibición de documentos electrónicos. La diferencia entre estos subgrupos se basa en el ámbito.

- **Administrador de exhibición de documentos** electrónicos: puede ver y administrar los casos de eDiscovery (Premium) de los que crean o son miembros. Si otro Administrador de exhibición de documentos electrónicos crea un caso pero no agrega un segundo Administrador de exhibición de documentos electrónicos como miembro de ese caso, el segundo Administrador de exhibición de documentos electrónicos no podrá ver ni abrir el caso en la página eDiscovery (Premium) del centro de cumplimiento. En general, la mayoría de las personas de la organización se pueden agregar al subgrupo administrador de exhibición de documentos electrónicos.

- **Administrador de eDiscovery**: puede realizar todas las tareas de administración de casos que un Administrador de exhibición de documentos electrónicos puede realizar. Además, un administrador de exhibición de documentos electrónicos puede:

  - Vea todos los casos que aparecen en la página eDiscovery (Premium).
  
  - Administre cualquier caso en la organización después de que se agreguen como miembro del caso.

  - Acceda y exporte datos de casos en cualquier caso de la organización.

  Debido a la amplia gama de acceso que tiene que tener una organización, solo unos pocos administradores que sean miembros del subgrupo de administradores de eDiscovery.

Para obtener más información sobre los permisos de eDiscovery y una descripción de cada rol asignado al grupo de roles del Administrador de exhibición de documentos electrónicos, vea [Asignar permisos de exhibición de documentos electrónicos](assign-ediscovery-permissions.md).

## <a name="step-3-configure-global-settings-for-ediscovery-premium"></a>Paso 3: Configurar la configuración global para eDiscovery (Premium)

El último paso que debe completarse antes de que los usuarios de su organización empiecen a crear y usar casos es configurar las opciones globales que se aplican a todos los casos de la organización. En este momento, la única configuración global es *detección de privilegios entre abogado y cliente* (habrá más configuraciones globales disponibles en el futuro). Esta configuración permite que el modelo de privilegios abogado-cliente se ejecute al analizar los datos de un conjunto de revisión. El modelo usa el aprendizaje automático para determinar la probabilidad de que un documento contenga contenido de naturaleza legal. También compara a los participantes de los documentos con una lista de abogados (que usted envía al configurar el modelo) para determinar si un documento tiene al menos un participante que es un abogado.

Para obtener más información sobre cómo configurar y usar el modelo de detección de privilegios abogado-cliente, vea [Configurar la detección de privilegios de abogado-cliente en eDiscovery (Premium)](attorney-privilege-detection.md).

> [!NOTE]
> Este es un paso opcional que puede realizar en cualquier momento. No implementar el modelo de detección de privilegios abogado-cliente no impide crear y usar casos de exhibición de documentos electrónicos (Premium).

## <a name="next-steps"></a>Siguientes pasos

Después de configurar eDiscovery (Premium), está listo para [crear un caso](create-and-manage-advanced-ediscoveryv2-case.md).