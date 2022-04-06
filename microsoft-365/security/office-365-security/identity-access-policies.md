---
title: 'Directivas comunes de identidad de confianza cero y acceso a dispositivos: Microsoft 365 para empresas | Microsoft Docs'
description: Describe las configuraciones y directivas comunes de acceso a dispositivos y identidades de confianza cero recomendadas.
ms.author: dansimp
author: dansimp
manager: dansimp
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 36df54090e80de180ffa16f41641daa6b6966eb9
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2022
ms.locfileid: "63681334"
---
# <a name="common-zero-trust-identity-and-device-access-policies"></a>Directivas comunes de acceso a dispositivos y identidad de confianza cero

En este artículo se describen las directivas comunes de acceso a dispositivos y identidades de confianza cero recomendadas para proteger el acceso a los servicios en la nube de Microsoft 365, incluidas las aplicaciones locales publicadas con proxy de aplicación Azure Active Directory (Azure AD).

En esta guía se describe cómo implementar las directivas recomendadas en un entorno recién aprovisionado. La configuración de estas directivas en un entorno de laboratorio independiente permite comprender y evaluar las directivas recomendadas antes de realizar el lanzamiento en los entornos de preproducción y producción. El entorno recién aprovisionado puede ser híbrido o solo en la nube para reflejar sus necesidades de evaluación.

## <a name="policy-set"></a>Conjunto de directivas

En el siguiente diagrama se muestra el conjunto de directivas recomendado. Muestra a qué nivel de protección se aplica cada directiva y si las directivas se aplican a equipos, teléfonos y tabletas, o ambas categorías de dispositivos. También indica dónde se configuran estas directivas.

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png" alt-text="Directivas comunes para configurar la identidad de confianza cero y el acceso a dispositivos." lightbox="../../media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png":::


<!--

Here's a one-page PDF summary:

[![Thumb image for the Zero Trust identity and device protection for Microsoft 365 handout.](../../media/microsoft-365-policies-configurations/zero-trust-id-device-protection-model-handout-thumbnail.png)](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) <br> [View as a PDF](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) \| [Download as a PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf)


--> 

El resto de este artículo describe cómo configurar estas directivas.

> [!NOTE]
> Se recomienda usar la autenticación multifactor (MFA) antes de inscribir dispositivos en Intune para asegurarse de que el dispositivo está en posesión del usuario previsto. Debes inscribir dispositivos en Intune para poder aplicar directivas de cumplimiento de dispositivos.

Para darle tiempo para llevar a cabo estas tareas, se recomienda implementar las directivas de punto de inicio en el orden enumerado en esta tabla. Sin embargo, las directivas de MFA para los niveles de seguridad especializados y empresariales de protección se pueden implementar en cualquier momento.

