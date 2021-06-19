---
title: Detectar y corregir las concesiones ilegales de consentimiento
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: Obtenga información sobre cómo reconocer y corregir el ataque de concesión de consentimientos ilícitos en Microsoft Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4c3c3c06974feb2dab3985a60938fe7d543543c3
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028924"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>Detectar y corregir las concesiones ilegales de consentimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Resumen**  Obtenga información sobre cómo reconocer y corregir el ataque de concesión de consentimientos ilícitos en Office 365.

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>¿Cuál es el ataque de concesión de consentimiento ilegal en Office 365?

En un ataque de concesión de consentimiento ilegal, el atacante crea una aplicación registrada en Azure que solicita acceso a datos como información de contacto, correo electrónico o documentos. A continuación, el atacante hace un truco al usuario final para conceder a esa aplicación el consentimiento para acceder a sus datos a través de un ataque de suplantación de identidad (phishing) o mediante la inyección de código ilícito en un sitio web de confianza. Una vez que se ha concedido el consentimiento a la aplicación ilícita, tiene acceso a los datos a nivel de cuenta sin necesidad de una cuenta organizativa. Los pasos normales de corrección, como restablecer contraseñas para cuentas vulneradas o requerir autenticación multifactor (MFA) en las cuentas, no son efectivos contra este tipo de ataque, ya que son aplicaciones de terceros y son externas a la organización.

Estos ataques aprovechan un modelo de interacción que supone que la entidad que llama a la información es la automatización y no un ser humano.

> [!IMPORTANT]
> ¿Sospecha que está experimentando problemas con las concesiones de consentimiento ilegales de una aplicación en este momento? Microsoft Cloud App Security (MCAS) tiene herramientas para detectar, investigar y corregir las aplicaciones de OAuth. Este artículo de MCAS tiene un tutorial que describe cómo investigar aplicaciones [de OAuth arriesgadas.](/cloud-app-security/investigate-risky-oauth) También puedes establecer directivas de [aplicación de OAuth](/cloud-app-security/app-permission-policy) para investigar los permisos solicitados por la aplicación, qué usuarios autorizan estas aplicaciones y aprobar o prohibir ampliamente estas solicitudes de permisos.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>¿Cómo es un ataque de concesión de consentimiento ilegal en Office 365?

Debe buscar en el registro de **auditoría** para encontrar signos, también denominados Indicadores de compromiso (IOC) de este ataque. Para las organizaciones con muchas aplicaciones registradas en Azure y una gran base de usuarios, el procedimiento recomendado es revisar las concesiones de consentimiento de las organizaciones cada semana.

### <a name="steps-for-finding-signs-of-this-attack"></a>Pasos para encontrar signos de este ataque

1. Abra el **portal Microsoft 365 Defender** en <https://security.microsoft.com> .

2. Vaya a **Buscar y** seleccione Búsqueda de registro **de auditoría.**

3. Busque (todas las actividades y todos los usuarios) y escriba la fecha de inicio y la fecha de finalización si es necesario y, a continuación, haga clic en **Buscar**.

4. Haga **clic en Filtrar resultados** y escriba Consentimiento para la aplicación en el **campo** Actividad.

5. Haga clic en el resultado para ver los detalles de la actividad. Haga **clic en Más información** para obtener detalles de la actividad. Compruebe si IsAdminContent está establecido en True.

