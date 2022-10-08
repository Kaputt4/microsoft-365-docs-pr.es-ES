---
title: Detección y corrección de concesiones de consentimiento ilícitas
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- m365-security
ms.date: 07/28/2022
ms.localizationpriority: medium
search.appverid:
- MET150
description: Obtenga información sobre cómo reconocer y corregir el ataque de concesiones de consentimiento ilícito en Microsoft 365.
ms.custom:
- seo-marvel-apr2020
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 4ddd978a4ac75680f10413a3064586ce38967f29
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68072489"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>Detección y corrección de concesiones de consentimiento ilícitas

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Resumen**  Obtenga información sobre cómo reconocer y corregir el ataque de concesiones de consentimiento ilícito en Microsoft 365.

## <a name="what-is-the-illicit-consent-grant-attack-in-microsoft-365"></a>¿Cuál es el ataque de concesión de consentimiento ilícito en Microsoft 365?

En un ataque de concesión de consentimiento ilícito, el atacante crea una aplicación registrada en Azure que solicita acceso a datos como información de contacto, correo electrónico o documentos. A continuación, el atacante engaña a un usuario final para que conceda el consentimiento de esa aplicación para acceder a sus datos a través de un ataque de suplantación de identidad (phishing) o mediante la inserción de código ilícito en un sitio web de confianza. Una vez que se ha concedido el consentimiento a la aplicación ilícita, tiene acceso a los datos a nivel de cuenta sin necesidad de una cuenta de la organización. Los pasos de corrección normales, como el restablecimiento de contraseñas para cuentas infringidas o la necesidad de Multi-Factor Authentication (MFA) en las cuentas, no son eficaces contra este tipo de ataque, ya que son aplicaciones de terceros y son externas a la organización.

Estos ataques aprovechan un modelo de interacción que presupone que la entidad que llama a la información es la automatización y no un humano.

> [!IMPORTANT]
> ¿Sospecha que está experimentando problemas con las concesiones de consentimiento ilícitas de una aplicación, en este momento? Microsoft Defender for Cloud Apps tiene herramientas para detectar, investigar y corregir las aplicaciones de OAuth. Este artículo de Defender for Cloud Apps tiene un tutorial que describe cómo investigar [aplicaciones de OAuth de riesgo](/cloud-app-security/investigate-risky-oauth). También puede establecer [directivas de aplicaciones de OAuth](/cloud-app-security/app-permission-policy) para investigar los permisos solicitados por la aplicación, qué usuarios autorizan estas aplicaciones y aprobar o prohibir ampliamente estas solicitudes de permisos.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-microsoft-365"></a>¿Cómo es un ataque de concesión de consentimiento ilícito en Microsoft 365?

Debe buscar en el **registro de auditoría** para encontrar signos, también denominados Indicadores de compromiso (IOC) de este ataque. En el caso de las organizaciones con muchas aplicaciones registradas en Azure y una base de usuarios grande, el procedimiento recomendado es revisar las concesiones de consentimiento de las organizaciones semanalmente.

### <a name="steps-for-finding-signs-of-this-attack"></a>Pasos para encontrar signos de este ataque

1. Abra el portal de Microsoft 365 Defender en y, a <https://security.microsoft.com> continuación, seleccione **Auditar**. O bien, para ir directamente a la página de **Auditoría**, use <https://security.microsoft.com/auditlogsearch>.

2. En la página **Auditoría** , compruebe que la pestaña **Buscar** está seleccionada y, a continuación, configure los siguientes valores:
   - **Intervalo de fecha y hora**
   - **Actividades**: compruebe que **la opción Mostrar resultados de todas las actividades** está seleccionada.

   Cuando haya terminado, haga clic en **Buscar**.

3. Haga clic en la columna **Actividad** para ordenar los resultados y busque **Consentimiento para la aplicación**.

4. Seleccione una entrada de la lista para ver los detalles de la actividad. Compruebe si IsAdminConsent está establecido en True.

