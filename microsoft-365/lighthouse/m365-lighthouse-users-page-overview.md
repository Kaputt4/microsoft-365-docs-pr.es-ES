---
title: Microsoft 365 Lighthouse de la página Usuarios
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre la página Usuarios.
ms.openlocfilehash: fad5ff4b41b43efb68c7e230401b80e50cea95a4
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63329945"
---
# <a name="microsoft-365-lighthouse-users-page-overview"></a>Microsoft 365 Lighthouse de la página Usuarios 

Microsoft 365 Lighthouse permite administrar usuarios en cuentas de inquilino de clientes seleccionando **Usuarios** en el panel de navegación izquierdo para abrir la página Usuarios. Desde esta página, puede buscar usuarios y evaluar y actuar en función del estado de seguridad de sus cuentas de usuario. También puede ver información sobre usuarios arriesgados y el estado de la autenticación multifactor y el restablecimiento de contraseñas de autoservicio.  
  
## <a name="search-users-tab"></a>Pestaña Buscar usuarios  
  
Desde la pestaña Buscar usuarios, puede buscar rápidamente en los inquilinos usuarios específicos y realizar acciones básicas de administración de usuarios, como restablecer una contraseña de cuenta.

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-search-users-tab.png" alt-text="Captura de pantalla de la pestaña Buscar usuarios.":::

## <a name="risky-users-tab"></a>Pestaña Usuarios arriesgados

La pestaña Usuarios riesgosos muestra las cuentas de usuario de los inquilinos que se han marcado para un comportamiento de riesgo. Seleccione cualquiera de los usuarios para ver más información sobre un riesgo detectado o para mitigar un riesgo mediante el restablecimiento de la contraseña de un usuario o el bloqueo del inicio de sesión. Para obtener más información acerca de los tipos de riesgo y la detección, vea [¿Qué es el riesgo?](/azure/active-directory/identity-protection/concept-identity-protection-risks).

La pestaña Usuarios riesgosos también incluye las siguientes opciones:
- **Exportar:** Seleccione esta opción para exportar datos de cumplimiento de dispositivos a Excel de valores separados por comas (.csv).
- **Actualizar:** Selecciona para recuperar los datos de cumplimiento del dispositivo más actuales.
- **Confirme que los usuarios están en peligro:** Seleccione esta opción para confirmar que el usuario está en peligro.
- **Descartar el riesgo de usuario:** Seleccione para descartar el riesgo de usuario.  
- **Restablecer contraseña:** Seleccione para cambiar o restablecer la contraseña de usuario.
- **Bloquear inicio de sesión:** Seleccione esta opción para impedir que alguien inicie sesión como este usuario.

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-risky-users-tab.png" alt-text="Captura de pantalla de la pestaña Usuarios arriesgados.":::

## <a name="multifactor-authentication-tab"></a>Ficha Autenticación multifactor

La pestaña Autenticación multifactor proporciona información detallada sobre el estado de la habilitación de autenticación multifactor (MFA) en los inquilinos. Seleccione cualquier inquilino de la lista para ver más detalles sobre ese inquilino, incluidas las directivas de acceso condicional que requieren MFA ya configuradas y qué usuarios aún no se han registrado para MFA.

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-mfa-tab.png" alt-text="Captura de pantalla de la pestaña Autenticación multifactor.":::

## <a name="password-reset-tab"></a>Pestaña Restablecimiento de contraseña

La pestaña restablecimiento de contraseñas muestra información detallada sobre el estado de la habilitación de restablecimiento de contraseñas de autoservicio en todos los inquilinos. También proporciona información sobre los usuarios que están habilitados pero que aún necesitan registrarse para poder restablecer su contraseña por su cuenta.

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-password-reset-tab.png" alt-text="Captura de pantalla de la pestaña restablecimiento de contraseña.":::

## <a name="related-content"></a>Contenido relacionado

[Microsoft 365 Lighthouse de la página de cumplimiento de dispositivos](m365-lighthouse-device-compliance-page-overview.md) (artículo)\
[Microsoft 365 Lighthouse preguntas más frecuentes](m365-lighthouse-faq.yml) (artículo)
