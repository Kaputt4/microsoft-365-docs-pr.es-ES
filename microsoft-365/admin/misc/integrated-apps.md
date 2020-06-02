---
title: Administrar el consentimiento del usuario para las aplicaciones en Microsoft 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: Obtenga información sobre el consentimiento del usuario para las aplicaciones y cómo activarlas para permitir que las aplicaciones de terceros obtengan acceso a la información de Microsoft 365 de los usuarios.
ms.openlocfilehash: df81d2cf3e1d796e462d2b9240b8288273ed5372
ms.sourcegitcommit: ff1af42b036bfdf75729db8c78f10cf4642616ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "44477177"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Administrar el consentimiento del usuario para las aplicaciones en Microsoft 365

Esta configuración controla si los usuarios pueden dar ese consentimiento a las aplicaciones que usan OpenID Connect y OAuth 2,0 para iniciar sesión y solicitar el acceso a los datos. Una aplicación se puede crear desde dentro de su propia organización o puede provenir de otra organización de Office 365 o de un tercero.

Si activa esta configuración, esas aplicaciones pedirán a los usuarios permiso para obtener acceso a los datos de su organización y los usuarios podrán elegir si lo permiten. Si desactiva esta opción, los administradores deben dar su consentimiento a esas aplicaciones antes de que los usuarios puedan usarlas. En este caso, considere la posibilidad de configurar un flujo de trabajo de consentimiento de administrador en Azure portal para que los usuarios puedan enviar una solicitud de aprobación de administrador para usar cualquier aplicación bloqueada.

Un usuario puede dar acceso sólo a las aplicaciones que acceden a su información Office 365. No se puede dar acceso a una aplicación a otra información del usuario.

## <a name="turning-user-consent-on-or-off"></a>Activar o desactivar el consentimiento del usuario
<a name="__toc379982114"> </a>

Esta es la manera de activar o desactivar el consentimiento del usuario en las aplicaciones.

1. En el centro de administración, vaya a la página **configuración** de la organización de servicios de configuración y, \> **Org settings**  >  [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) a continuación, seleccione **consentimiento del usuario para aplicaciones**.

2. En la página **consentimiento del usuario para aplicaciones** , seleccione la opción para activar o desactivar las aplicaciones integradas.

## <a name="more-info"></a>Más información
<a name="__toc379982114"> </a>

Para obtener información sobre cómo configurar las opciones de consentimiento en Azure Active Directory, consulte [configurar el flujo de trabajo de consentimiento del administrador](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow).

Para obtener información sobre cómo administrar el consentimiento del usuario para las aplicaciones, consulte [administrar el consentimiento de las aplicaciones y evaluar las solicitudes de consentimiento](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests).