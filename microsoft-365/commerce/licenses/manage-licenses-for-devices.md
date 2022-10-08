---
title: Administración de licencias para dispositivos
f1.keywords:
- CSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: shegu, nicholak
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
description: Obtenga información sobre cómo asignar licencias a grupos para su uso con dispositivos.
ms.custom:
- commerce_licensing
- AdminSurgePortfolio
- okr_SMB
search.appverid: MET150
ms.date: 05/12/2022
ms.openlocfilehash: 4e514da6900230fefe87a8dc1ddecaa308c3cfe4
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68199183"
---
# <a name="manage-licenses-for-devices"></a>Administración de licencias para dispositivos

Si tiene Aplicaciones Microsoft 365 para empresas (dispositivo) o Aplicaciones Microsoft 365 para Educación (dispositivo), puede asignar licencias a los dispositivos mediante grupos de Azure AD. Cuando un dispositivo tiene una licencia, cualquier usuario que use ese dispositivo puede usar Aplicaciones Microsoft 365 para empresas (anteriormente denominado Office 365 ProPlus). Por ejemplo, supongamos que tiene 20 portátiles y tabletas que usan los usuarios de su organización. Al asignar una licencia a cada dispositivo, cada persona que inicia sesión en uno de los dispositivos usa Aplicaciones Microsoft 365 para empresas sin necesidad de su propia licencia.

> [!IMPORTANT]
> Las licencias basadas en dispositivos para Aplicaciones Microsoft 365 para empresas solo están disponibles como licencia de complemento para algunos clientes comerciales y algunos clientes educativos. Para los clientes comerciales, la licencia está *Aplicaciones Microsoft 365 para empresas (dispositivo)* y solo está disponible a través de Enterprise Agreement o Enterprise Agreement Suscripción. Para los clientes de educación, la licencia es *Aplicaciones Microsoft 365 para Educación (dispositivo)* y solo está disponible a través de Enrollment for Education Solutions (EES). Para obtener más información, lea la entrada de blog sobre [la disponibilidad educativa](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education). Para obtener disponibilidad comercial, póngase en contacto con el representante de su cuenta Microsoft.

Para empezar, cree un grupo en el Centro de administración de Azure Active Directory y, a continuación, asigne dispositivos al grupo. Para obtener más información sobre las licencias de dispositivos, incluidos los requisitos de dispositivo, los tipos de grupos que puede usar y cómo configurar Aplicaciones Microsoft 365 para empresas para usar licencias de dispositivos, consulte [Licencias basadas en dispositivos para Aplicaciones Microsoft 365 para empresas](/deployoffice/device-based-licensing).

> [!IMPORTANT]
> Debe ser administrador global para completar las tareas de este artículo.

## <a name="assign-licenses-to-devices"></a>Asignación de licencias a dispositivos

Al asignar licencias a un grupo, se asignan licencias a todos los dispositivos del grupo. Solo puede asignar una suscripción a cualquier grupo único.

1. En el Centro de administración de Microsoft 365, vaya a la página <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licencias</a> de **facturación** > .
2. En la página **Licencias**, elija **Aplicaciones Microsoft 365 para Educación (dispositivo)** o **Aplicaciones Microsoft 365 para empresas (dispositivo).**
3. En la página siguiente, elija una suscripción y, a continuación, elija **Asignar licencias**.
4. En el panel **Asignar licencias a un grupo** , empiece a escribir un nombre de grupo y, a continuación, selecciónelo en los resultados para agregarlo a la lista.
5. Elija **Asignar** y, a continuación, **elija Cerrar**.

## <a name="unassign-licenses-from-devices"></a>Anulación de la asignación de licencias de dispositivos

Al anular la asignación de licencias de un grupo, se quitan las licencias de todos los dispositivos del grupo. Todas las aplicaciones y sus datos asociados son de solo lectura.

1. En el centro de administración, vaya a la página <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licencias de</a> **facturación** > .
2. En la página **Licencias**, elija **Aplicaciones Microsoft 365 para Educación (dispositivo)** o **Aplicaciones Microsoft 365 para empresas (dispositivo).**
3. En la página siguiente, elija una suscripción, seleccione los tres puntos (más acciones) y, a continuación, elija **Anular la asignación de licencias**.
4. En el cuadro de diálogo **Anular asignación de licencias** , elija **Quitar la asignación**.
