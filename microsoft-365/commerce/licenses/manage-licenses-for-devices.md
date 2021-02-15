---
title: Administrar licencias para dispositivos
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: Aprende a asignar licencias a grupos para su uso con dispositivos.
ms.custom:
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
ms.openlocfilehash: 29bd56ccff01d8c21cc67d1188fa21e338fb4b7e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638188"
---
# <a name="manage-licenses-for-devices"></a>Administrar licencias para dispositivos

Si tiene Aplicaciones de Microsoft 365 para empresas (dispositivo) o Aplicaciones de Microsoft 365 para educación (dispositivo), puede asignar licencias a dispositivos mediante grupos de Azure AD. Cuando un dispositivo tiene una licencia, cualquier persona que use ese dispositivo puede usar Aplicaciones de Microsoft 365 para empresas (anteriormente denominado Office 365 ProPlus). Por ejemplo, supongamos que tiene 20 portátiles y tabletas que usan las personas de su organización. Cuando asigna una licencia a cada dispositivo, cada persona que inicia sesión en uno de los dispositivos usa Aplicaciones de Microsoft 365 para empresas sin necesidad de su propia licencia.

> [!IMPORTANT]
> Las licencias basadas en dispositivos para Aplicaciones de Microsoft 365 para empresas solo están disponibles como una licencia de complemento para algunos clientes comerciales y algunos clientes de educación. Para los clientes comerciales, la licencia es Aplicaciones de *Microsoft 365* para empresas (dispositivo) y solo está disponible a través de Contrato Enterprise/Contrato Enterprise suscripción. Para los clientes del sector educativo, la licencia es Aplicaciones de *Microsoft 365* para educación (dispositivo) y solo está disponible a través de Enrollment for Education Solutions (EES). Para obtener más información, lea la entrada del blog sobre [la disponibilidad educativa.](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/) Para obtener disponibilidad comercial, póngase en contacto con el representante de su cuenta de Microsoft.

Para empezar, cree un grupo en el Centro de administración de Azure Active Directory y, a continuación, asigne dispositivos al grupo. Para obtener más información sobre las licencias de dispositivos, incluidos los requisitos de dispositivo, los tipos de grupos que puede usar y cómo configurar Aplicaciones de Microsoft 365 para empresas para usar licencias de dispositivos, consulte Licencias basadas en dispositivos para Aplicaciones de [Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2094216)para empresas.

> [!IMPORTANT]
> Debe ser administrador global para completar las tareas de este artículo.

## <a name="assign-licenses-to-devices"></a>Asignar licencias a dispositivos

Cuando asignas licencias a un grupo, asignas licencias a todos los dispositivos del grupo. Solo puede asignar una suscripción a cualquier grupo único.

1. En el Centro de administración de Microsoft 365, vaya a la página  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licencias de</a> facturación.
2. En la **página Licencias,** elija Aplicaciones de **Microsoft 365** para educación (dispositivo) o Aplicaciones de **Microsoft 365** para empresas (dispositivo).
3. En la página siguiente, elija una suscripción y, a continuación, **elija Asignar licencias.**
4. En el panel Asignar licencias a un grupo, empiece a escribir un nombre de grupo y, a continuación, selecciónelo en los **resultados** para agregarlo a la lista.
5. Elija **Asignar** y, a continuación, **seleccione Cerrar**.

## <a name="unassign-licenses-from-devices"></a>Desasignación de licencias de dispositivos

Cuando desasignas licencias de un grupo, quitas las licencias de todos los dispositivos del grupo. A continuación, todas las aplicaciones y sus datos asociados son de solo lectura.

1. En el centro de administración, vaya a la página  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licencias de</a> facturación.
2. En la **página Licencias,** elija Aplicaciones de **Microsoft 365** para educación (dispositivo) o Aplicaciones de **Microsoft 365** para empresas (dispositivo).
3. En la página siguiente, elija una suscripción, elija **Más acciones** y, a continuación, **desasigne licencias.**
4. En el **cuadro de diálogo Desasignación** de licencias, elija **Unassign**.