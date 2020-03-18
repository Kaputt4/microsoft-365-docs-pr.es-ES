---
title: Detectar y solucionar la concesión de consentimiento ilegal en Office 365
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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Aprenda a reconocer y corregir el consentimiento ilícito concede un ataque en Office 365.
ms.openlocfilehash: 171dbf586a869e9c85bb1e10b6beb7a2f4e5f425
ms.sourcegitcommit: 01ead889086ecc7dcf5d10244bcf67c5a33c8114
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2020
ms.locfileid: "42710529"
---
# <a name="detect-and-remediate-illicit-consent-grants-in-office-365"></a>Detectar y solucionar la concesión de consentimiento ilegal en Office 365

**Resumen**  Aprenda a reconocer y corregir el consentimiento ilícito concede un ataque en Office 365.

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>¿Cuál es el ataque de concesión de consentimiento ilícito en Office 365?

En un ataque de consentimiento ilícito, el atacante crea una aplicación registrada de Azure que solicita acceso a datos como la información de contacto, el correo electrónico o los documentos. A continuación, el atacante engaña a un usuario final para que conceda a esa aplicación el consentimiento para obtener acceso a sus datos mediante un ataque de suplantación de identidad o insertando código ilícito en un sitio web de confianza. Una vez que se ha concedido el consentimiento de la aplicación ilícita, tiene acceso de nivel de cuenta a los datos sin necesidad de una cuenta de la organización. Los pasos de corrección normales, como restablecer las contraseñas de las cuentas infringidas o requerir la autenticación multifactor (MFA) en las cuentas, no son eficaces contra este tipo de ataque, ya que son aplicaciones de terceros y son externas a la organización. 

Estos ataques aprovechan un modelo de interacción que presupone que la entidad que llama a la información es la automatización y no es una persona.

