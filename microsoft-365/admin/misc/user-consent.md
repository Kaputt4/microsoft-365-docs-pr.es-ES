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
description: Obtenga información sobre el consentimiento del usuario para las aplicaciones y cómo activarlas para permitir que las aplicaciones de terceros accedan a la información de Microsoft 365 de los usuarios.
ms.openlocfilehash: 955ae9e58c14dbb8012a440ef6c336f44b0760a4
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999588"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Administración del consentimiento del usuario para aplicaciones en Microsoft 365

Esta configuración controla si los usuarios pueden dar ese consentimiento a las aplicaciones que usan OpenID Connect y OAuth 2.0 para el inicio de sesión y las solicitudes de acceso a los datos. Una aplicación se puede crear desde dentro de su propia organización, o puede ser de otra organización de Office 365 o de un tercero.

Si activas esta configuración, esas aplicaciones pedirán permiso a los usuarios para acceder a los datos de la organización y los usuarios podrán elegir si desea permitirlo. Si desactivas esta configuración, los administradores deben dar su consentimiento a esas aplicaciones antes de que los usuarios puedan usarlas. En este caso, considere la posibilidad de configurar un flujo de trabajo de consentimiento de administrador en Azure Portal para que los usuarios puedan enviar una solicitud de aprobación de administrador para usar cualquier aplicación bloqueada.

Un usuario puede dar acceso sólo a las aplicaciones que acceden a su información Office 365. No se puede dar acceso a una aplicación a otra información del usuario.

## <a name="turning-user-consent-on-or-off"></a>Activar o desactivar el consentimiento del usuario
<a name="__toc379982114"> </a>

Aquí te explicamos cómo activar o desactivar el consentimiento del usuario para las aplicaciones.

1. En el centro de administración, vaya a la **página** Servicios de configuración de la organización de configuración y, a continuación, seleccione Consentimiento del usuario \>   >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743) para **las aplicaciones.**

2. En la **página Consentimiento del usuario para aplicaciones,** seleccione la opción para activar o desactivar el consentimiento del usuario.

## <a name="more-info"></a>Más información
<a name="__toc379982114"> </a>

Para obtener información sobre cómo configurar las opciones de consentimiento en Azure Active Directory, lea Configurar el flujo de [trabajo de consentimiento de administrador.](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow)

Para obtener información sobre cómo administrar el consentimiento del usuario a las aplicaciones, lea Administrar el consentimiento a las [aplicaciones y evaluar las solicitudes de consentimiento.](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests)