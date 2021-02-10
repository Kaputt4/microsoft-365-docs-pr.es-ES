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
description: Obtenga información sobre cómo reconocer y corregir el ataque de concesión ilegal de consentimiento en Microsoft Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a1c724bb3b201e0ddf1edea4794606c7083605e8
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165444"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>Detectar y corregir las concesiones ilegales de consentimiento

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Resumen**  Obtenga información sobre cómo reconocer y corregir el ataque de concesión de consentimiento ilícito en Office 365.

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>¿Cuál es el ataque ilícito de concesión de consentimiento en Office 365?

En un ataque de concesión de consentimiento ilegal, el atacante crea una aplicación registrada en Azure que solicita acceso a datos como información de contacto, correo electrónico o documentos. A continuación, el atacante trucosa al usuario final para conceder a esa aplicación el consentimiento para acceder a sus datos a través de un ataque de suplantación de identidad o mediante la inyección de código ilícito en un sitio web de confianza. Después de conceder el consentimiento a la aplicación ilegal, tiene acceso a los datos en el nivel de cuenta sin necesidad de una cuenta organizativa. Los pasos de corrección normales, como el restablecimiento de contraseñas para cuentas vulneradas o la necesidad de autenticación multifactor (MFA) en las cuentas, no son efectivos contra este tipo de ataque, ya que se trata de aplicaciones de terceros y son externas a la organización.

Estos ataques aprovechan un modelo de interacción que supone que la entidad que llama a la información es la automatización y no una persona.