|Nivel de protección|Directivas|Más información|Licencias|
|---|---|---|---|
|**Punto de inicio**|[Requerir MFA cuando el riesgo de inicio de sesión *es medio* o *alto*](#require-mfa-based-on-sign-in-risk)||Microsoft 365 E5 o Microsoft 365 E3 con el complemento seguridad E5|
||[Bloquear a los clientes que no sean compatibles con la autenticación moderna](#block-clients-that-dont-support-multi-factor)|Los clientes que no usan la autenticación moderna pueden omitir las directivas de acceso condicional, por lo que es importante bloquear estas directivas.|Microsoft 365 E3 o E5|
||[Los usuarios de riesgo alto tienen que cambiar la contraseña](#high-risk-users-must-change-password)|Fuerza a los usuarios a cambiar su contraseña al iniciar sesión si se detecta actividad de alto riesgo para su cuenta.|Microsoft 365 E5 o Microsoft 365 E3 con el complemento seguridad E5|
||[Aplicar protección de datos de directivas de protección de aplicaciones (APP)](#apply-app-data-protection-policies)|Una directiva de Protección de aplicaciones de Intune por plataforma (Windows, iOS/iPadOS, Android).|Microsoft 365 E3 o E5|
||[Requerir aplicaciones aprobadas y protección de aplicaciones](#require-approved-apps-and-app-protection)|Aplica la protección de aplicaciones móviles para teléfonos y tabletas con iOS, iPadOS o Android.|Microsoft 365 E3 o E5|
|**Empresarial**|[Requerir MFA cuando el riesgo de inicio de sesión *es bajo*, *medio* o *alto*](#require-mfa-based-on-sign-in-risk)||Microsoft 365 E5 o Microsoft 365 E3 con el complemento seguridad E5|
||[Definir directivas de cumplimiento de dispositivos](#define-device-compliance-policies)|Una directiva para cada plataforma.|Microsoft 365 E3 o E5|
||[Requerir equipos y dispositivos móviles compatibles](#require-compliant-pcs-and-mobile-devices)|Aplica la administración de Intune para equipos (Windows o macOS) y teléfonos o tabletas (iOS, iPadOS o Android).|Microsoft 365 E3 o E5|
|**Seguridad especializada**|[*Requerir* siempre MFA](#assigning-policies-to-groups-and-users)||Microsoft 365 E3 o E5|

## <a name="assigning-policies-to-groups-and-users"></a>Asignar directivas a grupos y usuarios

Antes de configurar directivas, identifique los Azure AD que está usando para cada nivel de protección. Normalmente, la protección de punto de inicio se aplica a todos los usuarios de la organización. Un usuario que se incluye para el punto de inicio y la protección de la empresa tendrá todas las directivas de punto de partida aplicadas más las directivas de empresa. La protección es acumulativa y se aplica la directiva más restrictiva.

Una práctica recomendada es crear un grupo Azure AD de exclusión de acceso condicional. Agregue este grupo a todas las directivas de acceso condicional en el  valor Excluir de la configuración **Usuarios y** grupos de la **sección Asignaciones**. Esto le proporciona un método para proporcionar acceso a un usuario mientras soluciona problemas de acceso. Esto se recomienda como una solución temporal solamente. Supervise este grupo en busca de cambios y asegúrese de que el grupo de exclusión se esté utilizando solo como se pretende.

Este es un ejemplo de asignación de grupo y exclusiones para requerir MFA.

![Ejemplo de asignación de grupos y exclusiones para directivas de MFA.](../../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

Estos son los resultados:

- Todos los usuarios deben usar MFA cuando el riesgo de inicio de sesión es medio o alto.

- Los miembros del grupo De personal ejecutivo deben usar MFA cuando el riesgo de inicio de sesión es bajo, medio o alto.

  En este caso, los miembros del grupo Personal ejecutivo coinciden tanto con el punto de inicio como con las directivas de acceso condicional de la empresa. Se combinan los controles de acceso para ambas directivas, que en este caso es equivalente a la directiva de acceso condicional de empresa.

- Los miembros del grupo secreto Project X siempre son necesarios para usar MFA

  En este caso, los miembros del grupo Top Secret Project X coinciden tanto con el punto inicial como con las directivas de acceso condicional de seguridad especializadas. Los controles de acceso para ambas directivas se combinan. Dado que el control de acceso de la directiva de acceso condicional de seguridad especializada es más restrictivo, se usa.

Tenga cuidado al aplicar niveles más altos de protección a grupos y usuarios. Por ejemplo, los miembros del grupo top secret Project X tendrán que usar MFA cada vez que inicien sesión, incluso si no están trabajando en el contenido de seguridad especializado para Project X.

Todos Azure AD creados como parte de estas recomendaciones deben crearse como Microsoft 365 grupos. Esto es importante para la implementación de etiquetas de confidencialidad al proteger documentos en Microsoft Teams y SharePoint.

![Ejemplo de creación de un Microsoft 365 grupo.](../../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)

## <a name="require-mfa-based-on-sign-in-risk"></a>Requerir MFA en función del riesgo de inicio de sesión

Debe hacer que los usuarios se registren en MFA antes de requerir su uso. Si tiene Microsoft 365 E5, Microsoft 365 E3 con el complemento seguridad E5, Office 365 con EMS E5 o licencias de Azure AD Premium P2 individuales, puede usar la directiva de registro de MFA con la protección de identidades de Azure AD para requerir que los usuarios se registren en MFA. El [trabajo previo incluye](identity-access-prerequisites.md) registrar todos los usuarios con MFA.

Una vez registrados los usuarios, puede requerir MFA para iniciar sesión con una nueva directiva de acceso condicional.

1. Vaya al [Azure Portal](https://portal.azure.com) e inicie sesión con sus credenciales.
2. En la lista de servicios de Azure, elija **Azure Active Directory**.
3. En la **lista Administrar** , elija **Seguridad** y, a continuación, **elija Acceso condicional**.
4. Elija **Nueva directiva** y escriba el nombre de la nueva directiva.

En las tablas siguientes se describe la configuración de la directiva de acceso condicional para requerir MFA en función del riesgo de inicio de sesión.

En la **sección Asignaciones** :

|Configuración|Propiedades|Valores|Notas|
|---|---|---|---|
|Usuarios y grupos|Incluir|**Seleccione usuarios y grupos > usuarios y grupos**: seleccione grupos específicos que contengan cuentas de usuario dirigidas.|Comience con el grupo que incluye cuentas de usuario piloto.|
||Excluir|**Usuarios y grupos**: seleccione el grupo de excepciones acceso condicional; cuentas de servicio (identidades de aplicación).|La pertenencia debe modificarse según sea necesario y temporalmente.|
|Acciones o aplicaciones en la nube|**Aplicaciones en la nube > incluir**|**Seleccionar aplicaciones**: selecciona las aplicaciones a las que quieres que se aplique esta directiva. Por ejemplo, seleccione Exchange Online.||
|Condiciones|||Configure condiciones específicas de su entorno y necesidades.|
||Riesgo de inicio de sesión||Vea las instrucciones de la tabla siguiente.|

### <a name="sign-in-risk-condition-settings"></a>Configuración de condición de riesgo de inicio de sesión

Aplica la configuración del nivel de riesgo en función del nivel de protección al que estás destinado.

|Nivel de protección|Valores de nivel de riesgo necesarios|Acción|
|---|---|---|
|Punto de inicio|Alto, medio|Compruebe ambos.|
|Empresa|Alto, medio, bajo|Compruebe los tres.|
|Seguridad especializada||Deje todas las opciones desactivadas para aplicar siempre MFA.|

En la **sección Controles de** Access:

|Configuración|Propiedades|Valores|Acción|
|---|---|---|---|
|Conceder|**Conceder acceso**||Seleccionar|
|||**Requerir autenticación multifactor**|Cheque|
||**Exigir todos los controles seleccionados**||Seleccionar|

Elija **Seleccionar** para guardar la **configuración de** concesión.

Por último, seleccione **Activar** para **Habilitar directiva** y, a continuación, elija **Crear**.

También considere la posibilidad de usar la [herramienta What if](/azure/active-directory/active-directory-conditional-access-whatif) para probar la directiva.

## <a name="block-clients-that-dont-support-multi-factor"></a>Bloquear clientes que no admiten factores múltiples

Use la configuración de estas tablas para una directiva de acceso condicional para bloquear clientes que no admiten la autenticación multifactor.

Vea [este artículo](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md) para obtener una lista de clientes en Microsoft 365 que admiten la autenticación multifactor.

En la **sección Asignaciones** :

|Configuración|Propiedades|Valores|Notas|
|---|---|---|---|
|Usuarios y grupos|Incluir|**Seleccione usuarios y grupos > usuarios y grupos**: seleccione grupos específicos que contengan cuentas de usuario dirigidas.|Comience con el grupo que incluye cuentas de usuario piloto.|
||Excluir|**Usuarios y grupos**: seleccione el grupo de excepciones acceso condicional; cuentas de servicio (identidades de aplicación).|La pertenencia debe modificarse según sea necesario y temporalmente.|
|Acciones o aplicaciones en la nube|**Aplicaciones en la nube > incluir**|**Seleccionar aplicaciones**: seleccione las aplicaciones correspondientes a los clientes que no admiten la autenticación moderna.||
|Condiciones|**Aplicaciones cliente**|Elija **Sí** para **Configurar** <p> Desactive las marcas de verificación para **aplicaciones de** explorador **y móviles y clientes de escritorio**||

En la **sección Controles de** Access:

|Configuración|Propiedades|Valores|Acción|
|---|---|---|---|
|Conceder|**Bloquear acceso**||Seleccionar|
||**Exigir todos los controles seleccionados**||Seleccionar|

Elija **Seleccionar** para guardar la **configuración de** concesión.

Por último, seleccione **Activar** para **Habilitar directiva** y, a continuación, elija **Crear**.

Considere la posibilidad de usar [la herramienta What if](/azure/active-directory/active-directory-conditional-access-whatif) para probar la directiva.

Por Exchange Online, puede usar directivas de autenticación para deshabilitar la autenticación [básica, lo](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) que fuerza a todas las solicitudes de acceso de cliente a usar la autenticación moderna.

## <a name="high-risk-users-must-change-password"></a>Los usuarios de riesgo alto tienen que cambiar la contraseña

Para asegurarse de que las cuentas comprometidas de todos los usuarios de alto riesgo se ven forzadas a realizar un cambio de contraseña al iniciar sesión, debe aplicar la siguiente directiva.

Inicie sesión en [Microsoft Azure Portal (https://portal.azure.com)](https://portal.azure.com/) con las credenciales de administrador y luego vaya a **Azure AD Identity Protection > Directiva de riesgo de usuario**.

En la **sección Asignaciones** :

|Tipo|Propiedades|Valores|Acción|
|---|---|---|---|
|Usuarios|Incluir|**Todos los usuarios**|Seleccionar|
|Riesgo de usuario|**Alto**||Seleccionar|

En la segunda **sección Asignaciones** :

|Tipo|Propiedades|Valores|Acción|
|---|---|---|---|
|Acceso|**Permitir acceso**||Seleccionar|
|||**Exigir cambio de contraseña**|Cheque|

Elija **Listo** para guardar la **configuración de Access** .

Por último, seleccione **Activar** para **Aplicar directiva** y, a continuación, **elija Guardar**.

Considere la posibilidad de usar [la herramienta What if](/azure/active-directory/active-directory-conditional-access-whatif) para probar la directiva.

Use esta directiva junto con [Configure Azure AD password protection](/azure/active-directory/authentication/concept-password-ban-bad), que detecta y bloquea las contraseñas débiles conocidas y sus variantes y términos débiles adicionales que son específicos de su organización. El Azure AD contraseña garantiza que las contraseñas modificadas sean seguras.

## <a name="apply-app-data-protection-policies"></a>Aplicar directivas de protección de datos de APP

Las APP definen qué aplicaciones se permiten y las acciones que pueden realizar con los datos de la organización. Las opciones disponibles en APP permiten a las organizaciones adaptar la protección a sus necesidades específicas. Para algunas de ellas, puede que no sea obvio qué configuración de directivas es necesaria para implementar un escenario completo. Para ayudar a las organizaciones a priorizar la protección del punto de conexión del cliente móvil, Microsoft ha introducido la taxonomía para su marco de protección de datos de APP para la administración de aplicaciones móviles de iOS y Android.

El marco de protección de datos de APP se organiza en tres niveles de configuración distintos, cada uno de ellos basado en el nivel anterior:

- **Nivel 1: Enterprise protección** de datos básica garantiza que las aplicaciones se protegen con un PIN y se cifran y realizan operaciones de borrado selectivo. En el caso de los dispositivos Android, este nivel valida la certificación de dispositivos Android. Se trata de una configuración de nivel de entrada que proporciona un control de protección de datos similar en las directivas de buzón de Exchange Online y que introduce tecnologías informáticas y el rellenado de usuarios en APP.
- **Nivel 2: Enterprise protección de datos mejorada** presenta mecanismos de prevención de pérdida de datos de APP y requisitos mínimos del sistema operativo. Esta es la configuración aplicable a la mayoría de los usuarios móviles que acceden a datos profesionales o educativos.
- **Nivel 3: Enterprise protección** de datos alta presenta mecanismos avanzados de protección de datos, una configuración de PIN mejorada y app Mobile Threat Defense. Esta configuración es conveniente para los usuarios que acceden a datos de alto riesgo.

A fin de ver las recomendaciones específicas para cada nivel de configuración y las aplicaciones mínimas que se deben proteger, revise [Marco de protección de datos mediante directivas de protección de aplicaciones](/mem/intune/apps/app-protection-framework).

Con los principios descritos en Las configuraciones de identidad de confianza cero y acceso a [dispositivos](microsoft-365-policies-configurations.md), los niveles de protección de punto de inicio y Enterprise se asignan estrechamente con la configuración de protección de datos mejorada de nivel 2 de empresa. El nivel de protección de seguridad especializada se asigna estrechamente a la configuración de protección de datos alta de nivel 3 de empresa.

|Nivel de protección|Directiva de protección de aplicaciones|Más información|
|---|---|---|
|Punto de inicio|[Protección de datos mejorada de nivel 2](/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|La configuración de directiva aplicada en el nivel 2 incluye todas las configuraciones de directiva recomendadas para el nivel 1 y solo agrega o actualiza la siguiente configuración de directiva para implementar más controles y una configuración más sofisticada que el nivel 1.|
|Empresa|[Protección de datos mejorada de nivel 2](/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|La configuración de directiva aplicada en el nivel 2 incluye todas las configuraciones de directiva recomendadas para el nivel 1 y solo agrega o actualiza la siguiente configuración de directiva para implementar más controles y una configuración más sofisticada que el nivel 1.|
|Seguridad especializada|[Protección de datos de nivel 3 de empresa alta](/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)|La configuración de directiva aplicada en el nivel 3 incluye toda la configuración de directiva recomendada para los niveles 1 y 2 y solo agrega o actualiza la siguiente configuración de directiva para implementar más controles y una configuración más sofisticada que el nivel 2.|

Para crear una nueva directiva de protección de aplicaciones para cada plataforma (iOS y Android) en Microsoft Endpoint Manager la configuración del marco de protección de datos, puede:

1. Cree manualmente las directivas siguiendo los pasos descritos en [How to create and deploy app protection policies with Microsoft Intune](/mem/intune/apps/app-protection-policies).
2. Importe las plantillas [JSON de Ejemplo de Intune App Protection Policy Configuration Framework](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) con los [scripts de PowerShell de Intune](https://github.com/microsoftgraph/powershell-intune-samples).

## <a name="require-approved-apps-and-app-protection"></a>Requerir aplicaciones aprobadas y protección de APLICACIONES

Para aplicar las directivas de protección de aplicaciones que aplicó en Intune, debe crear una directiva de acceso condicional para requerir aplicaciones cliente aprobadas y las condiciones establecidas en las directivas de protección de APLICACIONES.

La aplicación de directivas de protección de aplicaciones requiere un conjunto de directivas descritas en Requerir directiva de protección de aplicaciones para el acceso a aplicaciones en la nube [con acceso condicional](/azure/active-directory/conditional-access/app-protection-based-conditional-access). Estas directivas se incluyen en este conjunto recomendado de directivas de configuración de identidad y acceso.

Para crear la directiva de acceso condicional que requiere aplicaciones aprobadas y protección de aplicaciones, siga los pasos descritos en Requerir aplicaciones cliente aprobadas o directiva de protección de aplicaciones con dispositivos [móviles, que](/azure/active-directory/conditional-access/howto-policy-approved-app-or-app-protection#require-approved-client-apps-or-app-protection-policy-with-mobile-devices) solo permite que las cuentas dentro de aplicaciones móviles protegidas por directivas de protección de aplicaciones accedan Microsoft 365 puntos de conexión.

   > [!NOTE]
   > Esta directiva garantiza que los usuarios móviles puedan tener acceso a todos los Microsoft 365 con las aplicaciones aplicables.

Esta directiva también bloquea que Exchange ActiveSync clientes en dispositivos móviles se conecten a Exchange Online. Sin embargo, puedes crear una directiva independiente para controlar Exchange ActiveSync todos los dispositivos. Para obtener más información, vea [Bloquear clientes de ActiveSync](secure-email-recommended-policies.md#block-activesync-clients), que impide que los Exchange ActiveSync que aprovechan la autenticación básica se conecten a Exchange Online. Esta directiva no se muestra en la ilustración de la parte superior de este artículo. Se describe y se muestra en [Recomendaciones de directiva para proteger el correo electrónico](secure-email-recommended-policies.md).

 Esta directiva aprovecha los controles de concesión [Requerir aplicación cliente aprobada](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) y [Requerir directiva de protección de aplicaciones](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

Por último, el bloqueo de la autenticación heredada para otras aplicaciones cliente en dispositivos iOS y Android garantiza que estos clientes no puedan omitir las directivas de acceso condicional. Si sigue las instrucciones de este artículo, ya configuró Clientes de bloque que no [admiten la autenticación moderna](#block-clients-that-dont-support-multi-factor).

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>Definir directivas de cumplimiento de dispositivos

Las directivas de cumplimiento de dispositivos definen los requisitos que los dispositivos deben cumplir para determinarse como compatibles. Puede crear directivas de cumplimiento de dispositivos de Intune desde el centro Microsoft Endpoint Manager administración.

Debe crear una directiva para cada plataforma de PC, teléfono o tableta:

- Administrador de dispositivos Android
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 8.1 y posterior
- Windows 10 y versiones posteriores

Para crear directivas de cumplimiento de dispositivos, inicie sesión en el [Centro](https://endpoint.microsoft.com) de administración de Microsoft Endpoint Manager con sus credenciales de administrador y, a continuación, vaya a **Directivas** \> **de cumplimiento de dispositivos**\>. Seleccione **Crear directiva**.

Para que las directivas de cumplimiento de dispositivos se implementen, deben asignarse a grupos de usuarios. Una directiva se asigna después de crearla y guardarla. En el Centro de administración, seleccione la directiva y, a continuación, seleccione **Asignaciones**. Después de seleccionar los grupos que desea recibir la directiva, seleccione **Guardar** para guardar esa asignación de grupo e implementar la directiva.

Para obtener instrucciones paso a paso sobre cómo crear directivas de cumplimiento en Intune, consulte [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy) en la documentación de Intune.

### <a name="recommended-settings-for-ios"></a>Configuración recomendada para iOS

iOS/iPadOS admite varios escenarios de inscripción, dos de los cuales se tratan como parte de este marco:

- [Inscripción de dispositivos para dispositivos de](/mem/intune/enrollment/ios-enroll) propiedad personal: estos dispositivos son de propiedad personal y se usan para uso personal y laboral.
- [Inscripción de dispositivos automatizada](/mem/intune/enrollment/device-enrollment-program-enroll-ios) supervisada para dispositivos de propiedad corporativa: estos dispositivos son de propiedad corporativa, están asociados con un solo usuario y se usan exclusivamente para el trabajo y no para uso personal.

El marco de configuración de seguridad de iOS/iPadOS se organiza en varios escenarios de configuración distintos, lo que proporciona instrucciones para dispositivos de propiedad personal y supervisados.

Para dispositivos de propiedad personal:

- Seguridad básica (nivel 1): Microsoft recomienda esta configuración como la configuración de seguridad mínima para dispositivos personales en los que los usuarios tienen acceso a datos profesionales o educativos. Para ello, se aplican directivas de contraseñas y características de bloqueo de dispositivo, y se deshabilitan determinadas funciones de los dispositivos (p. ej., certificados no confiables).
- Seguridad mejorada (nivel 2): Microsoft recomienda esta configuración para dispositivos en los que los usuarios tienen acceso a información confidencial o confidencial. Esta configuración establece controles de uso compartido de datos. Esta configuración es aplicable a la mayoría de los usuarios móviles que acceden a los datos profesionales o educativos de un dispositivo.
- Alta seguridad (nivel 3): Microsoft recomienda esta configuración para dispositivos usados por usuarios o grupos específicos de alto riesgo (usuarios que manejan datos altamente confidenciales donde la divulgación no autorizada causa una pérdida considerable de material para la organización). Esta configuración aplica directivas de contraseñas más seguras, deshabilita determinadas funciones de dispositivo y aplica restricciones de transferencia de datos adicionales.

Para dispositivos supervisados:

- Seguridad básica (nivel 1): Microsoft recomienda esta configuración como la configuración de seguridad mínima para dispositivos supervisados en los que los usuarios tienen acceso a datos profesionales o educativos. Para ello, se aplican directivas de contraseñas y características de bloqueo de dispositivo, y se deshabilitan determinadas funciones de los dispositivos (p. ej., certificados no confiables).
- Seguridad mejorada (nivel 2): Microsoft recomienda esta configuración para dispositivos en los que los usuarios tienen acceso a información confidencial o confidencial. Esta configuración aplica controles de uso compartido de datos y bloquea el acceso a dispositivos USB. Esta configuración es aplicable a la mayoría de los usuarios móviles que acceden a los datos profesionales o educativos de un dispositivo.
- Alta seguridad (nivel 3): Microsoft recomienda esta configuración para dispositivos usados por usuarios o grupos específicos de alto riesgo (usuarios que manejan datos altamente confidenciales donde la divulgación no autorizada causa una pérdida considerable de material para la organización). Esta configuración establece directivas de contraseña más sólidas, deshabilita determinadas funciones de dispositivo, aplica restricciones adicionales de transferencia de datos y requiere que las aplicaciones se instalen a través del programa de compra por volumen de Apple.

Con los principios descritos en Las configuraciones de identidad de confianza cero y acceso a [dispositivos](microsoft-365-policies-configurations.md), los niveles de protección de punto de inicio y Enterprise se asignan estrechamente con la configuración de seguridad mejorada de nivel 2. El nivel de protección de seguridad especializada se asigna estrechamente a la configuración de alta seguridad de nivel 3.

|Nivel de protección  |Directiva de dispositivos |Más información  |
|---------|---------|---------|
|Punto de inicio     |Seguridad mejorada (nivel 2)         |La configuración de directiva aplicada en el nivel 2 incluye todas las configuraciones de directiva recomendadas para el nivel 1 y solo agrega o actualiza la siguiente configuración de directiva para implementar más controles y una configuración más sofisticada que el nivel 1.         |
|Empresa     |Seguridad mejorada (nivel 2)         |La configuración de directiva aplicada en el nivel 2 incluye todas las configuraciones de directiva recomendadas para el nivel 1 y solo agrega o actualiza la siguiente configuración de directiva para implementar más controles y una configuración más sofisticada que el nivel 1.         |
|Seguridad especializada     |Seguridad alta (nivel 3)         |La configuración de directiva aplicada en el nivel 3 incluye toda la configuración de directiva recomendada para los niveles 1 y 2 y solo agrega o actualiza la siguiente configuración de directiva para implementar más controles y una configuración más sofisticada que el nivel 2.         |

Para ver las recomendaciones específicas de cumplimiento de dispositivos y restricciones de dispositivos para cada nivel de configuración, revise el marco de configuración de seguridad de [iOS/iPadOS](/mem/intune/enrollment/ios-ipados-configuration-framework).

### <a name="recommended-settings-for-android"></a>Configuración recomendada para Android

Android Enterprise varios escenarios de inscripción, dos de los cuales se tratan como parte de este marco:

- [Android Enterprise de](/intune/android-work-profile-enroll) trabajo: este modelo de inscripción suele usarse para dispositivos de propiedad personal, donde TI quiere proporcionar un límite de separación claro entre datos personales y laborales. Las directivas controladas por IT garantizan que los datos de trabajo no se puedan transferir al perfil personal.
- [Android Enterprise totalmente](/intune/android-fully-managed-enroll) administrados: estos dispositivos son de propiedad corporativa, asociados con un único usuario y se usan exclusivamente para el trabajo y no para uso personal.

El marco Enterprise configuración de seguridad de Android se organiza en varios escenarios de configuración distintos, lo que proporciona instrucciones para perfiles de trabajo y escenarios totalmente administrados.

Para dispositivos Enterprise de perfil de trabajo de Android:

- Seguridad mejorada del perfil de trabajo (nivel 2): Microsoft recomienda esta configuración como la configuración de seguridad mínima para dispositivos personales en los que los usuarios tienen acceso a datos profesionales o educativos. Esta configuración presenta los requisitos de contraseña, separa los datos profesionales y personales y valida la atestación de dispositivos Android.
- Seguridad alta del perfil de trabajo (nivel 3): Microsoft recomienda esta configuración para dispositivos usados por usuarios o grupos específicos de alto riesgo (usuarios que manejan datos altamente confidenciales donde la divulgación no autorizada causa una pérdida considerable de material a la organización). Esta configuración presenta la defensa contra amenazas móviles o Microsoft Defender para Endpoint, establece la versión mínima de Android, establece directivas de contraseña más seguras y restringe aún más la separación personal y laboral.

Para dispositivos Android Enterprise totalmente administrados:

- Seguridad básica totalmente administrada (nivel 1): Microsoft recomienda esta configuración como la configuración de seguridad mínima para un dispositivo de empresa. Esta configuración se aplica a la mayoría de los usuarios móviles que acceden a datos laborales o educativos. Esta configuración presenta los requisitos de contraseña, establece la versión mínima de Android y establece ciertas restricciones de dispositivo.
- Seguridad mejorada totalmente administrada (nivel 2): Microsoft recomienda esta configuración para dispositivos donde los usuarios tienen acceso a información confidencial o confidencial. Esta configuración aprueba directivas de contraseña más sólidas y deshabilita las capacidades de usuario/cuenta.
- Alta seguridad totalmente administrada (nivel 3): Microsoft recomienda esta configuración para dispositivos usados por usuarios o grupos específicos que son de riesgo exclusivo (usuarios que administran datos altamente confidenciales donde la divulgación no autorizada causa una pérdida considerable de material para la organización). Esta configuración aumenta la versión mínima de Android, presenta la defensa contra amenazas móviles o Microsoft Defender para endpoint y aplica restricciones de dispositivos adicionales.

Con los principios descritos en Las configuraciones de identidad de confianza cero y acceso a [dispositivos](microsoft-365-policies-configurations.md), los niveles de protección de punto inicial y Enterprise se asignan estrechamente con la seguridad básica de nivel 1 para dispositivos de propiedad personal y la configuración de seguridad mejorada de nivel 2 para dispositivos totalmente administrados. El nivel de protección de seguridad especializada se asigna estrechamente a la configuración de alta seguridad de nivel 3.

Para dispositivos Enterprise de perfil de trabajo de Android:

|Nivel de protección  |Directiva de dispositivos |Más información  |
|---------|---------|---------|
|Punto de inicio     |Perfil de trabajo: seguridad básica (nivel 1)      |N/D         |
|Empresa     |Perfil de trabajo: seguridad básica (nivel 1)         |N/D         |
|Punto de inicio     |Totalmente administrado: seguridad mejorada (nivel 2)       |La configuración de directiva aplicada en el nivel 2 incluye todas las configuraciones de directiva recomendadas para el nivel 1 y solo agrega o actualiza la siguiente configuración de directiva para implementar más controles y una configuración más sofisticada que el nivel 1.         |
|Empresa     |Totalmente administrado: seguridad mejorada (nivel 2)         |La configuración de directiva aplicada en el nivel 2 incluye todas las configuraciones de directiva recomendadas para el nivel 1 y solo agrega o actualiza la siguiente configuración de directiva para implementar más controles y una configuración más sofisticada que el nivel 1.         |
|Seguridad especializada     |Seguridad alta (nivel 3)         |La configuración de directiva aplicada en el nivel 3 incluye toda la configuración de directiva recomendada para los niveles 1 y 2 y solo agrega o actualiza la siguiente configuración de directiva para implementar más controles y una configuración más sofisticada que el nivel 2.         |

Para ver las recomendaciones específicas de cumplimiento de dispositivos y restricciones de dispositivos para cada nivel de configuración, revise el marco de configuración de seguridad de [Android Enterprise.](/mem/intune/enrollment/android-configuration-framework)

### <a name="recommended-settings-for-windows-10-and-later"></a>Configuración recomendada para Windows 10 y versiones posteriores

Se recomiendan las siguientes opciones de configuración para equipos que ejecutan Windows 10 y versiones posteriores, tal como se configura en **paso 2: Configuración** de cumplimiento, del proceso de creación de directivas.

Para **obtener información sobre > Windows de evaluación del servicio de atestación** de estado del dispositivo, consulte esta tabla.

|Propiedades|Valor|Acción|
|---|---|---|
|Requerir BitLocker|Obligatoria|Seleccionar|
|Requerir que el arranque seguro esté habilitado en el dispositivo|Obligatoria|Seleccionar|
|Requerir integridad de código|Obligatoria|Seleccionar|

Para **las propiedades del dispositivo**, especifique los valores adecuados para las versiones del sistema operativo en función de las directivas de TI y seguridad.

Para **El cumplimiento de Configuration Manager**, seleccione **Requerir**.

Para **Seguridad del sistema**, consulte esta tabla.

|Tipo|Propiedades|Valor|Acción|
|---|---|---|---|
|Password|Requerir una contraseña para desbloquear dispositivos móviles|Obligatoria|Seleccionar|
||Contraseñas sencillas|Bloquear|Seleccionar|
||Tipo de contraseña|Valor predeterminado del dispositivo|Seleccionar|
||Longitud mínima de la contraseña|6 |Tipo|
||Máximo de minutos de inactividad antes de solicitar la contraseña|15 |Tipo <p> Esta configuración es compatible con las versiones 4.0 y posteriores de Android o KNOX 4.0 y versiones posteriores. Para dispositivos iOS, es compatible con iOS 8.0 y versiones posteriores.|
||Expiración de contraseña (días)|41|Tipo|
||Número de contraseñas anteriores que no se pueden reutilizar|5|Tipo|
||Requerir contraseña cuando el dispositivo devuelve el estado de inactividad (móvil y holográfico)|Obligatoria|Disponible para Windows 10 versiones posteriores|
|Cifrado|Cifrado de almacenamiento de datos en el dispositivo|Obligatoria|Seleccionar|
|Seguridad de dispositivos|Firewall|Obligatoria|Seleccionar|
||Antivirus|Obligatoria|Seleccionar|
||Antiespía|Obligatoria|Seleccionar <p> Esta configuración requiere una solución anti spyware registrada con la Seguridad de Windows aplicación.|
|Defender para la nube|Antimalware de Microsoft Defender|Obligatoria|Seleccionar|
||Versión mínima de Antimalware de Microsoft Defender||Tipo <p> Solo se admite para Windows 10 escritorio. Microsoft recomienda versiones no más de cinco detrás de la versión más reciente.|
||Firma antimalware de Microsoft Defender actualizada|Obligatoria|Seleccionar|
||Protección en tiempo real|Obligatoria|Seleccionar <p> Solo se admite para Windows 10 escritorio posterior|

#### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender para punto de conexión

|Tipo|Propiedades|Valor|Acción|
|---|---|---|---|
|Reglas de Microsoft Defender para endpoint en el Centro Microsoft Endpoint Manager administración|[Requerir que el dispositivo esté en o bajo la puntuación de riesgo de la máquina](/mem/intune/protect/advanced-threat-protection-configure#create-and-assign-compliance-policy-to-set-device-risk-level)|Medio|Seleccionar|

<!--
## Require compliant PCs (but not compliant phones and tablets)

Before adding a policy to require compliant PCs, be sure to enroll your devices for management in Intune. Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user.

To require compliant PCs:

1. Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.
2. In the list of Azure services, choose **Azure Active Directory**.
3. In the **Manage** list, choose **Security**, and then choose **Conditional Access**.
4. Choose **New policy** and type the new policy's name.

5. Under **Assignments**, choose **Users and groups** and include who you want the policy to apply to. Also exclude your Conditional Access exclusion group.

6. Under **Assignments**, choose **Cloud apps or actions**.

7. For **Include**, choose **Select apps > Select**, and then select the desired apps from the **Cloud apps** list. For example, select Office 365. Choose **Select** when done.

8. To require compliant PCs (but not compliant phones and tablets), under **Assignments**, choose **Conditions > Device platforms**. Select **Yes** for **Configure**. Choose  **Select device platforms**, select **Yes** and select **Any device** and under Exclude select **iOS** and **Android**, and then choose **Done**.

9. Under **Access controls**, choose **Grant** .

10. Choose **Grant access** and then check **Require device to be marked as compliant**. For multiple controls, select **Require all the selected controls**. When complete, choose **Select**.

11. Select **On** for **Enable policy**, and then choose **Create**.

> [!NOTE]
> Make sure that your device is compliant before enabling this policy. Otherwise, you could get locked out and will be unable to change this policy until your user account has been added to the Conditional Access exclusion group.

--> 

## <a name="require-compliant-pcs-and-mobile-devices"></a>Requerir equipos y dispositivos móviles compatibles

Para requerir el cumplimiento de todos los dispositivos:

1. Vaya al [Azure Portal](https://portal.azure.com) e inicie sesión con sus credenciales.
2. En la lista de servicios de Azure, elija **Azure Active Directory**.
3. En la **lista Administrar** , elija **Seguridad** y, a continuación, **elija Acceso condicional**.
4. Elija **Nueva directiva** y escriba el nombre de la nueva directiva.

5. En **Asignaciones**, elija **Usuarios y grupos** e incluya a quién desea que se aplique la directiva. También excluya el grupo de exclusión acceso condicional.

6. En **Asignaciones**, elija **Aplicaciones o acciones en la nube**.

7. Para **Incluir**, elige **Seleccionar aplicaciones > Seleccionar** y, a continuación, selecciona las aplicaciones deseadas de la **lista Aplicaciones en** la nube. Por ejemplo, seleccione Office 365. Elija **Seleccionar** cuando haya terminado.

8. En **Controles de Access**, elija **Conceder** .

9. Elija **Conceder acceso y** , a continuación, **compruebe Requerir que el dispositivo se marque como compatible**. Para varios controles, seleccione **Requerir todos los controles seleccionados**. Cuando se complete, elija **Seleccionar**.

10. Seleccione **Activar para** **Habilitar directiva** y, a continuación, **elija Crear**.

> [!NOTE]
> Asegúrate de que el dispositivo es compatible antes de habilitar esta directiva. De lo contrario, podría bloquearse y no podrá cambiar esta directiva hasta que su cuenta de usuario se haya agregado al grupo de exclusión acceso condicional.

## <a name="next-step"></a>Paso siguiente

[![Paso 3: Directivas para usuarios invitados y externos.](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png)](identity-access-policies-guest-access.md)

[Más información sobre las recomendaciones de directiva para usuarios invitados y externos](identity-access-policies-guest-access.md)