> [!NOTE]
>
> La entrada del registro de auditoría correspondiente puede tardar entre 30 minutos y 24 horas en mostrarse en los resultados de búsqueda después de que se produzca un evento.
>
> El tiempo durante el que se conserva y se puede buscar un registro de auditoría en el registro de auditoría depende de la suscripción Microsoft 365 y, específicamente, del tipo de licencia asignada a un usuario específico. Para obtener más información, vea [Registro de auditoría](../../compliance/search-the-audit-log-in-security-and-compliance.md).
>
> Si este valor es true, indica que alguien con acceso de administrador global puede haber concedido un amplio acceso a los datos. Si esto es inesperado, siga los pasos [necesarios para confirmar un ataque](#how-to-confirm-an-attack).

## <a name="how-to-confirm-an-attack"></a>Cómo confirmar un ataque

Si tiene una o más instancias de los IIC enumerados anteriormente, debe realizar una investigación adicional para confirmar positivamente que se produjo el ataque. Puedes usar cualquiera de estos tres métodos para confirmar el ataque:

- Aplicaciones de inventario y sus permisos mediante el portal Azure Active Directory web. Este método es exhaustivo, pero solo puede comprobar un usuario a la vez, lo que puede llevar mucho tiempo si tiene muchos usuarios que comprobar.

- Aplicaciones de inventario y sus permisos con PowerShell. Este es el método más rápido y exhaustivo, con la menor cantidad de sobrecarga.

- Haga que los usuarios comprueben individualmente sus aplicaciones y permisos e informen los resultados a los administradores para que los solucionen.

## <a name="inventory-apps-with-access-in-your-organization"></a>Inventario de aplicaciones con acceso en la organización

Puede hacerlo para los usuarios con el portal de Azure Active Directory o PowerShell o hacer que los usuarios enumeren individualmente su acceso a la aplicación.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Pasos para usar el Azure Active Directory Portal

Puede buscar las aplicaciones a las que cualquier usuario individual ha concedido permisos mediante [el Azure Active Directory Portal](https://portal.azure.com/).

1. Inicie sesión en Azure Portal con derechos administrativos.

2. Seleccione la hoja Azure Active Directory hoja.

3. Seleccione **Usuarios**.

4. Seleccione el usuario que desea revisar.

5. Seleccione **Aplicaciones**.

Esto te mostrará las aplicaciones asignadas al usuario y los permisos que tienen las aplicaciones.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>Pasos para que los usuarios enumeren su acceso a la aplicación

Haga que los usuarios vayan y https://myapps.microsoft.com revisen su propio acceso a la aplicación allí. Deben poder ver todas las aplicaciones con acceso, ver detalles sobre ellas (incluido el ámbito de acceso) y poder revocar privilegios a aplicaciones sospechosas o ilícitas.

### <a name="steps-for-doing-this-with-powershell"></a>Pasos para hacerlo con PowerShell

La forma más sencilla de comprobar el ataque de concesión ilegal de consentimiento es ejecutar [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), que volcará todas las concesiones de consentimiento de OAuth y las aplicaciones de OAuth para todos los usuarios de su arrendamiento en un archivo .csv.

#### <a name="pre-requisites"></a>Requisitos previos

- La biblioteca de PowerShell de Azure AD instalada.

- Derechos de administrador global en el inquilino en el que se ejecutará el script.

- Administrador local en el equipo desde el que se ejecutarán los scripts.

> [!IMPORTANT]
> Se ***recomienda encarecidamente*** que necesite autenticación multifactor en su cuenta administrativa. Este script admite la autenticación MFA.

1. Inicie sesión en el equipo desde el que ejecutará el script con derechos de administrador local.

2. Descargue o copie el script [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) de GitHub a una carpeta desde la que ejecutará el script. Esta será la misma carpeta en la que se escribirá el archivo "permissions.csv" de salida.

3. Abra una instancia de PowerShell como administrador y abra la carpeta en la que guardó el script.

4. Conectar a su directorio mediante el cmdlet [Conectar-AzureAD.](/powershell/module/azuread/connect-azuread)

5. Ejecute este comando de PowerShell:

   ```powershell
   .\Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

El script genera un archivo denominado Permissions.csv. Siga estos pasos para buscar concesiones de permisos de aplicación ilegales:

1. En la columna ConsentType (columna G) busque el valor "AllPrinciples". El permiso AllPrincipals permite a la aplicación cliente obtener acceso al contenido de todos los usuarios del arrendamiento. Las Microsoft 365 nativas necesitan este permiso para funcionar correctamente. Todas las aplicaciones que no sean de Microsoft con este permiso deben revisarse detenidamente.

2. En la columna Permiso (columna F) revise los permisos que cada aplicación delegada tiene para el contenido. Busque el permiso "Lectura" y "Escritura" o "*. All" permiso y revisar estos cuidadosamente porque puede que no sean adecuados.

3. Revise los usuarios específicos que tienen los consentimientos concedidos. Si los usuarios de alto perfil o de alto impacto tienen consentimientos inadecuados concedidos, debe investigar más a fondo.

4. En la columna ClientDisplayName (columna C) busque aplicaciones que parezcan sospechosas. Las aplicaciones con nombres mal escritos, nombres super bland o nombres de sonido de hacker deben revisarse cuidadosamente.

## <a name="determine-the-scope-of-the-attack"></a>Determinar el ámbito del ataque

Una vez que haya terminado de realizar el inventario del acceso a la aplicación, revise el registro de **auditoría** para determinar el ámbito completo de la infracción. Busque en los usuarios afectados, los períodos de tiempo a los que la aplicación ilícita tuvo acceso a su organización y los permisos que tenía la aplicación. Puede buscar en el registro **de auditoría** en el [Microsoft 365 Defender](../../compliance/search-the-audit-log-in-security-and-compliance.md).

> [!IMPORTANT]
> [La auditoría de buzones](../../compliance/enable-mailbox-auditing.md) de correo y la auditoría de actividad para administradores y usuarios deben estar [habilitadas](../../compliance/turn-audit-log-search-on-or-off.md) antes del ataque para que pueda obtener esta información.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>Cómo detener y corregir un ataque de concesión de consentimiento ilegal

Después de identificar una aplicación con permisos ilícitos, tiene varias formas de quitar ese acceso.

- Puede revocar el permiso de la aplicación en el portal de Azure Active Directory mediante:

  - Vaya al usuario afectado en la **hoja Azure Active Directory Usuario.**

  - Seleccione **Aplicaciones**.

  - Seleccione la aplicación ilícita.

  - Haga **clic en** Quitar en el desglose.

- Puede revocar la concesión de consentimiento de OAuth con PowerShell siguiendo los pasos descritos en [Remove-AzureADOAuth2PermissionGrant](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).

- Puede revocar la asignación de roles de aplicación de servicio con PowerShell siguiendo los pasos descritos en [Remove-AzureADServiceAppRoleAssignment](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).

- También puedes deshabilitar el inicio de sesión para la cuenta afectada por completo, lo que a su vez deshabilitará el acceso de la aplicación a los datos de esa cuenta. Esto no es ideal para la productividad del usuario final, por supuesto, pero si está trabajando para limitar el impacto rápidamente, puede ser una corrección viable a corto plazo.

- Puede desactivar las aplicaciones integradas para su arrendamiento. Este es un paso drástico que deshabilita la posibilidad de que los usuarios finales concedan su consentimiento en todo el espacio empresarial. Esto evita que los usuarios concedan acceso a una aplicación malintencionada de forma involuntaria. Esto no es muy recomendable, ya que afecta gravemente la capacidad de los usuarios para ser productivos con aplicaciones de terceros. Para ello, siga los pasos descritos en Activar o desactivar aplicaciones [integradas.](../../admin/misc/user-consent.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Proteger Microsoft 365 como un profesional de la ciberseguridad

Su suscripción a Microsoft 365 incluye un potente conjunto de capacidades de seguridad que puede usar para proteger sus datos y los usuarios. Use el [Plan de seguridad de Microsoft 365: principales prioridades para los primeros 30 días, 90 días y en adelante](security-roadmap.md) para implementar las prácticas recomendadas de Microsoft para proteger su espacio empresarial de Microsoft 365.

- Tareas a realizar en los primeros 30 días. Estas tienen un efecto inmediato y de bajo impacto para los usuarios.

- Tareas para llevar a cabo en 90 días. Estas tareas necesitan un poco más de tiempo para planearlas e implementarlas, pero mejoran considerablemente el nivel de seguridad.

- Más de 90 días. Estas mejoras se crean en el trabajo de los 90 primeros días.

## <a name="see-also"></a>Vea también:

- [Una aplicación inesperada en la lista de](/azure/active-directory/application-access-unexpected-application) aplicaciones guía a los administradores a través de varias acciones que pueden querer realizar después de darse cuenta de que hay aplicaciones inesperadas con acceso a datos.

- [La integración de aplicaciones Azure Active Directory](/azure/active-directory/active-directory-apps-permissions-consent) es una introducción de alto nivel de permisos y consentimientos.

- [Los problemas de desarrollo de mi aplicación](/azure/active-directory/active-directory-application-dev-development-content-map) proporcionan vínculos a diversos artículos relacionados con el consentimiento.

- Los objetos de entidad de seguridad de aplicación y servicio [de Azure Active Directory (Azure AD)](/azure/active-directory/develop/active-directory-application-objects) proporcionan una introducción a los objetos de entidad de seguridad de aplicación y servicio que son esenciales para el modelo de aplicaciones.

- [Administrar el acceso a las aplicaciones](/azure/active-directory/active-directory-managing-access-to-apps) es una introducción a las capacidades que los administradores tienen para administrar el acceso de los usuarios a las aplicaciones.
