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
description: Obtenga información sobre cómo asignar licencias a grupos para su uso con dispositivos.
ms.custom:
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
ms.openlocfilehash: a316810e3e6ddb1373697dc56b2fccb5a32cf0b1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911487"
---
# <a name="manage-licenses-for-devices"></a>Administrar licencias para dispositivos

Si tienes Aplicaciones de Microsoft 365 para empresas (dispositivo) o Aplicaciones de Microsoft 365 para Educación (dispositivo), puedes asignar licencias a dispositivos mediante grupos de Azure AD. Cuando un dispositivo tiene una licencia, cualquier persona que use ese dispositivo puede usar Aplicaciones de Microsoft 365 para empresas (anteriormente denominada Office 365 ProPlus). Por ejemplo, supongamos que tiene 20 portátiles y tabletas que usan los usuarios de su organización. Cuando asignas una licencia a cada dispositivo, cada persona que inicia sesión en uno de los dispositivos usa Aplicaciones de Microsoft 365 para empresas sin necesidad de su propia licencia.

> [!IMPORTANT]
> Las licencias basadas en dispositivos para Aplicaciones de Microsoft 365 para empresas solo están disponibles como una licencia de complemento para algunos clientes comerciales y algunos clientes de educación. Para los clientes comerciales, la licencia es Aplicaciones de *Microsoft 365* para empresas (dispositivo) y solo está disponible a través de Contrato Enterprise/Contrato Enterprise suscripción. Para los clientes de educación, la licencia es Aplicaciones de *Microsoft 365* para educación (dispositivo) y solo está disponible a través de Enrollment for Education Solutions (EES). Para obtener más información, lea la entrada de blog sobre [disponibilidad educativa](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/). Para obtener disponibilidad comercial, póngase en contacto con el representante de la cuenta microsoft.

Para empezar, cree un grupo en el Centro de administración de Azure Active Directory y, a continuación, asigne dispositivos al grupo. Para obtener más información sobre las licencias de dispositivos, incluidos los requisitos de dispositivo, qué tipos de grupos puede usar y cómo configurar Aplicaciones de Microsoft 365 para empresas para que usen licencias de dispositivos, consulte Licencias basadas en dispositivos para Aplicaciones de [Microsoft 365](/deployoffice/device-based-licensing)para empresas.

> [!IMPORTANT]
> Debe ser un administrador global para completar las tareas de este artículo.

## <a name="assign-licenses-to-devices"></a>Asignar licencias a dispositivos

Al asignar licencias a un grupo, se asignan licencias a todos los dispositivos del grupo. Solo puede asignar una suscripción a cualquier grupo.

1. En el Centro de administración de Microsoft 365, vaya a la página **Licencias**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">de</a> facturación.
2. En la **página Licencias,** elija Aplicaciones de **Microsoft 365** para Educación (dispositivo) o Aplicaciones de **Microsoft 365 para empresas (dispositivo).**
3. En la página siguiente, elija una suscripción y, a continuación, **elija Asignar licencias.**
4. En el panel Asignar licencias a un grupo, empiece a escribir un nombre de grupo y, a continuación, elija en los **resultados** para agregarlo a la lista.
5. Elija **Asignar** y, a continuación, **seleccione Cerrar**.

## <a name="unassign-licenses-from-devices"></a>Unassign licenses from devices

Cuando se quitan las licencias de un grupo, se quitan las licencias de todos los dispositivos del grupo. A continuación, todas las aplicaciones y sus datos asociados son de solo lectura.

1. En el Centro de administración, vaya a la página **Licencias**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">de</a> facturación.
2. En la **página Licencias,** elija Aplicaciones de **Microsoft 365** para Educación (dispositivo) o Aplicaciones de **Microsoft 365 para empresas (dispositivo).**
3. En la página siguiente, elija una suscripción, elija **Más acciones** y, a continuación, **elija Unassign licenses**.
4. En el **cuadro de diálogo Unassign licenses,** elija **Unassign**.