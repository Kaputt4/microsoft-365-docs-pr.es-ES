---
title: Power BI en su organización
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- PWB150
ms.assetid: d7941332-8aec-4e5e-87e8-92073ce73dc5
ROBOTS: NOINDEX
description: Obtenga información sobre Power BI y cómo los usuarios de su organización pueden usar este servicio de análisis empresarial.
ms.openlocfilehash: b4e1fd299caa4045a68770adc3a2d53dd4b11ec0
ms.sourcegitcommit: da6b3cb3b2ccfcdcd5091efce8290b6c486547db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2022
ms.locfileid: "65469544"
---
# <a name="using-power-bi-data-in-your-organization"></a>Uso de datos de Power BI en la organización

Esta página describe cómo los usuarios de su organización pueden usar Power BI y cómo puede controlar el modo en que la organización adquiere este servicio.

## <a name="what-is-power-bi"></a>¿Qué es Power BI?

Microsoft Power BI permite a los usuarios visualizar datos, compartir descubrimientos y colaborar de maneras nuevas e intuitivas. Para obtener más información, consulte el [sitio Web de Power BI](https://powerbi.microsoft.com/en-us/).
  
## <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>¿cumple Power BI requisitos de cumplimiento nacionales, regionales y específicos del sector?

Para obtener más información sobre el cumplimiento de Power BI, consulte el [Centro de confianza de Microsoft](https://go.microsoft.com/fwlink/?LinkId=785324).
  
## <a name="how-do-users-sign-up-for-power-bi"></a>¿Cómo se registran los usuarios en Power BI?

Como administrador, puede registrarse en Power BI a través del [sitio web de Power BI](https://powerbi.microsoft.com/en-us/). También puede registrarse a través de la página de servicios de compra en el Centro de administración de Microsoft 365. Cuando un administrador se registra en Power BI, puede asignar licencias de suscripción a usuarios que deberían tener acceso.
  
Además, los usuarios individuales en su organización pueden registrarse en Power BI a través del [sitio web de Power BI](https://powerbi.microsoft.com/en-us/). Cuando un usuario de su organización se registra en Power BI, se le asigna automáticamente una licencia de Power BI.
  
## <a name="how-do-individual-users-in-my-organization-sign-up"></a>¿Cómo se registran los usuarios individuales de mi organización?

Hay tres posibles situaciones para los usuarios de su organización:
  
### <a name="scenario-1-your-organization-already-has-an-existing-microsoft-365-environment-and-the-user-signing-up-for-power-bi-already-has-a-microsoft-365-account"></a>Escenario 1: su organización ya tiene un entorno de Microsoft 365 existente y el usuario que se registra para Power BI ya tiene una cuenta de Microsoft 365.

En este caso, si un usuario ya tiene una cuenta profesional o educativa en el inquilino (por ejemplo, contoso.com) pero aún no tiene Power BI, Microsoft simplemente activa el plan para dicha cuenta y se notificará automáticamente al usuario cómo usar el servicio Power BI.
  
### <a name="scenario-2-your-organization-has-an-existing-microsoft-365-environment-and-the-user-signing-up-for-power-bi-doesnt-have-a-microsoft-365-account"></a>Escenario 2: La organización tiene un entorno de Microsoft 365 existente y el usuario que se registra para Power BI no tiene una cuenta de Microsoft 365.

En este escenario, el usuario tiene una dirección de correo electrónico en el dominio de su organización (por ejemplo, contoso.com), pero aún no tiene una cuenta de Microsoft 365. En este caso, el usuario puede registrarse en Power BI y se le asignará automáticamente una cuenta. Esto permite al usuario acceder al servicio de Power BI. Por ejemplo, si un empleado llamado Nancy usa su dirección de correo electrónico de trabajo (por ejemplo, Nancy@contoso.com) para registrarse, Microsoft agregará automáticamente Nancy como usuario en el entorno de Contoso Microsoft 365 y activará Power BI para esa cuenta.
  
### <a name="scenario-3-your-organization-does-not-have-a-microsoft-365-environment-connected-to-your-email-domain"></a>Escenario 3: Su organización no tiene un entorno de Microsoft 365 conectado al dominio de correo electrónico.

No hay ninguna acción administrativa que su organización necesite para aprovechar Power BI.
  
> [!IMPORTANT]
> Si su organización tiene varios dominios de correo electrónico y prefiere que todas las extensiones de dirección de correo electrónico estén en el mismo inquilino, antes de que los usuarios creen el inquilino principal, agregue todos los dominios de dirección de correo electrónico a ese inquilino antes de que los usuarios creen el inquilino principal. No hay ningún mecanismo automatizado para mover usuarios entre inquilinos después de que se hayan creado. Para obtener más información sobre este proceso, consulte [Si tengo varios dominios, ¿puedo controlar el inquilino al que se agregan los usuarios más](#if-i-have-multiple-domains-can-i-control-the-tenant-that-users-are-added-to) adelante en este artículo y [Agregar un dominio a Office 365](../setup/add-domain.md) en línea.
  
## <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>¿Cómo cambio la forma en la que administro las identidades de los usuarios en mi organización?

Si su organización ya tiene un entorno de Microsoft 365 existente y todos los usuarios de la organización tienen cuentas de Microsoft 365, la administración de identidades no cambiará.
  
Si su organización ya tiene un entorno de Microsoft 365 existente, pero no todos los usuarios de su organización tienen cuentas de Microsoft 365, crearemos un usuario en el inquilino y asignaremos licencias basadas en la dirección de correo electrónico profesional o educativa del usuario. Esto significa que el número de usuarios que administra en un tiempo en particular crecerá a medida que los usuarios de su organización se registren en el servicio.
  
Si administra su directorio de forma local y usa Active_Directory_Federation_Services_(AD_FS), Microsoft no agregará usuarios a su inquilino y los usuarios que intenten unirse a su inquilino recibirán un mensaje indicándoles que se pongan en contacto con el administrador de su organización.
  
Si su organización no tiene un entorno de Microsoft 365 conectado al dominio de correo electrónico, no habrá ningún cambio en la forma de administrar la identidad. Los usuarios se agregarán a un nuevo directorio de usuario exclusivamente en la nube y tendrá la opción de tener el puesto de administrador de inquilino para administrarlos.
  
## <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>¿Cuál es el proceso para administrar un inquilino creado por Microsoft para mis usuarios?

Si un inquilino ha sido creado por Microsoft, puede reclamar y administrar dicho inquilino siguiendo estos pasos:
  
1. Únase al inquilino [registrándose en Power BI](https://go.microsoft.com/fwlink/?LinkId=522448) con un correo electrónico que coincida con el dominio del inquilino que desea administrar. Por ejemplo, si Microsoft ha creado el inquilino contoso.com, deberá unirse al inquilino con una dirección de correo electrónico que termine en @contoso.com.

1. Solicite el control de administración verificando la propiedad del dominio: una vez que esté en el inquilino, puede ascender al puesto de administrador verificando la propiedad del dominio. Para hacerlo, siga estos pasos:

::: moniker range="o365-worldwide"

3. Vaya a <a href="https://admin.microsoft.com" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-21vianet"

3. Vaya a <a href="https://portal.partner.microsoftonline.cn" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end

4. Seleccione el icono del iniciador de aplicaciones en la esquina superior izquierda y elija **Administrador**.

    ![Iniciador de aplicaciones con la aplicación admin resaltada.](../../media/4eea9dbc-591b-48be-9916-322d41c6525b.png)
  
5. Lea las instrucciones de la página **Convertirse en administrador** y, **a continuación, seleccione Sí, quiero ser el administrador**.

    > [!NOTE]
    >  Si esta opción no aparece, ya hay un administrador en su lugar.
  
## <a name="if-i-have-multiple-domains-can-i-control-the-tenant-that-users-are-added-to"></a>Si tengo varios dominios, ¿puedo controlar el inquilino al que se agregan los usuarios?

Si no hace nada, se creará un inquilino para cada dominio y subdominio de correo electrónico de usuario.
  
Si desea que todos los usuarios estén en el mismo inquilino independientemente de sus extensiones de dirección de correo electrónico:
  
- Cree un inquilino de destino con antelación o utilice un inquilino existente y agregue todos los dominios y subdominios existentes que quiera que se consoliden en ese inquilino. A continuación, todos los usuarios con direcciones de correo electrónico que terminen en estos dominios y subdominios se unirán de forma automática al inquilino de destino al registrarse.

> [!IMPORTANT]
> No hay ningún mecanismo automatizado compatible para mover usuarios de un inquilino a otro una vez que se han creado. Para obtener información sobre cómo agregar dominios a un único inquilino Microsoft 365, consulte [Adición de un dominio a Office 365](../setup/add-domain.md).

> [!IMPORTANT]
> Para obtener más información e instrucciones sobre cómo administrar inquilinos, consulte [¿Qué es Power BI administración?](/power-bi/service-admin-administering-power-bi-in-your-organization).
  
## <a name="how-can-i-prevent-users-from-joining-my-existing-tenant"></a>¿Cómo puedo impedir que los usuarios se unan a mi inquilino existente?

Hay pasos que puede seguir como administrador para evitar que los usuarios se unan a su inquilino existente. Si impide que los usuarios se unan al inquilino, se producirá un error en los intentos de inicio de sesión de los usuarios y se les dirigirá para que se pongan en contacto con el administrador de su organización. No es necesario repetir este proceso si ya ha deshabilitado la distribución automática de licencias antes (por ejemplo, Office 365 Educación para estudiantes, profesores y personal).
  
Estos pasos requieren el uso de Windows PowerShell. Para empezar a trabajar con Windows PowerShell, consulte la [Guía de introducción de PowerShell](/powershell/scripting/overview).
  
Para realizar los pasos siguientes, debe instalar la versión más reciente de 64 bits del [módulo de PowerShell Azure Active Directory V2](https://www.powershellgallery.com/packages/AzureADPreview/2.0.2.5).
  
Después de seleccionar el vínculo, seleccione **Ejecutar** para ejecutar el paquete de instalación.
  
**Deshabilitar la opción de unión automática al inquilino**: utilice este comando de Windows PowerShell para evitar que los nuevos usuarios se unan a un inquilino administrado:
  
Para deshabilitar la unión automática al inquilino para nuevos usuarios:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $false`
  
Para habilitar la unión automática al inquilino para nuevos usuarios:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`
  
> [!NOTE]
> Este bloqueo impide que los nuevos usuarios de la organización se registren para Power BI. Los usuarios que se registren para Power BI antes de deshabilitar los nuevos registros de su organización seguirán conservando sus licencias. Consulte el [Cómo quitar Power BI para los usuarios que ya se han registrado?](#how-do-i-remove-power-bi-for-users-that-already-signed-up) para obtener instrucciones sobre cómo puede quitar el acceso a Power BI para los usuarios que se habían registrado anteriormente para el servicio.
  
## <a name="how-can-i-allow-users-to-join-my-existing-tenant"></a>¿Cómo puedo permitir que los usuarios se unan a mi inquilino existente?

Para permitir que los usuarios se unan a su inquilino, ejecute el comando contrario como se describe en la pregunta anterior:  `Set-MsolCompanySettings -AllowEmailVerifiedUsers $true`
  
## <a name="how-do-i-verify-if-i-have-the-block-on-in-the-tenant"></a>¿Cómo puedo comprobar si el bloqueo del inquilino está activado?

Utilice la siguiente secuencia de comandos de PowerShell:  `Get-MsolCompanyInformation | fl allow*`
  
## <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>¿Cómo puedo evitar que mis usuarios existentes comiencen a usar Power BI?

**Deshabilitar la distribución automática de licencias:** Use este script de Windows PowerShell para deshabilitar las distribuciones automáticas de licencias para los usuarios existentes. No es necesario repetir este proceso si ya ha deshabilitado la distribución automática de licencias antes (por ejemplo, Office 365 Educación para estudiantes, profesores y personal).
  
Para deshabilitar la distribución automática de licencias para los usuarios existentes:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $false`
  
Para habilitar la distribución automática de licencias para los usuarios existentes:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`
  
> [!NOTE]
> La marca *AllowAdHocSubscriptions* se usa para controlar varias funcionalidades de usuario de la organización, incluida la posibilidad de que los usuarios se registren en el servicio Azure Rights Management. El cambio de este indicador afectará a todas estas capacidades.
  
## <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>¿Cómo puedo permitir que mis usuarios actuales se registren para usar Power BI?

Para permitir que los usuarios existentes se registren para usar Power BI, ejecute el comando contrario como se describe en la pregunta anterior:  `Set-MsolCompanySettings -AllowAdHocSubscriptions $true`
  
## <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>¿Cómo puedo quitar Power BI para los usuarios que ya se han registrado?

Si un usuario se ha registrado para Power BI, pero ya no quiere que tenga acceso a Power BI, puede quitar la licencia de Power BI para ese usuario.
  
::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

::: moniker-end

2. Busque el usuario para el que desea quitar la licencia y, a continuación, seleccione su nombre.

3. En la pestaña **Licencias y aplicaciones**, desactive la casilla **Microsoft Power BI**.

4. Seleccione **Guardar cambios**.

## <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>¿Cómo puedo saber cuándo se han unido nuevos usuarios al espacio empresarial?

Los usuarios que ya se unieron al inquilino como parte del programa tienen asignada una única licencia por que puede filtrar en su panel de usuarios activos en el panel de administrador.
  
Para crear esta nueva vista, en el Centro de administración, siga los pasos descritos en [Crear una vista de usuario personalizada](../add-users/create-edit-or-delete-a-custom-user-view.md#create-a-custom-user-view). En **Licencia de producto asignada**, seleccione **Microsoft Power BI**. Una vez creada la nueva vista, podrá ver todos los usuarios del inquilino que se han inscrito en este programa.
  
## <a name="are-there-any-additional-things-i-should-be-prepared-for"></a>¿Debería estar preparado para alguna otra cuestión?

Puede experimentar un aumento de solicitudes de recuperación de contraseñas. Para más información sobre este proceso, vea [Restablecer la contraseña de un usuario](../add-users/reset-passwords.md).
  
Puede quitar un usuario del inquilino a través del proceso estándar en el centro de administración. Sin embargo, si el usuario aún tiene una dirección de correo electrónico activa de su organización, podrá unirse de nuevo a menos que lo bloquee.
  
## <a name="why-did-1-million-licenses-for-microsoft-power-bi-show-up-in-my-tenant"></a>¿Por qué se mostraron 1 millón de licencias para Microsoft Power BI en mi inquilino?

Como organización apta, los usuarios de su organización son aptos para usar microsoft servicio Power BI y estas licencias representan la capacidad disponible para los nuevos usuarios de Power BI en el inquilino. No hay ningún cargo por estas licencias. Si ha elegido permitir que los usuarios se registren para Power BI ellos mismos, se les asignará una de estas licencias gratuitas disponibles cuando completen el proceso de registro. También puede optar por asignar estas licencias a los usuarios usted mismo a través del centro de administración.
  
## <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>¿Es este gratuito? ¿Se me cobrará por estas licencias?

Estas licencias son para la versión gratuita de Power BI. Si está interesado en otras capacidades, eche un vistazo a la versión Power BI Pro.
  
## <a name="why-1-million-licenses"></a>¿Por qué un millón de licencias?

Elegimos un número lo suficientemente grande como para que la mayoría de las organizaciones tuvieran licencias suficientes para proporcionar esta ventaja sin demora a sus usuarios.
  
## <a name="what-if-i-need-more-than-1-million-licenses"></a>¿Qué debo hacer si necesito más de un millón de licencias?

Póngase en contacto con el representante de su cuenta de Microsoft para obtener más información si necesita adquirir licencias adicionales.