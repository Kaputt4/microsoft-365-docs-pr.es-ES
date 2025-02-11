---
title: Información general de la página Usuarios de Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms.reviewer: ragovind
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: En el caso de los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre la página Usuarios.
ms.openlocfilehash: ebf4fd001fca207704e8e7656759552f91219396
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68736307"
---
# <a name="overview-of-the-users-page-in-microsoft-365-lighthouse"></a>Información general de la página Usuarios de Microsoft 365 Lighthouse 

Microsoft 365 Lighthouse permite administrar usuarios en cuentas de inquilino de clientes seleccionando cualquiera de los vínculos en **Usuarios** en el panel de navegación izquierdo. En la página Usuarios, puede buscar usuarios y evaluar y actuar sobre el estado de seguridad de las cuentas de usuario. También puede ver información sobre los usuarios de riesgo y el estado de la autenticación multifactor y el autoservicio de restablecimiento de contraseña.  
  
## <a name="account-management-page"></a>Página de administración de cuentas  
  
En la página Administración de cuentas, puede buscar rápidamente usuarios específicos en los inquilinos y realizar tareas comunes de administración de usuarios, como actualizar la información de la cuenta de usuario, restablecer contraseñas, asignar licencias y administrar grupos, buzones de correo o OneDrive de un usuario. También puede ver cuentas inactivas, realizar las acciones de seguridad adecuadas y reclamar licencias sin usar.

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-search-users-tab.png" alt-text="Captura de pantalla de la página Buscar y usuarios inactivos.":::

## <a name="risky-users-page"></a>Página Usuarios de riesgo

En la página Usuarios de riesgo se muestran las cuentas de usuario de los inquilinos que se han marcado como comportamientos de riesgo. Seleccione cualquiera de los usuarios para ver más información sobre un riesgo detectado o para mitigar un riesgo mediante el restablecimiento de la contraseña de un usuario o el bloqueo del inicio de sesión. Para obtener más información sobre los tipos de riesgo y la detección, consulte [¿Qué es el riesgo?](/azure/active-directory/identity-protection/concept-identity-protection-risks).

La página Usuarios de riesgo también incluye las siguientes opciones:
- **Exportar:** Seleccione esta opción para exportar los datos de cumplimiento de dispositivos a un archivo de valores separados por comas (.csv) de Excel.
- **Actualizar:** Seleccione esta opción para recuperar los datos de cumplimiento de dispositivos más actuales.
- **Confirme que los usuarios están en peligro:** Seleccione esta opción para confirmar que el usuario está en peligro.
- **Descartar el riesgo de los usuarios:** Seleccione esta opción para descartar el riesgo del usuario.  
- **Restablecer contraseña:** Seleccione esta opción para cambiar o restablecer la contraseña de usuario.
- **Bloquear inicio de sesión:** Seleccione esta opción para evitar que nadie inicie sesión como este usuario.

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-risky-users-tab.png" alt-text="Captura de pantalla de la página Usuarios de riesgo.":::

## <a name="multifactor-authentication-page"></a>Página Autenticación multifactor

La página Autenticación multifactor proporciona información detallada sobre el estado de la habilitación de la autenticación multifactor (MFA) en los inquilinos. Seleccione cualquier inquilino de la lista para ver más detalles para ese inquilino, incluidas las directivas de acceso condicional que requieren MFA ya configuradas y qué usuarios aún no se han registrado para MFA.

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-mfa-tab.png" alt-text="Captura de pantalla de la página Autenticación multifactor.":::

## <a name="password-reset-page"></a>Página de restablecimiento de contraseña

La página Restablecimiento de contraseña muestra información detallada sobre el estado de la habilitación del autoservicio de restablecimiento de contraseña en los inquilinos. También proporciona información sobre los usuarios que están habilitados pero que todavía necesitan registrarse para poder restablecer su contraseña por sí mismos.

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-password-reset-tab.png" alt-text="Captura de pantalla de la página Restablecimiento de contraseña.":::

## <a name="related-content"></a>Contenido relacionado

[Microsoft 365 Lighthouse información general de la página de cumplimiento de](m365-lighthouse-device-compliance-page-overview.md) dispositivos (artículo)\
[Preguntas más frecuentes sobre Microsoft 365 Lighthouse](m365-lighthouse-faq.yml) (artículo)
