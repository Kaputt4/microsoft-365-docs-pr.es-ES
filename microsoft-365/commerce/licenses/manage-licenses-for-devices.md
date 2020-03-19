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
ms.openlocfilehash: a29465e9425694f8913cc09d1b8a0c761c79803c
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826284"
---
# <a name="manage-licenses-for-devices"></a>Administrar licencias para dispositivos

Si tiene Office 365 ProPlus (dispositivo) u Office 365 ProPlus para educación (dispositivo), puede asignar licencias a los dispositivos con grupos de Azure AD. Cuando un dispositivo tiene una licencia, cualquier usuario que use ese dispositivo puede usar Office 365. Por ejemplo, supongamos que tiene 20 equipos portátiles y tabletas que usan las personas de su organización. Cuando se asigna una licencia a cada dispositivo, cada persona que inicie sesión en uno de los dispositivos usa Office 365 sin la necesidad de su propia licencia.

> [!IMPORTANT]
> La licencia basada en dispositivos para Office 365 ProPlus solo está disponible como una licencia de complemento para algunos clientes de commerical y para algunos clientes de educación. Para los clientes comerciales, la licencia es *Office 365 ProPlus (dispositivo)* y solo está disponible a través de Enterprise Agreement/Enterprise Agreement subscription. Para los clientes de educación, la licencia es *Office 365 ProPlus para el ámbito educativo (dispositivo)* y está disponible solo a través de la inscripción para las soluciones educativas (EES). Para obtener más información, lea la entrada de blog sobre la [disponibilidad de educación](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/). Para obtener disponibilidad comercial, póngase en contacto con el representante de su cuenta de Microsoft.

Para empezar, cree un grupo en el centro de administración de Azure Active Directory y, a continuación, asigne dispositivos al grupo. Para obtener más información sobre las licencias de dispositivos, incluidos los requisitos de dispositivos, los tipos de grupos que puede usar y cómo configurar Office 365 ProPlus para usar licencias de dispositivos, consulte [licencias basadas en dispositivos para office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=2094216).

> [!IMPORTANT]
> Debe ser un administrador global para completar las tareas de este artículo.

## <a name="assign-licenses-to-devices"></a>Asignar licencias a dispositivos

Cuando se asignan licencias a un grupo, se asignan licencias a todos los dispositivos del grupo. Solo se puede asignar una suscripción a un único grupo.

1. En el centro de administración de Microsoft 365, vaya a la página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licencias</a> de **facturación** > .
2. En la página **licencias** , elija **Office 365 ProPlus para educación (dispositivo)** u **Office ProPlus (dispositivo)**.
3. En la página siguiente, elija una suscripción y, a continuación, elija **asignar licencias**.
4. En el panel **asignar licencias a un grupo** , empiece a escribir un nombre de grupo y, a continuación, selecciónelo en los resultados para agregarlo a la lista.
5. Elija **asignar**y, después, haga clic en **cerrar**.

## <a name="unassign-licenses-from-devices"></a>Cancelar la asignación de licencias de dispositivos

Al anular la asignación de licencias de un grupo, se quitan las licencias de todos los dispositivos dentro del grupo. Todas las aplicaciones y sus datos asociados son de solo lectura.

1. En el centro de administración, vaya a la página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licencias</a> de **facturación** > .
2. En la página **licencias** , elija **Office 365 ProPlus para educación (dispositivo)** u **Office ProPlus (dispositivo)**.
3. En la página siguiente, elija una suscripción, elija **más acciones**y, a continuación, elija **Cancelar asignación de licencias**.
4. En el cuadro de diálogo **cancelar la asignación de licencias** , elija **Anular asignación**.