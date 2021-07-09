---
title: Configurar Advanced eDiscovery en Microsoft 365
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
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: En este artículo se describe cómo configurar Advanced eDiscovery para que pueda empezar a crear y administrar casos. También describe las suscripciones y licencias de Microsoft necesarias. Después de completar algunos pasos rápidos, la Advanced eDiscovery está lista para usarse.
ms.openlocfilehash: be5e5aea03950d28889590004bd796455a71c5be
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341453"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a>Configurar Microsoft 365 Advanced eDiscovery

Advanced eDiscovery en Microsoft 365 proporciona un flujo de trabajo completo para conservar, recopilar, revisar, analizar y exportar datos que responden a las investigaciones internas y externas de la organización. No se necesita nada para implementar Advanced eDiscovery, pero hay algunas tareas de requisitos previos que un administrador de TI y un administrador de exhibición de documentos electrónicos deben completar antes de que su organización pueda empezar a crear y usar casos Advanced eDiscovery para administrar las investigaciones.

En este artículo se analizan los siguientes pasos necesarios para configurar Advanced eDiscovery.

![Pasos para configurar Advanced eDiscovery](../media/set-up-advanced-ediscovery.png)

Esto incluye garantizar la licencia adecuada necesaria para tener acceso a Advanced eDiscovery y agregar custodios a los casos, y asignar permisos al equipo legal e investigador para que puedan acceder y administrar los casos.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Paso 1: Comprobar y asignar licencias adecuadas

Las licencias Advanced eDiscovery requieren la suscripción de la organización adecuada y las licencias por usuario. Para obtener una lista de los requisitos de licencia Advanced eDiscovery, vea [Suscripciones y licencias](overview-ediscovery-20.md#subscriptions-and-licensing).

## <a name="step-2-assign-ediscovery-permissions"></a>Paso 2: Asignar permisos de exhibición de documentos electrónicos

Para obtener Advanced eDiscovery o agregar como miembro de un Advanced eDiscovery caso, se deben asignar los permisos adecuados a un usuario. Específicamente, un usuario debe agregarse como miembro del grupo de roles administrador de exhibición de documentos electrónicos en el Centro de seguridad & cumplimiento. Los miembros de este grupo de roles pueden crear y administrar Advanced eDiscovery casos. Pueden agregar y quitar miembros, poner a los custodios y ubicaciones de contenido en espera, administrar notificaciones de retención legal, crear y editar búsquedas asociadas en un caso, agregar resultados de búsqueda a un conjunto de revisión, analizar datos de un conjunto de revisión y exportar y descargar desde un caso Advanced eDiscovery.

Siga estos pasos para agregar usuarios al grupo de roles administrador de exhibición de documentos electrónicos:

1. Vaya a <https://compliance.microsoft.com/permissions> e inicie sesión con las credenciales de una cuenta de administrador en su Microsoft 365 organización.

2. En la **página Permisos,** seleccione el grupo de **roles** Administrador de exhibición de documentos electrónicos.

3. En la página desplegable administrador de exhibición de documentos electrónicos, haga clic **en Editar** junto a la sección Administrador de **exhibición de documentos** electrónicos.

4. En la página **Elegir administrador de exhibición** de documentos electrónicos en el asistente para editar grupos de roles, haga clic **en Elegir administrador de exhibición de documentos electrónicos.**

5. Haga **clic en** Agregar y seleccione la casilla para todos los usuarios que desee agregar al grupo de roles.

6. Haga **clic en** Agregar para agregar los usuarios seleccionados y, a continuación, haga clic en **Listo**.

7. Haga **clic en** Guardar para agregar los usuarios al grupo de roles y, a continuación, haga clic **en** Cerrar para completar el paso.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Más información sobre el grupo de roles administrador de exhibición de documentos electrónicos

Hay dos subgrupos en el grupo de roles administrador de exhibición de documentos electrónicos. La diferencia entre estos subgrupos se basa en el ámbito.

- **Administrador de exhibición de** documentos electrónicos: puede ver y administrar los Advanced eDiscovery de los que crean o son miembros. Si otro administrador de exhibición de documentos electrónicos crea un caso pero no agrega un segundo administrador de exhibición de documentos electrónicos como miembro de ese caso, el segundo administrador de exhibición de documentos electrónicos no podrá ver ni abrir el caso en la página Advanced eDiscovery del centro de cumplimiento. En general, la mayoría de las personas de la organización se pueden agregar al subgrupo del Administrador de exhibición de documentos electrónicos.

- **Administrador de exhibición de documentos electrónicos:** puede realizar todas las tareas de administración de casos que un administrador de exhibición de documentos electrónicos puede realizar. Además, un administrador de exhibición de documentos electrónicos puede:

  - Ver todos los casos que se enumeran en la página Exhibición de documentos electrónicos.
  
  - Administre cualquier caso en la organización después de que se agreguen como miembro del caso.

  - Acceda y exporte datos de casos en cualquier caso de la organización.

  Debido a la amplia gama de acceso que tiene que tener una organización, solo unos pocos administradores que sean miembros del subgrupo de administradores de eDiscovery.

Para obtener más información acerca de los permisos de exhibición de documentos electrónicos y una descripción de cada función asignada al grupo de roles administrador de exhibición de documentos electrónicos, vea Asignar permisos de exhibición [de documentos electrónicos](assign-ediscovery-permissions.md).

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a>Paso 3: Configurar la configuración global para Advanced eDiscovery

El último paso que se debe completar antes de que los usuarios de la organización comiencen a crear y usar casos es configurar las opciones globales que se aplican a todos los casos de la organización. En este momento, la única configuración global es *la detección* de privilegios de abogado y cliente (habrá más opciones globales disponibles en el futuro). Esta configuración permite que el modelo de privilegios abogado-cliente se ejecute al analizar los datos de un conjunto de revisión. El modelo usa el aprendizaje automático para determinar la probabilidad de que un documento contenga contenido de naturaleza legal. También compara los participantes de los documentos con una lista de abogados (que envía al configurar el modelo) para determinar si un documento tiene al menos un participante que sea abogado.

Para obtener más información acerca de cómo configurar y usar el modelo de detección de privilegios [abogado-cliente,](attorney-privilege-detection.md)vea Configurar la detección de privilegios de abogado-cliente en Advanced eDiscovery .

> [!NOTE]
> Este es un paso opcional que puede realizar en cualquier momento. No implementar el modelo de detección de privilegios abogado-cliente no le impide crear y usar Advanced eDiscovery casos.

## <a name="next-steps"></a>Siguientes pasos

Después de configurar Advanced eDiscovery, está listo para [crear un caso](create-and-manage-advanced-ediscoveryv2-case.md).