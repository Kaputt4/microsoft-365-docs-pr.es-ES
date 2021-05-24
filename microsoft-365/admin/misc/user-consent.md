---
title: Administración del consentimiento del usuario para aplicaciones en Microsoft 365
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
description: Obtén información sobre el consentimiento de los usuarios a las aplicaciones y cómo activarlas para permitir que las aplicaciones de terceros accedan a la información Microsoft 365 usuarios.
ms.openlocfilehash: b8f65b50e50b0e0b4d978388463bbd380ca60d4e
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624506"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Administración del consentimiento del usuario para aplicaciones en Microsoft 365

Esta configuración controla si los usuarios pueden dar ese consentimiento a las aplicaciones que usan OpenID Conectar y OAuth 2.0 para el inicio de sesión y las solicitudes de acceso a los datos. Una aplicación se puede crear desde dentro de su propia organización, o puede venir de otra Office 365 organización o de un tercero.

Si activas esta configuración, esas aplicaciones pedirán a los usuarios permiso para acceder a los datos de la organización y los usuarios pueden elegir si se permiten. Si desactivas esta configuración, los administradores deben dar su consentimiento a dichas aplicaciones antes de que los usuarios puedan usarlas. En este caso, considere la posibilidad de configurar un flujo de trabajo de consentimiento de administrador en Azure Portal para que los usuarios puedan enviar una solicitud de aprobación de administrador para usar cualquier aplicación bloqueada.

Un usuario puede dar acceso sólo a las aplicaciones que acceden a su información Office 365. No se puede dar acceso a una aplicación a otra información del usuario.

## <a name="turning-user-consent-on-or-off"></a>Activar o desactivar el consentimiento del usuario
<a name="__toc379982114"> </a>

Este es el modo de activar o desactivar el consentimiento del usuario para las aplicaciones.

1. En el Centro de administración, vaya a la **página Configuración** Configuración de la organización \>   >  [y,](https://go.microsoft.com/fwlink/p/?linkid=2053743) a continuación, seleccione **Consentimiento del** usuario para aplicaciones .

2. En la **página Consentimiento de usuario para aplicaciones,** seleccione la opción para activar o desactivar el consentimiento del usuario.

## <a name="related-content"></a>Contenido relacionado 
<a name="__toc379982114"> </a>

[Configurar el flujo de trabajo de consentimiento de administrador](/azure/active-directory/manage-apps/configure-admin-consent-workflow) (artículo)\
[Administrar el consentimiento a las aplicaciones y evaluar las solicitudes de consentimiento](/azure/active-directory/manage-apps/manage-consent-requests) (artículo)