> [!IMPORTANT]
> ¿Sospecha que tiene problemas con el consentimiento ilícito: concesiones de una aplicación ahora? Microsoft Cloud App Security (MCAS) tiene herramientas para detectar, investigar y corregir las aplicaciones de OAuth. Este artículo de MCAS tiene un tutorial que describe cómo [investigar aplicaciones de OAuth de riesgo](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth). También puede establecer [directivas de aplicación de OAuth](https://docs.microsoft.com/cloud-app-security/app-permission-policy) para investigar los permisos solicitados por la aplicación, qué usuarios autorizan estas aplicaciones y aprobar o prohibir ampliamente estas solicitudes de permisos.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>¿Qué aspecto tiene un ataque ilegal de concesión de consentimiento en Office 365?

Debe buscar en el **registro de auditoría** de Office 365 para encontrar signos, también denominados "indicadores de peligro" (IOC) de este ataque. Para las organizaciones con muchas aplicaciones registradas en Azure y una base de usuarios grande, el procedimiento recomendado es revisar las concesiones de consentimiento de las organizaciones cada semana.

### <a name="steps-for-finding-signs-of-this-attack"></a>Pasos para buscar signos de este ataque

1. Abra el **centro de seguridad y cumplimiento** en el inquilino de Office 365.

2. Desplácese hasta **Buscar** y seleccione **búsqueda de registros de auditoría**.

3. Búsqueda (todas las actividades y todos los usuarios), especifique la fecha de inicio y la fecha de finalización si es necesario y, a continuación, haga clic en **Buscar**. 

4. Filtre los resultados por consentimiento a Application y agregue OAuth2PermissionGrant.

5. Haga clic en el resultado para ver los detalles de la actividad. Haga clic en **más información** para obtener detalles de la actividad. Compruebe si IsAdminContent está establecido en true.

> [!NOTE]
> * La entrada de registro de auditoría correspondiente puede tardar de 30 minutos de hasta 24 horas en aparecer en los resultados de la búsqueda después de que se produzca un evento. <br/><br/> La cantidad de tiempo que se retiene un registro de auditoría y se pueden buscar en el registro de auditoría depende de la suscripción de Office 365 y, específicamente, del tipo de licencia asignado a un usuario específico. Para obtener más información, vea [registro de auditoría](../../compliance/search-the-audit-log-in-security-and-compliance.md).
Si este valor es true, indica que un usuario con acceso de administrador global puede haber concedido acceso general a los datos. Si esto es inesperado, siga los pasos para [confirmar un ataque](#how-to-confirm-an-attack).

## <a name="how-to-confirm-an-attack"></a>Cómo confirmar un ataque

Si tiene una o más instancias de la IOCs enumeradas anteriormente, debe seguir investigando para confirmar que se ha producido el ataque. Puede usar cualquiera de estos tres métodos para confirmar el ataque.

- Las aplicaciones de inventario y sus permisos mediante el portal de Azure Active Directory. Este método es exhaustivo, pero solo puede realizar comprobaciones en un usuario cada vez que puede llevar mucho tiempo si tiene que comprobar muchos usuarios.

- Aplicaciones de inventario y sus permisos mediante PowerShell. Este es el método más rápido y completo, con la menor cantidad de sobrecarga.

- Pida a los usuarios que comprueben individualmente sus aplicaciones y permisos, y devuelvan los resultados a los administradores para corregirlos.

## <a name="inventory-apps-with-access-in-your-organization"></a>Aplicaciones de inventario con acceso en la organización

Puede hacerlo para los usuarios con el portal de Azure Active Directory o con PowerShell, o bien hacer que los usuarios enumeren individualmente el acceso a la aplicación.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Pasos para usar el portal de Azure Active Directory

Puede buscar las aplicaciones a las que cualquier usuario individual ha concedido permisos mediante el uso del [portal de Azure Active Directory](https://portal.azure.com/).

1. Inicie sesión en Azure portal con derechos administrativos.

2. Seleccione la hoja Azure Active Directory.

3. Seleccione **Usuarios**.

4. Seleccione el usuario que desea revisar.

5. Seleccione **aplicaciones**.

Esto le mostrará las aplicaciones que se asignan al usuario y qué permisos tienen las aplicaciones.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>Pasos para hacer que los usuarios enumeren el acceso a la aplicación

Pida a los usuarios que https://myapps.microsoft.com vayan a y revisen su propio acceso a la aplicación. Deben poder ver todas las aplicaciones con acceso, ver detalles sobre ellas (incluido el ámbito de acceso) y poder revocar los privilegios de aplicaciones sospechosas o ilícitas.

### <a name="steps-for-doing-this-with-powershell"></a>Pasos para hacerlo con PowerShell

La forma más sencilla de comprobar el ataque de consentimiento ilícito es ejecutar [Get-AzureADPSPermissions. PS1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), que volcarán todas las concesiones de consentimiento de OAuth y las aplicaciones de OAuth para todos los usuarios de su arrendamiento en un archivo. csv.

#### <a name="pre-requisites"></a>Requisitos previos

- La biblioteca de Azure AD PowerShell instalada.

- Derechos de administrador global en el espacio empresarial en el que se ejecutará el script.

- Administrador local en el equipo desde el que se ejecutarán los scripts.

> [!IMPORTANT]
> Se ***recomienda encarecidamente*** que requiera la autenticación multifactor en su cuenta administrativa. Este script admite la autenticación MFA.

1. Inicie sesión en el equipo en el que va a ejecutar el script con derechos de administrador local.

2. Descargue o copie el script [Get-AzureADPSPermissions. PS1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) de github a una carpeta desde la que se ejecutará el script. Se trata de la misma carpeta en la que se escribirá el archivo "Permissions. csv" de salida.

3. Abra una instancia de PowerShell como administrador y abra la carpeta en la que guardó el script.

4. Conéctese a su directorio mediante el cmdlet [Connect-AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread) .

5. Ejecute este comando de PowerShell:

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

La secuencia de comandos genera un archivo denominado Permissions. csv. Siga estos pasos para buscar concesiones de permisos de aplicaciones ilícitas:

1. En la columna ConsentType (Column G), busque el valor "AllPrinciples". El permiso AllPrincipals permite a la aplicación cliente obtener acceso al contenido de todo el inquilino. Las aplicaciones nativas de Office 365 necesitan este permiso para funcionar correctamente. Todas las aplicaciones que no sean de Microsoft con este permiso deben revisarse con cuidado.

2. En la columna permiso (columna F), revise los permisos que tiene cada aplicación delegada en el contenido. Busque el permiso "leer" y "escribir" o "*. All "permiso y revise estos detenidamente porque es posible que no sean apropiados.

3. Revise los usuarios específicos que tienen permisos concedidos. Si los usuarios de alto impacto o alto impacto tienen concedidos inadecuados, debe investigar más.

4. En la columna ClientDisplayName (columna C), busque las aplicaciones que parecen sospechosas. Las aplicaciones con nombres mal escritos, nombres de súper Bland o nombres de sonido de hacker deben revisarse detenidamente.

## <a name="determine-the-scope-of-the-attack"></a>Determinar el ámbito del ataque

Una vez que haya terminado de inventariar el acceso a la aplicación, revise el **registro de auditoría** de Office 365 para determinar el ámbito completo de la infracción. Busque los usuarios afectados, los intervalos de tiempo en los que la aplicación ilícita tuvo acceso a su organización y los permisos que tenía la aplicación. Puede buscar en el **registro de auditoría** del [centro de seguridad y cumplimiento de Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

> [!IMPORTANT]
> La auditoría de [buzones](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) y la [Auditoría de actividades para administradores y usuarios](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) deben estar habilitados antes del ataque para que pueda obtener esta información.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>Cómo detener y corregir un ataque de concesión de consentimiento ilícito

Una vez que haya identificado una aplicación con permisos de ilícitas, tiene varias formas de quitar ese acceso.

- Puede revocar el permiso de la aplicación en el portal de Azure Active Directory de la siguiente manera:

  - Navegue al usuario afectado en la hoja de **usuario de Azure Active** Directory.

  - Seleccione **aplicaciones**.

  - Seleccione la aplicación ilícita.

  - Haga clic en **quitar** en el detalle.

- Puede revocar la concesión de consentimiento de OAuth con PowerShell siguiendo los pasos descritos en [Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).

- Puede revocar la asignación de roles de aplicación de servicio con PowerShell siguiendo los pasos descritos en [Remove-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).

- También puede deshabilitar el inicio de sesión para la cuenta afectada por completo, que a su vez deshabilitará el acceso a la aplicación a los datos de esa cuenta. Esto no es ideal para la productividad del usuario final, por supuesto, pero si está trabajando para limitar rápidamente el impacto, puede ser una corrección viable a corto plazo.

- Puede desactivar las aplicaciones integradas para su arrendamiento. Se trata de un paso drástico que deshabilita la capacidad de los usuarios finales para conceder consentimiento en un espacio empresarial. Esto evita que los usuarios concedan de forma inadvertida acceso a una aplicación malintencionada. Esto no es muy recomendable ya que perjudica seriamente la capacidad de los usuarios de ser productivo con aplicaciones de terceros. Para ello, siga los pasos que se indican en [activar o desactivar las aplicaciones integradas](https://docs.microsoft.com/office365/admin/misc/integrated-apps).

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>Proteger Office 365 como un profesional de ciberseguridad

Su suscripción a Office 365 incluye un potente conjunto de capacidades de seguridad que puede usar para proteger sus datos y los usuarios. Use el [Plan de seguridad de Office 365: principales prioridades para los primeros 30 días, 90 días y en adelante](security-roadmap.md) para implementar las prácticas recomendadas de Microsoft para proteger su espacio empresarial de Office 365.

- Tareas a realizar en los primeros 30 días. Estas tienen un efecto inmediato y de bajo impacto para los usuarios.

- Tareas para llevar a cabo en 90 días. Estas tareas necesitan un poco más de tiempo para planearlas e implementarlas, pero mejoran considerablemente el nivel de seguridad.

- Más de 90 días. Estas mejoras se crean en el trabajo de los 90 primeros días.

## <a name="see-also"></a>Vea también:

- Una [aplicación inesperada en la lista de mis aplicaciones](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) dirige a los administradores a través de diversas acciones que quizás deseen realizar después de la realización de que hay aplicaciones inesperadas con acceso a los datos.

- La [integración de aplicaciones con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) es una introducción de alto nivel de consentimiento y permisos.

- [Problemas en el desarrollo de la aplicación](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) proporciona vínculos a varios artículos relacionados con el consentimiento.

- La [aplicación y los objetos de entidad de servicio de Azure Active Directory (Azure ad)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) proporcionan una introducción a los objetos de la entidad de servicio y la aplicación que son fundamentales para el modelo de la aplicación.

- [Manage Access to apps](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) es una introducción a las funcionalidades que los administradores tienen para administrar el acceso de los usuarios a las aplicaciones.