> [!IMPORTANT]
> ¿Sospeche que está experimentando problemas con concesiones de consentimiento ilegales de una aplicación en este momento? Microsoft Cloud App Security (MCAS) tiene herramientas para detectar, investigar y corregir las aplicaciones de OAuth. Este artículo de MCAS contiene un tutorial que describe cómo investigar [aplicaciones de OAuth de riesgo.](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth) También puedes establecer directivas de [aplicación de OAuth](https://docs.microsoft.com/cloud-app-security/app-permission-policy) para investigar los permisos solicitados por la aplicación, qué usuarios están autorizando estas aplicaciones y aprobar o prohibir ampliamente estas solicitudes de permisos.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>¿Qué aspecto tiene un ataque de concesión de consentimiento ilícito en Office 365?

Debe buscar en el registro **de auditoría** signos, también denominados Indicadores de peligro (IOC) de este ataque. Para las organizaciones con muchas aplicaciones registradas en Azure y una gran base de usuarios, el procedimiento recomendado es revisar las concesiones de consentimiento de las organizaciones semanalmente.

### <a name="steps-for-finding-signs-of-this-attack"></a>Pasos para encontrar signos de este ataque

1. Abra el **Centro de & cumplimiento en** <https://protection.office.com> .

2. Vaya a **Buscar y** seleccione Búsqueda del registro **de auditoría.**

3. Busque (todas las actividades y todos los usuarios) y escriba la fecha de inicio y la fecha de finalización si es necesario y, a continuación, haga clic en **Buscar.**

4. Haga **clic en Filtrar resultados** y escriba Consentimiento para la aplicación en el **campo** Actividad.

5. Haga clic en el resultado para ver los detalles de la actividad. Haga **clic en Más** información para obtener detalles de la actividad. Compruebe si IsAdminContent está establecido en True.

> [!NOTE]
>
> La entrada del registro de auditoría correspondiente puede tardar entre 30 minutos y 24 horas en mostrarse en los resultados de la búsqueda después de que se produzca un evento.
>
> El tiempo que un registro de auditoría se conserva y se puede buscar en el registro de auditoría depende de su suscripción a Microsoft 365 y, específicamente, del tipo de licencia que se asigna a un usuario específico. Para obtener más información, vea [Registro de auditoría.](../../compliance/search-the-audit-log-in-security-and-compliance.md)
>
> Si este valor es true, indica que alguien con acceso de administrador global puede haber concedido un amplio acceso a los datos. Si esto es inesperado, siga los pasos para [confirmar un ataque.](#how-to-confirm-an-attack)

## <a name="how-to-confirm-an-attack"></a>Cómo confirmar un ataque

Si tiene una o más instancias de las IIC enumeradas anteriormente, debe realizar una investigación más exhaustiva para confirmar de forma positiva que se produjo el ataque. Puedes usar cualquiera de estos tres métodos para confirmar el ataque:

- Realizar un inventario de las aplicaciones y sus permisos mediante el portal de Azure Active Directory. Este método es minucioso, pero solo puede comprobar un usuario cada vez, lo que puede llevar mucho tiempo si tiene muchos usuarios que comprobar.

- Realizar un inventario de las aplicaciones y sus permisos mediante PowerShell. Este es el método más rápido y exhaustivo, con la menor cantidad de sobrecarga.

- Haga que los usuarios comprueben individualmente sus aplicaciones y permisos e informen de los resultados a los administradores para su corrección.

## <a name="inventory-apps-with-access-in-your-organization"></a>Inventario de aplicaciones con acceso en la organización

Puede hacerlo para los usuarios con el Portal de Azure Active Directory o PowerShell o hacer que los usuarios enumeren individualmente su acceso a la aplicación.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Pasos para usar el Portal de Azure Active Directory

Puede buscar las aplicaciones a las que cualquier usuario individual ha concedido permisos mediante el [Portal de Azure Active Directory.](https://portal.azure.com/)

1. Inicie sesión en Azure Portal con derechos administrativos.

2. Seleccione la hoja de Azure Active Directory.

3. Seleccione **Usuarios**.

4. Seleccione el usuario que desea revisar.

5. Seleccione **Aplicaciones**.

Esto te mostrará las aplicaciones asignadas al usuario y los permisos que tienen las aplicaciones.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>Pasos para que los usuarios enumeren su acceso a la aplicación

Haga que los usuarios vayan y https://myapps.microsoft.com revisen su propio acceso a la aplicación allí. Deben poder ver todas las aplicaciones con acceso, ver detalles sobre ellas (incluido el ámbito de acceso) y poder revocar privilegios a aplicaciones sospechosas o ilegales.

### <a name="steps-for-doing-this-with-powershell"></a>Pasos para hacerlo con PowerShell

La forma más sencilla de comprobar el ataque de concesión ilegal de consentimiento es ejecutar [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), que volcará todas las concesiones de consentimiento de OAuth y las aplicaciones de OAuth para todos los usuarios de su arrendamiento en un archivo .csv.

#### <a name="pre-requisites"></a>Requisitos previos

- La biblioteca de PowerShell de Azure AD instalada.

- Derechos de administrador global en el inquilino en el que se ejecutará el script.

- Administrador local en el equipo desde el que se ejecutarán los scripts.

> [!IMPORTANT]
> Le ***recomendamos encarecidamente*** que requiera la autenticación multifactor en su cuenta administrativa. Este script admite la autenticación MFA.

1. Inicie sesión en el equipo desde el que ejecutará el script con derechos de administrador local.

2. Descargue o copie el [ scriptGet-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) de GitHub en una carpeta desde la que ejecutará el script. Esta será la misma carpeta en la que se escribirá el archivo de salida "permissions.csv".

3. Abra una instancia de PowerShell como administrador y abra la carpeta en la que guardó el script.

4. Conéctese al directorio con el cmdlet [Connect-AzureAD.](https://docs.microsoft.com/powershell/module/azuread/connect-azuread)

5. Ejecute este comando de PowerShell:

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

El script genera un archivo denominado Permissions.csv. Siga estos pasos para buscar concesiones de permisos de aplicación ilegales:

1. En la columna ConsentType (columna G), busque el valor "AllPrinciples". El permiso AllPrincipals permite que la aplicación cliente tenga acceso al contenido de todos los usuarios del arrendamiento. Las aplicaciones nativas de Microsoft 365 necesitan este permiso para funcionar correctamente. Todas las aplicaciones que no sean de Microsoft con este permiso deben revisarse detenidamente.

2. En la columna Permiso (columna F), revise los permisos que cada aplicación delegada tiene para el contenido. Busque los permisos "Leer" y "Escribir" o "*. Todos" y repase estos cuidadosamente porque puede que no sean adecuados.

3. Revise los usuarios específicos que tienen los consentimientos concedidos. Si los usuarios de alto perfil o de alto impacto tienen permisos inapropiados concedidos, debe investigar más.

4. En la columna ClientDisplayName (columna C), busca aplicaciones que parezcan sospechosas. Las aplicaciones con nombres mal escritos, nombres extraños o nombres de hackers deben revisarse cuidadosamente.

## <a name="determine-the-scope-of-the-attack"></a>Determinar el ámbito del ataque

Cuando haya terminado de realizar un inventario del acceso a la aplicación, revise el registro de **auditoría** para determinar el ámbito completo de la infracción. Buscar en los usuarios afectados, los plazos de tiempo a los que la aplicación ilegal tuvo acceso a la organización y los permisos que tenía la aplicación. Puede buscar el registro **de auditoría en** el Centro de seguridad y cumplimiento de Microsoft [365.](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

> [!IMPORTANT]
> [La auditoría de buzones](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) de correo y la auditoría de actividad para administradores y usuarios deben estar [habilitadas](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) antes del ataque para que pueda obtener esta información.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>Cómo detener y corregir un ataque ilegal de concesión de consentimiento

Después de identificar una aplicación con permisos ilícitos, tiene varias formas de quitar ese acceso.

- Puede revocar el permiso de la aplicación en el Portal de Azure Active Directory mediante:

  - Vaya al usuario afectado en la hoja **De usuario de Azure Active Directory.**

  - Seleccione **Aplicaciones**.

  - Seleccione la aplicación ilegal.

  - Haga **clic en** Quitar en la exploración en profundidad.

- Puede revocar la concesión de consentimiento de OAuth con PowerShell siguiendo los pasos de [Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).

- Puede revocar la asignación de roles de aplicación de servicio con PowerShell siguiendo los pasos descritos en [Remove-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).

- También puedes deshabilitar el inicio de sesión de la cuenta afectada por completo, lo que a su vez deshabilitará el acceso de la aplicación a los datos de esa cuenta. Esto no es ideal para la productividad del usuario final, por supuesto, pero si está trabajando para limitar el impacto rápidamente, puede ser una corrección viable a corto plazo.

- Puede desactivar las aplicaciones integradas para su arrendamiento. Este es un paso drástico que deshabilita la capacidad de los usuarios finales para conceder consentimiento en todo el espacio empresarial. Esto impide que los usuarios concedan acceso a una aplicación malintencionada de forma involuntaria. Esto no es muy recomendable, ya que afecta gravemente a la capacidad de los usuarios de ser productivos con aplicaciones de terceros. Para ello, siga los pasos descritos en Activar o desactivar aplicaciones [integradas.](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Proteger Microsoft 365 como un profesional de la ciberseguridad

Su suscripción a Microsoft 365 incluye un potente conjunto de capacidades de seguridad que puede usar para proteger sus datos y los usuarios. Use el [Plan de seguridad de Microsoft 365: principales prioridades para los primeros 30 días, 90 días y en adelante](security-roadmap.md) para implementar las prácticas recomendadas de Microsoft para proteger su espacio empresarial de Microsoft 365.

- Tareas a realizar en los primeros 30 días. Estas tienen un efecto inmediato y de bajo impacto para los usuarios.

- Tareas para llevar a cabo en 90 días. Estas tareas necesitan un poco más de tiempo para planearlas e implementarlas, pero mejoran considerablemente el nivel de seguridad.

- Más de 90 días. Estas mejoras se crean en el trabajo de los 90 primeros días.

## <a name="see-also"></a>Vea también:

- [Una aplicación inesperada en la lista de](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) mis aplicaciones guía a los administradores a través de diversas acciones que pueden desear realizar después de darse cuenta de que hay aplicaciones inesperadas con acceso a los datos.

- [La integración de aplicaciones con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) es una introducción general de alto nivel de consentimiento y permisos.

- [Los problemas de desarrollo de mi aplicación](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) proporcionan vínculos a diversos artículos relacionados con el consentimiento.

- Los objetos de entidad de seguridad de aplicación y servicio de [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) proporcionan información general sobre los objetos de entidad de seguridad de aplicación y servicio que son fundamentales para el modelo de aplicación.

- [Administrar el acceso a las](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) aplicaciones es una introducción a las funcionalidades que los administradores tienen para administrar el acceso de los usuarios a las aplicaciones.
