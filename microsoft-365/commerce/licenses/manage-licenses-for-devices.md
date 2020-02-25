---
title: Administrar licencias para dispositivos
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: Obtenga información sobre cómo asignar licencias a grupos para usarlas con dispositivos.
ms.custom: okr_SMB
search.appverid:
- MET150
ms.openlocfilehash: c7c747d5f4d2408b717bf16068d23c7882c2d667
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42246352"
---
# <a name="manage-licenses-for-devices"></a>Administrar licencias para dispositivos

Si tiene Office 365 ProPlus for Education (dispositivo), puede asignar licencias a los dispositivos con grupos de Azure AD. Cuando un dispositivo tiene una licencia, cualquier usuario que use ese dispositivo puede usar Office 365. Por ejemplo, supongamos que tiene 20 equipos portátiles y tabletas que usan las personas de su organización. Cuando se asigna una licencia a cada dispositivo, cada persona que inicie sesión en uno de los dispositivos usa Office 365 sin la necesidad de su propia licencia.

> [!IMPORTANT]
> Office 365 ProPlus para el ámbito educativo (dispositivo) solo está disponible para los clientes de licencias por volumen a3 y A5.

Para empezar, cree un grupo en el centro de administración de Azure Active Directory y, a continuación, asigne dispositivos al grupo. Para obtener más información sobre las licencias de dispositivos, incluidos los requisitos de dispositivos, los tipos de grupos que puede usar y cómo configurar Office 365 ProPlus para usar licencias de dispositivos, vea [licencias de dispositivos para office 365 ProPlus para educación para clientes](https://go.microsoft.com/fwlink/p/?linkid=2094216).

> [!IMPORTANT]
> Debe ser un administrador global para completar las tareas de este artículo.

## <a name="assign-licenses-to-devices"></a>Asignar licencias a dispositivos

Cuando se asignan licencias a un grupo, se asignan licencias a todos los dispositivos del grupo. Solo se puede asignar una suscripción a un único grupo.

1. En el centro de administración de Microsoft 365, vaya a la página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licencias</a> de **facturación** > .
2. En la página **licencias** , elija **Office 365 ProPlus para educación (dispositivo)**.
3. En la página **Office 365 ProPlus para educación (dispositivo)** , elija una suscripción y, a continuación, elija **asignar licencias**.
4. En el panel **asignar licencias a un grupo** , empiece a escribir un nombre de grupo y, a continuación, selecciónelo en los resultados para agregarlo a la lista.
6. Elija **asignar**y, después, haga clic en **cerrar**.

## <a name="unassign-licenses-from-devices"></a>Cancelar la asignación de licencias de dispositivos

Al anular la asignación de licencias de un grupo, se quitan las licencias de todos los dispositivos dentro del grupo. Todas las aplicaciones y sus datos asociados son de solo lectura.

1. En el centro de administración, vaya a la página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licencias</a> de **facturación** > .
2. En la página **licencias** , elija **Office 365 ProPlus para educación (dispositivo)**.
3. En la página **Office 365 ProPlus para educación (dispositivo)** , elija una suscripción, elija **más acciones**y, a continuación, elija **Cancelar asignación de licencias**.
5. En el cuadro de diálogo **cancelar la asignación de licencias** , elija **Anular asignación**.