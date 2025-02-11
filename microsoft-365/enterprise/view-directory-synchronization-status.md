---
title: Visualización del estado de sincronización de directorios en Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- scotvorg
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: 18be3b98-34ae-47be-9337-ab6c3fb372ac
description: En este artículo, aprenderá a comprobar el estado de la sincronización de directorios en Office 365.
ms.openlocfilehash: 2318bed115921cd2eb2d44f12822b9a94f79bd80
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68194519"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a>Visualización del estado de sincronización de directorios en Microsoft 365

Si ha integrado la Active Directory local Domain Services (AD DS) con Azure Active Directory (Azure AD) mediante la sincronización del entorno local con Microsoft 365, también puede comprobar el estado de la sincronización.
  
## <a name="view-directory-synchronization-status"></a>Ver el estado de sincronización de directorios

- Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com) y elija **Estado de DirSync** en la página principal.
- Como alternativa, puede ir a **Usuarios** \> **usuarios activos** y, en la página **Usuarios activos**, seleccione la **sincronización de Elipse** \> Directory. En el panel **Sincronización de directorios** , elija **Ir a administración de DirSync**.

## <a name="information-on-the-manage-directory-synchronization-page"></a>Información en la página Administrar sincronización de directorios

En la tabla siguiente se enumeran las características sobre las que puede obtener información en la página.
  
Si hay un problema con la sincronización de directorios, los errores también se muestran en esta página. Para obtener más información sobre los distintos errores que puede encontrar, consulte [Identificación de errores de sincronización de directorios en Microsoft 365](identify-directory-synchronization-errors.md).
  
|Elemento|Para qué sirve|
|:-----|:-----|
|**Dominios comprobados** | Número de dominios en el inquilino de Microsoft 365 que ha comprobado que posee. |
|**Dominios no comprobados** | Dominios que ha agregado, pero no comprobados. |
|**Sincronización de directorios habilitada** |Verdadero o Falso Especifica si ha habilitado la sincronización de directorios. |
|**Sincronización del directorio más reciente** | Última vez que se ejecutó la sincronización de directorios. Mostrará una advertencia y un vínculo a una herramienta de solución de problemas si la última sincronización fue hace más de tres días. |
|**Sincronización de contraseña habilitada** | Verdadero o Falso Especifica si tiene sincronización de hash de contraseña entre el entorno local y el inquilino de Microsoft 365. |
|**Última sincronización de contraseñas** | Última vez que se ejecutó la sincronización de hash de contraseña. Mostrará una advertencia y un vínculo a una herramienta de solución de problemas si la última sincronización fue hace más de tres días. |
|**Versión del cliente de sincronización de directorios** | Contiene un vínculo de descarga si se ha publicado una nueva versión de Azure AD Connect. |
|**Cuenta de servicio de sincronización de directorios** | Muestra el nombre de la cuenta de servicio de sincronización de directorios de Microsoft 365. |
|||

## <a name="monitor-synchronization-health"></a>Supervisión del estado de sincronización

En esta sección, deberá instalar a un agente de Azure AD Connect Health en cada uno de los controladores de dominio AD DS locales para supervisar su infraestructura de identidades y los servicios de sincronización proporcionados por Azure AD Connect. En el portal de Azure AD Connect Health podrá consultar la información de supervisión, y se pueden ver alertas, supervisión del rendimiento y análisis de uso, entre otros datos.

La decisión de diseño clave sobre cómo usar Azure AD Connect Health se basa en la forma en que use Azure AD Connect:

- Si usa la opción de **autenticación administrada**, vea primero [Usar Azure AD Connect Health con sincronización](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) para comprender y configurar Azure AD Connect Health.
- Si solo sincroniza los nombres de las cuentas y los grupos mediante la **autenticación federada** con Servicios de federación de Active Directory (AD FS), empiece con [Usar Azure AD Connect Health con AD FS](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) para comprender y configurar Azure AD Connect Health.

Cuando haya terminado, tendrá lo siguiente:

- El agente de Azure AD Connect Health instalado en los servidores de proveedor de identidades locales.
- En el portal de Azure AD Connect Health, se mostrará el estado actual de la infraestructura local y las actividades de sincronización con el espacio empresarial de Azure AD para su suscripción de Microsoft 365.
