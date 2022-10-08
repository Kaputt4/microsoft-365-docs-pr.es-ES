---
title: Administración del consentimiento del usuario a aplicaciones en Microsoft 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: Obtenga información sobre el consentimiento del usuario a las aplicaciones y cómo activarlas para permitir que las aplicaciones de terceros accedan a la información de Microsoft 365 de los usuarios.
ms.openlocfilehash: 66cfd821f51624790b6c1e73e0d156da6dfd2380
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68204747"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Administración del consentimiento del usuario a aplicaciones en Microsoft 365

Esta configuración controla si los usuarios pueden dar ese consentimiento a las aplicaciones que usan OpenID Connect y OAuth 2.0 para el inicio de sesión y las solicitudes de acceso a los datos. Una aplicación se puede crear desde dentro de su propia organización o puede provenir de otra organización Office 365 o de un tercero.

Si activa esta configuración, esas aplicaciones pedirán permiso a los usuarios para acceder a los datos de la organización y los usuarios pueden elegir si lo permiten. Si desactiva esta configuración, los administradores deben dar su consentimiento a esas aplicaciones antes de que los usuarios puedan usarlas. En este caso, considere la posibilidad de configurar un flujo de trabajo de consentimiento del administrador en el Azure Portal para que los usuarios puedan enviar una solicitud de aprobación de administrador para usar cualquier aplicación bloqueada.

Un usuario puede dar acceso sólo a las aplicaciones que acceden a su información Office 365. No se puede dar acceso a una aplicación a otra información del usuario.

## <a name="turning-user-consent-on-or-off"></a>Activar o desactivar el consentimiento del usuario

A continuación se muestra cómo activar o desactivar el consentimiento del usuario para las aplicaciones.

1. En el Centro de administración, vaya a la página **Configuración** \>[servicios](https://go.microsoft.com/fwlink/p/?linkid=2053743) de configuración  >  de **la organización** y, a continuación, seleccione **Consentimiento del usuario para las aplicaciones**.

2. En la página **Consentimiento del usuario para las aplicaciones** , seleccione la opción para activar o desactivar el consentimiento del usuario.

## <a name="related-content"></a>Contenido relacionado 

[Configuración del flujo de trabajo de consentimiento del administrador](/azure/active-directory/manage-apps/configure-admin-consent-workflow) (artículo)\
[Administración del consentimiento para aplicaciones y evaluación de solicitudes de consentimiento](/azure/active-directory/manage-apps/manage-consent-requests) (artículo)