> [!NOTE]
>
> La entrada de registro de auditoría correspondiente puede tardar entre 30 minutos y 24 horas en mostrarse en los resultados de la búsqueda después de que se produzca un evento.
>
> El período de tiempo que se conserva un registro de auditoría y se puede buscar en el registro de auditoría depende de la suscripción de Microsoft 365 y, en concreto, del tipo de licencia que se asigna a un usuario específico. Para obtener más información, consulte [Registro de auditoría](../../compliance/search-the-audit-log-in-security-and-compliance.md).
>
> Si este valor es true, indica que alguien con acceso de administrador global puede haber concedido acceso amplio a los datos. Si esto es inesperado, realice los pasos necesarios para [confirmar un ataque](#how-to-confirm-an-attack).

## <a name="how-to-confirm-an-attack"></a>Confirmación de un ataque

Si tiene una o varias instancias de las IOC enumeradas anteriormente, debe realizar una investigación adicional para confirmar positivamente que se produjo el ataque. Puede usar cualquiera de estos tres métodos para confirmar el ataque:

- Inventario de aplicaciones y sus permisos mediante el portal de Azure Active Directory. Este método es exhaustivo, pero solo puede comprobar un usuario a la vez, lo que puede llevar mucho tiempo si tiene muchos usuarios que comprobar.
- Inventario de aplicaciones y sus permisos mediante PowerShell. Este es el método más rápido y exhaustivo, con la menor cantidad de sobrecarga.
- Pida a los usuarios que comprueben individualmente sus aplicaciones y permisos e informen de los resultados a los administradores para que los corrijan.

## <a name="inventory-apps-with-access-in-your-organization"></a>Inventario de aplicaciones con acceso en su organización

Puede hacerlo para los usuarios con el Portal de Azure Active Directory o PowerShell, o bien hacer que los usuarios enumeren individualmente su acceso a la aplicación.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Pasos para usar el Portal de Azure Active Directory

Puede buscar las aplicaciones a las que cualquier usuario individual ha concedido permisos mediante el Portal de Azure Active Directory en <https://portal.azure.com>.

1. Inicie sesión en el Azure Portal con derechos administrativos.
2. Seleccione la hoja Azure Active Directory.
3. Seleccione **Usuarios**.
4. Seleccione el usuario que desea revisar.
5. Seleccione **Aplicaciones**.

Esto le mostrará las aplicaciones que se asignan al usuario y qué permisos tienen las aplicaciones.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>Pasos para hacer que los usuarios enumeren su acceso a la aplicación

Haga que los usuarios vayan a <https://myapps.microsoft.com> su propia aplicación y revisen su propio acceso a ella. Deben poder ver todas las aplicaciones con acceso, ver detalles sobre ellas (incluido el ámbito de acceso) y poder revocar privilegios a aplicaciones sospechosas o ilícitas.

### <a name="steps-for-doing-this-with-powershell"></a>Pasos para hacerlo con PowerShell

La manera más sencilla de comprobar el ataque de concesión de consentimiento ilícito es ejecutar [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), que volcará todas las concesiones de consentimiento de OAuth y las aplicaciones de OAuth para todos los usuarios del inquilino en un archivo .csv.

#### <a name="pre-requisites"></a>Requisitos previos

- La biblioteca de PowerShell de Azure AD instalada.
- Administrador global derechos en el inquilino en el que se ejecutará el script.
- Administrador local en el equipo desde el que se ejecutarán los scripts.

> [!IMPORTANT]
> Se ***recomienda encarecidamente*** requerir la autenticación multifactor en la cuenta administrativa. Este script admite la autenticación MFA.

1. Inicie sesión en el equipo desde el que ejecutará el script con derechos de administrador local.

2. Descargue o copie el script [ deGet-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) de GitHub en una carpeta desde la que ejecutará el script. Esta será la misma carpeta en la que se escribirá el archivo "permissions.csv" de salida.

3. Abra una sesión de PowerShell como administrador y abra la carpeta en la que guardó el script.

4. Conéctese al directorio mediante el cmdlet [Connect-AzureAD](/powershell/module/azuread/connect-azuread) .

5. Ejecute este comando de PowerShell:

   ```powershell
   .\Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

El script genera un archivo denominado Permissions.csv. Siga estos pasos para buscar concesiones de permisos de aplicación ilícitas:

1. En la columna ConsentType (columna G), busque el valor "AllPrinciples". El permiso AllPrincipals permite a la aplicación cliente acceder al contenido de todos los usuarios del inquilino. Las aplicaciones nativas de Microsoft 365 necesitan este permiso para funcionar correctamente. Todas las aplicaciones que no sean de Microsoft con este permiso deben revisarse cuidadosamente.

2. En la columna Permiso (columna F), revise los permisos que cada aplicación delegada tiene para el contenido. Busque los permisos "Leer" y "Escribir" o "Todos", y revíselos cuidadosamente porque es posible que no sean adecuados.

3. Revise los usuarios específicos que tienen consentimientos concedidos. Si los usuarios de alto perfil o de alto impacto tienen consentimientos inadecuados concedidos, debe investigar más.

4. En la columna ClientDisplayName (columna C), busque aplicaciones que parezcan sospechosas. Las aplicaciones con nombres mal escritos, nombres supersómbidos o nombres que suenan a piratas informáticos deben revisarse cuidadosamente.

## <a name="determine-the-scope-of-the-attack"></a>Determinación del ámbito del ataque

Una vez que haya terminado de inventariar el acceso a la aplicación, revise el **registro de auditoría** para determinar el ámbito completo de la infracción. Busque en los usuarios afectados, los períodos de tiempo a los que la aplicación ilegal tenía acceso a su organización y los permisos que tenía la aplicación. Puede buscar en el **registro de auditoría** en el [portal de Microsoft 365 Defender](../../compliance/search-the-audit-log-in-security-and-compliance.md).

> [!IMPORTANT]
> [La auditoría de buzones](../../compliance/enable-mailbox-auditing.md) y la [auditoría de actividad para administradores y usuarios](../../compliance/turn-audit-log-search-on-or-off.md) deben haberse habilitado antes del ataque para que pueda obtener esta información.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>Cómo detener y corregir un ataque de concesión de consentimiento ilícito

Una vez que haya identificado una aplicación con permisos ilícitos, tiene varias maneras de quitar ese acceso.

- Puede revocar el permiso de la aplicación en el Portal de Azure Active Directory mediante:
  1. Vaya al usuario afectado en la hoja **Usuario de Azure Active Directory** .
  2. Seleccione **Aplicaciones**.
  3. Seleccione la aplicación ilícita.
  4. Haga clic en **Quitar** en la exploración en profundidad.

- Puede revocar la concesión de consentimiento de OAuth con PowerShell siguiendo los pasos descritos en [Remove-AzureADOAuth2PermissionGrant](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).

- Puede revocar la asignación de roles de aplicación de servicio con PowerShell siguiendo los pasos descritos en [Remove-AzureADServiceAppRoleAssignment](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).

- También puede deshabilitar por completo el inicio de sesión de la cuenta afectada, lo que, a su vez, deshabilitará el acceso de la aplicación a los datos de esa cuenta. Esto no es ideal para la productividad del usuario final, por supuesto, pero si está trabajando para limitar el impacto rápidamente, puede ser una corrección viable a corto plazo.

- Puede desactivar las aplicaciones integradas para su inquilino. Se trata de un paso drástico que deshabilita la capacidad de los usuarios finales para conceder consentimiento en todo el inquilino. Esto impide que los usuarios concedan acceso involuntariamente a una aplicación malintencionada. Esto no es muy recomendable, ya que afecta gravemente a la capacidad de los usuarios para ser productivos con aplicaciones de terceros. Para ello, siga los pasos descritos en [Activar o desactivar aplicaciones integradas](../../admin/misc/user-consent.md).

## <a name="see-also"></a>Vea también

- [Una aplicación inesperada en la lista de aplicaciones](/azure/active-directory/application-access-unexpected-application) guía a los administradores a través de varias acciones que pueden querer realizar después de darse cuenta de que hay aplicaciones inesperadas con acceso a los datos.
- [La integración de aplicaciones con Azure Active Directory](/azure/active-directory/active-directory-apps-permissions-consent) es una introducción de alto nivel al consentimiento y los permisos.
- [Problemas al desarrollar mi aplicación](/azure/active-directory/active-directory-application-dev-development-content-map) proporciona vínculos a varios artículos relacionados con el consentimiento.
- [Los objetos de aplicación y entidad de servicio de Azure Active Directory (Azure AD)](/azure/active-directory/develop/active-directory-application-objects) proporcionan información general sobre los objetos de entidad de servicio y aplicación que son fundamentales para el modelo de aplicación.
- [Administrar el acceso a las aplicaciones](/azure/active-directory/active-directory-managing-access-to-apps) es una introducción a las funcionalidades que los administradores tienen para administrar el acceso de los usuarios a las aplicaciones.
