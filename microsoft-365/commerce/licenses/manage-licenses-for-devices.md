---
title: Administrar licencias para dispositivos
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: shegu, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
description: Obtenga información sobre cómo asignar licencias a grupos para su uso con dispositivos.
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_licensing
search.appverid: MET150
ms.date: 03/17/2021
ms.openlocfilehash: c590c2d47699c4c3cbea4b5145bea9e7c9fc79ec
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535667"
---
# <a name="manage-licenses-for-devices"></a>Administrar licencias para dispositivos

Si tienes Aplicaciones Microsoft 365 para empresas (dispositivo) o Aplicaciones Microsoft 365 para Educación (dispositivo), puedes asignar licencias a dispositivos mediante grupos de Azure AD. Cuando un dispositivo tiene una licencia, cualquier persona que use ese dispositivo puede usar Aplicaciones Microsoft 365 para empresas (anteriormente denominado Office 365 ProPlus). Por ejemplo, supongamos que tiene 20 portátiles y tabletas que usan los usuarios de su organización. Cuando asignas una licencia a cada dispositivo, cada persona que inicia sesión en uno de los dispositivos usa Aplicaciones Microsoft 365 para empresas sin necesidad de su propia licencia.

> [!IMPORTANT]
> Las licencias basadas en dispositivos Aplicaciones Microsoft 365 para empresas solo están disponibles como una licencia de complemento para algunos clientes comerciales y algunos clientes de educación. Para los clientes comerciales, la licencia *Aplicaciones Microsoft 365 para empresas (dispositivo)* y solo está disponible a través Enterprise Agreement/Enterprise Agreement suscripción. Para los clientes de educación, la *licencia Aplicaciones Microsoft 365 educación (dispositivo)* y solo está disponible a través de Enrollment for Education Solutions (EES). Para obtener más información, lea la entrada de blog sobre [disponibilidad educativa](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education). Para obtener disponibilidad comercial, póngase en contacto con el representante de la cuenta microsoft.

Para empezar, creas un grupo en el centro Azure Active Directory administración y, a continuación, asignas dispositivos al grupo. Para obtener más información sobre las licencias de dispositivos, incluidos los requisitos de dispositivo, los tipos de grupos que puedes usar y cómo configurar Aplicaciones Microsoft 365 para empresas para usar licencias de dispositivos, consulta Licencias basadas en dispositivos [para Aplicaciones Microsoft 365 para empresas](/deployoffice/device-based-licensing).

> [!IMPORTANT]
> Debe ser un administrador global para completar las tareas de este artículo.

## <a name="assign-licenses-to-devices"></a>Asignar licencias a dispositivos

Al asignar licencias a un grupo, se asignan licencias a todos los dispositivos del grupo. Solo puede asignar una suscripción a cualquier grupo.

1. En el centro Microsoft 365 administración, vaya a la página **Licencias**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">de</a> facturación.
2. En la **página Licencias,** elija **Aplicaciones Microsoft 365 educación (dispositivo)** **o Aplicaciones Microsoft 365 para empresas (dispositivo).**
3. En la página siguiente, elija una suscripción y, a continuación, **elija Asignar licencias.**
4. En el panel Asignar licencias a un grupo, empiece a escribir un nombre de grupo y, a continuación, elija en los **resultados** para agregarlo a la lista.
5. Elija **Asignar** y, a continuación, **seleccione Cerrar**.

## <a name="unassign-licenses-from-devices"></a>Unassign licenses from devices

Cuando se quitan las licencias de un grupo, se quitan las licencias de todos los dispositivos del grupo. A continuación, todas las aplicaciones y sus datos asociados son de solo lectura.

1. En el Centro de administración, vaya a la página **Licencias**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">de</a> facturación.
2. En la **página Licencias,** elija **Aplicaciones Microsoft 365 educación (dispositivo)** **o Aplicaciones Microsoft 365 para empresas (dispositivo).**
3. En la página siguiente, elija una suscripción, seleccione los tres puntos (más acciones) y, a continuación, elija **Unassign licenses**.
4. En el **cuadro de diálogo Unassign licenses,** elija **Unassign**.
