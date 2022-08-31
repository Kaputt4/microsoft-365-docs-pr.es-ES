---
title: 'Directivas comunes de acceso a dispositivos e identidades de Confianza cero: Microsoft 365 para empresas | Microsoft Docs'
description: Describe las directivas y configuraciones de acceso a dispositivos e identidades comunes recomendadas de Confianza cero.
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
- zerotrust-solution
- highpri
ms.technology: mdo
ms.openlocfilehash: e47dffc84870a34cb22aa8246b82ce230bcd7ebd
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67468193"
---
# <a name="common-zero-trust-identity-and-device-access-policies"></a>Directivas comunes de acceso a dispositivos e identidades de Confianza cero

En este artículo se describen las directivas comunes recomendadas de Confianza cero identidad y acceso a dispositivos para proteger el acceso a los servicios en la nube de Microsoft 365, incluidas las aplicaciones locales publicadas con Azure Active Directory (Azure AD) Application Proxy.

En esta guía se describe cómo implementar las directivas recomendadas en un entorno recién aprovisionado. La configuración de estas directivas en un entorno de laboratorio independiente le permite comprender y evaluar las directivas recomendadas antes de almacenar provisionalmente el lanzamiento en los entornos de preproducción y producción. El entorno recién aprovisionado puede ser solo en la nube o híbrido para reflejar sus necesidades de evaluación.

## <a name="policy-set"></a>Conjunto de directivas

En el diagrama siguiente se muestra el conjunto recomendado de directivas. Muestra a qué nivel de protecciones se aplica cada directiva y si las directivas se aplican a equipos, teléfonos y tabletas, o a ambas categorías de dispositivos. También indica dónde se configuran estas directivas.

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png" alt-text="Directivas comunes para configurar Confianza cero identidad y acceso al dispositivo." lightbox="../../media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png":::

<!--

Here's a one-page PDF summary:

[![Thumb image for the Zero Trust identity and device protection for Microsoft 365 handout.](../../media/microsoft-365-policies-configurations/zero-trust-id-device-protection-model-handout-thumbnail.png)](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) <br> [View as a PDF](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) \| [Download as a PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf)

-->

En el resto de este artículo se describe cómo configurar estas directivas.

> [!NOTE]
> Se recomienda requerir el uso de la autenticación multifactor (MFA) antes de inscribir dispositivos en Intune para garantizar que el dispositivo esté en posesión del usuario previsto. Debe inscribir dispositivos en Intune para poder aplicar las directivas de cumplimiento de dispositivos.

Para darle tiempo para realizar estas tareas, se recomienda implementar las directivas de punto de partida en el orden indicado en esta tabla. Sin embargo, las directivas de MFA para los niveles de protección empresariales y especializados se pueden implementar en cualquier momento.

|Nivel de protección|Directivas|Más información|Licencias|
|---|---|---|---|
|**Punto de inicio**|[Requerir MFA cuando el riesgo de inicio de sesión es *medio* o *alto*](#require-mfa-based-on-sign-in-risk)||Microsoft 365 E5 o Microsoft 365 E3 con el complemento de seguridad E5|
||[Bloquear a los clientes que no sean compatibles con la autenticación moderna](#block-clients-that-dont-support-multi-factor)|Los clientes que no usan la autenticación moderna pueden omitir las directivas de acceso condicional, por lo que es importante bloquearlas.|Microsoft 365 E3 o E5|
||[Los usuarios de riesgo alto tienen que cambiar la contraseña](#high-risk-users-must-change-password)|Obliga a los usuarios a cambiar su contraseña al iniciar sesión si se detecta actividad de alto riesgo para su cuenta.|Microsoft 365 E5 o Microsoft 365 E3 con el complemento de seguridad E5|
||[Aplicar protección de datos de directivas de protección de aplicaciones (APP)](#apply-app-data-protection-policies)|Una directiva de Protección de aplicaciones de Intune por plataforma (Windows, iOS/iPadOS, Android).|Microsoft 365 E3 o E5|
||[Requerir aplicaciones aprobadas y protección de aplicaciones](#require-approved-apps-and-app-protection)|Aplica la protección de aplicaciones móviles para teléfonos y tabletas con iOS, iPadOS o Android.|Microsoft 365 E3 o E5|
|**Empresarial**|[Requerir MFA cuando el riesgo de inicio de sesión es *bajo*, *medio* o *alto*](#require-mfa-based-on-sign-in-risk)||Microsoft 365 E5 o Microsoft 365 E3 con el complemento de seguridad E5|
||[Definición de directivas de cumplimiento de dispositivos](#define-device-compliance-policies)|Una directiva para cada plataforma.|Microsoft 365 E3 o E5|
||[Requerir equipos compatibles y dispositivos móviles](#require-compliant-pcs-and-mobile-devices)|Exige la administración de Intune para equipos (Windows o macOS) y teléfonos o tabletas (iOS, iPadOS o Android).|Microsoft 365 E3 o E5|
|**Seguridad especializada**|[*Siempre* se requiere MFA](#assigning-policies-to-groups-and-users)||Microsoft 365 E3 o E5|

## <a name="assigning-policies-to-groups-and-users"></a>Asignación de directivas a grupos y usuarios

Antes de configurar las directivas, identifique los grupos de Azure AD que usa para cada nivel de protección. Normalmente, la protección de punto de partida se aplica a todos los usuarios de la organización. Un usuario que se incluya para el punto de partida y la protección empresarial tendrá todas las directivas de punto de inicio aplicadas más las directivas de empresa. La protección es acumulativa y se aplica la directiva más restrictiva.

Una práctica recomendada consiste en crear un grupo de Azure AD para la exclusión de acceso condicional. Agregue este grupo a todas las directivas de acceso condicional en el valor **Excluir** de la configuración **Usuarios y grupos** de la sección **Asignaciones** . Esto le proporciona un método para proporcionar acceso a un usuario mientras soluciona problemas de acceso. Esto solo se recomienda como solución temporal. Supervise este grupo en busca de cambios y asegúrese de que el grupo de exclusión solo se usa según lo previsto.

Este es un ejemplo de asignación de grupos y exclusiones para requerir MFA.

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png" alt-text="Asignación y exclusiones de grupos de ejemplo para directivas de MFA" lightbox="../../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png":::

Estos son los resultados:

- Todos los usuarios deben usar MFA cuando el riesgo de inicio de sesión es medio o alto.

- Los miembros del grupo Personal ejecutivo deben usar MFA cuando el riesgo de inicio de sesión es bajo, medio o alto.

  En este caso, los miembros del grupo Personal ejecutivo coinciden tanto con el punto de partida como con las directivas de acceso condicional de la empresa. Se combinan los controles de acceso para ambas directivas, que en este caso son equivalentes a la directiva de acceso condicional de empresa.

- Los miembros del grupo top secret project X siempre son necesarios para usar MFA.

  En este caso, los miembros del grupo Top Secret Project X coinciden tanto con el punto inicial como con las directivas de acceso condicional de seguridad especializadas. Se combinan los controles de acceso para ambas directivas. Dado que el control de acceso para la directiva de acceso condicional de seguridad especializada es más restrictivo, se usa.

Tenga cuidado al aplicar niveles más altos de protección a grupos y usuarios. Por ejemplo, los miembros del grupo Top Secret Project X tendrán que usar MFA cada vez que inicien sesión, incluso si no están trabajando en el contenido de seguridad especializado para Project X.

Todos los grupos de Azure AD creados como parte de estas recomendaciones deben crearse como grupos de Microsoft 365. Esto es importante para la implementación de etiquetas de confidencialidad al proteger documentos en Microsoft Teams y SharePoint.

:::image type="content" source="../../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png" alt-text="Creación de un grupo de Microsoft 365" lightbox="../../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png":::

## <a name="require-mfa-based-on-sign-in-risk"></a>Requerir MFA en función del riesgo de inicio de sesión

Debe hacer que los usuarios se registren para MFA antes de requerir su uso. Si tiene Microsoft 365 E5, Microsoft 365 E3 con el complemento de seguridad E5, Office 365 con EMS E5 o licencias individuales de Azure AD Premium P2, puede usar la directiva de registro de MFA con Azure AD Identity Protection para requerir que los usuarios se registren en MFA. El [trabajo de requisitos previos](identity-access-prerequisites.md) incluye el registro de todos los usuarios con MFA.

Una vez registrados los usuarios, puede requerir MFA para el inicio de sesión con una nueva directiva de acceso condicional.

1. Vaya al [Azure Portal](https://portal.azure.com) e inicie sesión con sus credenciales.
2. En la lista de servicios de Azure, elija **Azure Active Directory**.
3. En la lista **Administrar** , elija **Seguridad** y, después, **Acceso condicional**.
4. Elija **Nueva directiva** y escriba el nombre de la nueva directiva.

En las tablas siguientes se describe la configuración de la directiva de acceso condicional para requerir MFA en función del riesgo de inicio de sesión.

En la sección **Asignaciones** :

|Setting|Propiedades|Valores|Notas|
|---|---|---|---|
|Usuarios y grupos|Incluir|**Seleccione usuarios y grupos > Usuarios y grupos**: seleccione grupos específicos que contengan cuentas de usuario de destino.|Comience con el grupo que incluye cuentas de usuario piloto.|
||Excluir|**Usuarios y grupos**: seleccione el grupo de excepciones de acceso condicional; cuentas de servicio (identidades de aplicación).|La pertenencia debe modificarse de forma temporal según sea necesario.|
|Aplicaciones o acciones en la nube|**Aplicaciones en la nube > Incluir**|**Seleccionar aplicaciones**: seleccione las aplicaciones a las que desea aplicar esta directiva. Por ejemplo, seleccione Exchange Online.||
|Condiciones|||Configure condiciones específicas de su entorno y necesidades.|
||Riesgo de inicio de sesión||Consulte las instrucciones de la tabla siguiente.|

### <a name="sign-in-risk-condition-settings"></a>Configuración de la condición de riesgo de inicio de sesión

Aplique la configuración del nivel de riesgo en función del nivel de protección que tenga como destino.

|Nivel de protección|Valores de nivel de riesgo necesarios|Acción|
|---|---|---|
|Punto de inicio|Alto, medio|Compruebe ambas cosas.|
|Enterprise|Alto, medio, bajo|Compruebe los tres.|
|Seguridad especializada||Deje desactivadas todas las opciones para aplicar siempre MFA.|

En la sección **Controles de acceso** :

|Setting|Propiedades|Valores|Acción|
|---|---|---|---|
|Conceder|**Conceder acceso**||Seleccionar|
|||**Requerir autenticación multifactor**|Cheque|
||**Exigir todos los controles seleccionados**||Seleccionar|

Elija **Seleccionar** para guardar la configuración **de concesión** .

Por último, seleccione **Activado** para **Habilitar directiva** y, a continuación, elija **Crear**.

Considere también el uso de la herramienta [What if](/azure/active-directory/active-directory-conditional-access-whatif) para probar la directiva.

## <a name="block-clients-that-dont-support-multi-factor"></a>Bloquear clientes que no admiten multifactor

Use la configuración de estas tablas para una directiva de acceso condicional para bloquear los clientes que no admiten la autenticación multifactor.

Consulte [este artículo](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md) para obtener una lista de los clientes de Microsoft 365 que admiten la autenticación multifactor.

En la sección **Asignaciones** :

|Setting|Propiedades|Valores|Notas|
|---|---|---|---|
|Usuarios y grupos|Incluir|**Seleccione usuarios y grupos > Usuarios y grupos**: seleccione grupos específicos que contengan cuentas de usuario de destino.|Comience con el grupo que incluye cuentas de usuario piloto.|
||Excluir|**Usuarios y grupos**: seleccione el grupo de excepciones de acceso condicional; cuentas de servicio (identidades de aplicación).|La pertenencia debe modificarse de forma temporal según sea necesario.|
|Aplicaciones o acciones en la nube|**Aplicaciones en la nube > Incluir**|**Seleccionar aplicaciones**: seleccione las aplicaciones correspondientes a los clientes que no admiten la autenticación moderna.||
|Condiciones|**Aplicaciones cliente**|Elija **Sí** para **Configurar**. <p> Desactive las marcas de verificación para las aplicaciones **de explorador** y **móviles y los clientes de escritorio**.||

En la sección **Controles de acceso** :

|Setting|Propiedades|Valores|Acción|
|---|---|---|---|
|Conceder|**Bloquear acceso**||Seleccionar|
||**Exigir todos los controles seleccionados**||Seleccionar|

Elija **Seleccionar** para guardar la configuración **de concesión** .

Por último, seleccione **Activado** para **Habilitar directiva** y, a continuación, elija **Crear**.

Considere la posibilidad de usar la herramienta [What if](/azure/active-directory/active-directory-conditional-access-whatif) para probar la directiva.

Por Exchange Online, puede usar directivas de autenticación para deshabilitar la [autenticación básica](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online), lo que obliga a todas las solicitudes de acceso de cliente a usar la autenticación moderna.

## <a name="high-risk-users-must-change-password"></a>Los usuarios de riesgo alto tienen que cambiar la contraseña

Para asegurarse de que todas las cuentas en peligro de los usuarios de alto riesgo se ven obligadas a realizar un cambio de contraseña al iniciar sesión, debe aplicar la siguiente directiva.

Inicie sesión en [Microsoft Azure Portal (https://portal.azure.com)](https://portal.azure.com/) con las credenciales de administrador y luego vaya a **Azure AD Identity Protection > Directiva de riesgo de usuario**.

En la sección **Asignaciones** :

|Tipo|Propiedades|Valores|Acción|
|---|---|---|---|
|Usuarios|Incluir|**Todos los usuarios**|Seleccionar|
|Riesgo de usuario|**Alto**||Seleccionar|

En la segunda sección **Asignaciones** :

|Tipo|Propiedades|Valores|Acción|
|---|---|---|---|
|Acceso|**Permitir acceso**||Seleccionar|
|||**Exigir cambio de contraseña**|Cheque|

Elija **Listo** para guardar la configuración de **Access** .

Por último, seleccione **Activado** para **Aplicar directiva** y, a continuación, elija **Guardar**.

Considere la posibilidad de usar la herramienta [What if](/azure/active-directory/active-directory-conditional-access-whatif) para probar la directiva.

Use esta directiva junto con [Configurar la protección con contraseña de Azure AD](/azure/active-directory/authentication/concept-password-ban-bad), que detecta y bloquea las contraseñas no seguras conocidas y sus variantes y términos débiles adicionales específicos de su organización. El uso de la protección con contraseña de Azure AD garantiza que las contraseñas modificadas sean seguras.

## <a name="apply-app-data-protection-policies"></a>Aplicación de directivas de protección de datos de APLICACIONES

Las API definen qué aplicaciones se permiten y las acciones que pueden realizar con los datos de la organización. Las opciones disponibles en APP permiten a las organizaciones adaptar la protección a sus necesidades específicas. Para algunas de ellas, puede que no sea obvio qué configuración de directivas es necesaria para implementar un escenario completo. Para ayudar a las organizaciones a priorizar la protección del punto de conexión del cliente móvil, Microsoft ha introducido la taxonomía para su marco de protección de datos de APP para la administración de aplicaciones móviles de iOS y Android.

El marco de protección de datos de APP se organiza en tres niveles de configuración distintos, cada uno de ellos basado en el nivel anterior:

- **Nivel 1: la protección de datos básica de empresa** garantiza que las aplicaciones estén protegidas con un PIN y cifradas y realice operaciones de borrado selectivo. En el caso de los dispositivos Android, este nivel valida la certificación de dispositivos Android. Se trata de una configuración de nivel de entrada que proporciona un control de protección de datos similar en las directivas de buzón de Exchange Online y que introduce tecnologías informáticas y el rellenado de usuarios en APP.
- **Nivel 2: La protección de datos mejorada para empresas** presenta mecanismos de prevención de pérdida de datos de APP y requisitos mínimos del sistema operativo. Esta es la configuración aplicable a la mayoría de los usuarios móviles que acceden a datos profesionales o educativos.
- **Nivel 3: La alta protección de datos empresarial** presenta mecanismos avanzados de protección de datos, una configuración mejorada del PIN y APP Mobile Threat Defense. Esta configuración es conveniente para los usuarios que acceden a datos de alto riesgo.

A fin de ver las recomendaciones específicas para cada nivel de configuración y las aplicaciones mínimas que se deben proteger, revise [Marco de protección de datos mediante directivas de protección de aplicaciones](/mem/intune/apps/app-protection-framework).

Con los principios descritos en [Confianza cero configuraciones de acceso a dispositivos e identidades](microsoft-365-policies-configurations.md), los niveles De punto de inicio y Protección empresarial se asignan estrechamente con la configuración de protección de datos mejorada empresarial de nivel 2. El nivel de protección de seguridad especializada se asigna estrechamente a la configuración de protección de datos alta empresarial de nivel 3.

|Nivel de protección|Directiva de protección de aplicaciones|Más información|
|---|---|---|
|Punto de inicio|[Protección de datos mejorada de nivel 2](/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|La configuración de directiva aplicada en el nivel 2 incluye todas las opciones de configuración de directiva recomendadas para el nivel 1 y solo agrega o actualiza la siguiente configuración de directiva para implementar más controles y una configuración más sofisticada que el nivel 1.|
|Enterprise|[Protección de datos mejorada de nivel 2](/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|La configuración de directiva aplicada en el nivel 2 incluye todas las opciones de configuración de directiva recomendadas para el nivel 1 y solo agrega o actualiza la siguiente configuración de directiva para implementar más controles y una configuración más sofisticada que el nivel 1.|
|Seguridad especializada|[Protección de datos alta empresarial de nivel 3](/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)|La configuración de directiva aplicada en el nivel 3 incluye todas las opciones de configuración de directiva recomendadas para los niveles 1 y 2 y solo agrega o actualiza la siguiente configuración de directiva para implementar más controles y una configuración más sofisticada que el nivel 2.|

Para crear una nueva directiva de protección de aplicaciones para cada plataforma (iOS y Android) en Microsoft Endpoint Manager mediante la configuración del marco de protección de datos, puede:

1. Cree manualmente las directivas siguiendo los pasos descritos en [Creación e implementación de directivas de protección de aplicaciones con Microsoft Intune](/mem/intune/apps/app-protection-policies).
2. Importe el ejemplo [Intune plantillas JSON de App Protection Policy Configuration Framework](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) con [los scripts de PowerShell de Intune](https://github.com/microsoftgraph/powershell-intune-samples).

## <a name="require-approved-apps-and-app-protection"></a>Requerir aplicaciones aprobadas y protección de aplicaciones

Para aplicar las directivas de Protección de aplicaciones que aplicó en Intune, debe crear una directiva de acceso condicional para requerir aplicaciones cliente aprobadas y las condiciones establecidas en las directivas de protección de aplicaciones.

La aplicación de directivas de Protección de aplicaciones requiere un conjunto de directivas que se describen en Requerir directiva de [protección de aplicaciones para el acceso a aplicaciones en la nube con acceso condicional](/azure/active-directory/conditional-access/app-protection-based-conditional-access). Estas directivas se incluyen en este conjunto recomendado de directivas de configuración de identidad y acceso.

Para crear la directiva de acceso condicional que requiere aplicaciones aprobadas y protección de aplicaciones, siga los pasos descritos en [Requerir aplicaciones cliente aprobadas o directiva de protección de aplicaciones con dispositivos móviles](/azure/active-directory/conditional-access/howto-policy-approved-app-or-app-protection#require-approved-client-apps-or-app-protection-policy-with-mobile-devices), que solo permite que las cuentas de las aplicaciones móviles protegidas por directivas de Protección de aplicaciones accedan a los puntos de conexión de Microsoft 365.

   > [!NOTE]
   > Esta directiva garantiza que los usuarios móviles puedan acceder a todos los puntos de conexión de Microsoft 365 mediante las aplicaciones aplicables.

Esta directiva también impide que Exchange ActiveSync clientes de dispositivos móviles se conecten a Exchange Online. Sin embargo, puede crear una directiva independiente para controlar Exchange ActiveSync en todos los dispositivos. Para obtener más información, vea [Bloquear clientes activesync](secure-email-recommended-policies.md#block-activesync-clients), lo que impide que Exchange ActiveSync clientes que aprovechan la autenticación básica se conecten a Exchange Online. Esta directiva no se muestra en la ilustración de la parte superior de este artículo. Se describe e ilustra en Recomendaciones de [directivas para proteger el correo electrónico](secure-email-recommended-policies.md).

 Esta directiva aprovecha los controles de concesión [Requerir aplicación cliente aprobada](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) y [Requerir directiva de protección de aplicaciones](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

Por último, el bloqueo de la autenticación heredada para otras aplicaciones cliente en dispositivos iOS y Android garantiza que estos clientes no puedan omitir las directivas de acceso condicional. Si sigue las instrucciones de este artículo, ya ha configurado [Bloquear clientes que no admiten la autenticación moderna](#block-clients-that-dont-support-multi-factor).

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>Definición de directivas de cumplimiento de dispositivos

Las directivas de cumplimiento de dispositivos definen los requisitos que los dispositivos deben cumplir para determinarse como compatibles. Cree directivas de cumplimiento de dispositivos Intune desde el Centro de administración de Microsoft Endpoint Manager.

Debe crear una directiva para cada pc, teléfono o plataforma de tableta:

- Administrador de dispositivos Android
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 8.1 y posterior
- Windows 10 y versiones posteriores

Para crear directivas de cumplimiento de dispositivos, inicie sesión en el [Centro de microsoft Endpoint Manager Administración](https://endpoint.microsoft.com) con sus credenciales de administrador y, a continuación, vaya a **Directivas** **de cumplimiento** \> de **dispositivos**\>. Seleccione **Crear directiva**.

Para que las directivas de cumplimiento de dispositivos se implementen, deben asignarse a grupos de usuarios. Una directiva se asigna después de crearla y guardarla. En el centro de administración, seleccione la directiva y, a continuación, seleccione **Asignaciones**. Después de seleccionar los grupos que desea recibir la directiva, seleccione **Guardar** para guardar esa asignación de grupo e implementar la directiva.

Para obtener instrucciones paso a paso sobre cómo crear directivas de cumplimiento en Intune, consulte [Creación de una directiva de cumplimiento en Microsoft Intune](/mem/intune/protect/create-compliance-policy) en la documentación de Intune.

### <a name="recommended-settings-for-ios"></a>Configuración recomendada para iOS

iOS/iPadOS admite varios escenarios de inscripción, dos de los cuales se tratan como parte de este marco:

- [Inscripción de dispositivos para dispositivos de propiedad personal](/mem/intune/enrollment/ios-enroll) : estos dispositivos son de propiedad personal y se usan para uso profesional y personal.
- [Inscripción de dispositivos automatizada supervisada para dispositivos corporativos](/mem/intune/enrollment/device-enrollment-program-enroll-ios) : estos dispositivos son de propiedad corporativa, están asociados a un único usuario y se usan exclusivamente para uso profesional y no personal.

El marco de configuración de seguridad de iOS/iPadOS se organiza en varios escenarios de configuración distintos, lo que proporciona instrucciones para dispositivos de propiedad personal y supervisados.

Para dispositivos de propiedad personal:

- Seguridad básica (nivel 1): Microsoft recomienda esta configuración como la configuración de seguridad mínima para los dispositivos personales en los que los usuarios acceden a datos profesionales o educativos. Para ello, se aplican directivas de contraseñas y características de bloqueo de dispositivo, y se deshabilitan determinadas funciones de los dispositivos (p. ej., certificados no confiables).
- Seguridad mejorada (nivel 2): Microsoft recomienda esta configuración para los dispositivos en los que los usuarios acceden a información confidencial o confidencial. Esta configuración establece controles de uso compartido de datos. Esta configuración es aplicable a la mayoría de los usuarios móviles que acceden a los datos profesionales o educativos de un dispositivo.
- Alta seguridad (nivel 3): Microsoft recomienda esta configuración para los dispositivos utilizados por usuarios o grupos específicos que son de alto riesgo único (usuarios que controlan datos altamente confidenciales donde la divulgación no autorizada provoca una pérdida considerable de material para la organización). Esta configuración implementa directivas de contraseña más seguras, deshabilita determinadas funciones de dispositivo y aplica restricciones adicionales de transferencia de datos.

Para dispositivos supervisados:

- Seguridad básica (nivel 1): Microsoft recomienda esta configuración como configuración de seguridad mínima para dispositivos supervisados en los que los usuarios acceden a datos profesionales o educativos. Para ello, se aplican directivas de contraseñas y características de bloqueo de dispositivo, y se deshabilitan determinadas funciones de los dispositivos (p. ej., certificados no confiables).
- Seguridad mejorada (nivel 2): Microsoft recomienda esta configuración para los dispositivos en los que los usuarios acceden a información confidencial o confidencial. Esta configuración aplica controles de uso compartido de datos y bloquea el acceso a dispositivos USB. Esta configuración es aplicable a la mayoría de los usuarios móviles que acceden a los datos profesionales o educativos de un dispositivo.
- Alta seguridad (nivel 3): Microsoft recomienda esta configuración para los dispositivos utilizados por usuarios o grupos específicos que son de alto riesgo único (usuarios que controlan datos altamente confidenciales donde la divulgación no autorizada provoca una pérdida considerable de material para la organización). Esta configuración implementa directivas de contraseña más seguras, deshabilita determinadas funciones de dispositivo, aplica restricciones adicionales de transferencia de datos y requiere que las aplicaciones se instalen a través del programa de compra por volumen de Apple.

Con los principios descritos en [Confianza cero configuraciones de acceso a dispositivos e identidades](microsoft-365-policies-configurations.md), los niveles Punto de inicio y Protección empresarial se asignan estrechamente con la configuración de seguridad mejorada de nivel 2. El nivel de protección de seguridad especializada se asigna estrechamente a la configuración de alta seguridad de nivel 3.

|Nivel de protección  |Directiva de dispositivo |Más información  |
|---------|---------|---------|
|Punto de inicio     |Seguridad mejorada (nivel 2)         |La configuración de directiva aplicada en el nivel 2 incluye todas las opciones de configuración de directiva recomendadas para el nivel 1 y solo agrega o actualiza la siguiente configuración de directiva para implementar más controles y una configuración más sofisticada que el nivel 1.         |
|Enterprise     |Seguridad mejorada (nivel 2)         |La configuración de directiva aplicada en el nivel 2 incluye todas las opciones de configuración de directiva recomendadas para el nivel 1 y solo agrega o actualiza la siguiente configuración de directiva para implementar más controles y una configuración más sofisticada que el nivel 1.         |
|Seguridad especializada     |Seguridad alta (nivel 3)         |La configuración de directiva aplicada en el nivel 3 incluye todas las opciones de configuración de directiva recomendadas para los niveles 1 y 2 y solo agrega o actualiza la siguiente configuración de directiva para implementar más controles y una configuración más sofisticada que el nivel 2.         |

Para ver las recomendaciones específicas de cumplimiento de dispositivos y restricciones de dispositivos para cada nivel de configuración, revise el marco de [configuración de seguridad de iOS/iPadOS](/mem/intune/enrollment/ios-ipados-configuration-framework).

### <a name="recommended-settings-for-android"></a>Configuración recomendada para Android

Android Enterprise admite varios escenarios de inscripción, dos de los cuales se tratan como parte de este marco:

- [Perfil de trabajo de Android Enterprise](/intune/android-work-profile-enroll) : este modelo de inscripción se usa normalmente para dispositivos de propiedad personal, donde TI quiere proporcionar un límite de separación claro entre datos profesionales y personales. Las directivas controladas por TI garantizan que los datos de trabajo no se puedan transferir al perfil personal.
- [Dispositivos Android Enterprise totalmente administrados](/intune/android-fully-managed-enroll) : estos dispositivos son de propiedad corporativa, están asociados a un único usuario y se usan exclusivamente para uso profesional y no personal.

El marco de configuración de seguridad de Android Enterprise se organiza en varios escenarios de configuración distintos, lo que proporciona instrucciones para escenarios de perfil de trabajo y totalmente administrados.

Para dispositivos de perfil de trabajo de Android Enterprise:

- Seguridad mejorada del perfil de trabajo (nivel 2): Microsoft recomienda esta configuración como la configuración de seguridad mínima para los dispositivos personales en los que los usuarios acceden a datos profesionales o educativos. Esta configuración presenta los requisitos de contraseña, separa los datos profesionales y personales y valida la atestación de dispositivos Android.
- Alta seguridad del perfil de trabajo (nivel 3): Microsoft recomienda esta configuración para los dispositivos utilizados por usuarios o grupos específicos que son de riesgo único alto (usuarios que controlan datos altamente confidenciales donde la divulgación no autorizada provoca una pérdida considerable de material para la organización). Esta configuración presenta la defensa contra amenazas móviles o Microsoft Defender para punto de conexión, establece la versión mínima de Android, implementa directivas de contraseña más seguras y restringe aún más la separación personal y laboral.

Para dispositivos Android Enterprise totalmente administrados:

- Seguridad básica totalmente administrada (nivel 1): Microsoft recomienda esta configuración como la configuración de seguridad mínima para un dispositivo empresarial. Esta configuración es aplicable a la mayoría de los usuarios móviles que acceden a datos profesionales o educativos. Esta configuración introduce los requisitos de contraseña, establece la versión mínima de Android y establece ciertas restricciones de dispositivo.
- Seguridad mejorada totalmente administrada (nivel 2): Microsoft recomienda esta configuración para los dispositivos en los que los usuarios acceden a información confidencial o confidencial. Esta configuración implementa directivas de contraseña más seguras y deshabilita las funcionalidades de usuario o cuenta.
- Alta seguridad totalmente administrada (nivel 3): Microsoft recomienda esta configuración para los dispositivos utilizados por usuarios o grupos específicos que son de alto riesgo único (usuarios que controlan datos altamente confidenciales donde la divulgación no autorizada provoca una pérdida considerable de material para la organización). Esta configuración aumenta la versión mínima de Android, introduce la defensa contra amenazas móviles o Microsoft Defender para punto de conexión y aplica restricciones de dispositivo adicionales.

Con los principios descritos en [Confianza cero configuraciones de acceso a dispositivos e identidades](microsoft-365-policies-configurations.md), el punto de partida y los niveles de protección de empresa se asignan estrechamente con la seguridad básica de nivel 1 para dispositivos de propiedad personal y la configuración de seguridad mejorada de nivel 2 para dispositivos totalmente administrados. El nivel de protección de seguridad especializada se asigna estrechamente a la configuración de alta seguridad de nivel 3.

Para dispositivos de perfil de trabajo de Android Enterprise:

|Nivel de protección  |Directiva de dispositivo |Más información  |
|---------|---------|---------|
|Punto de inicio     |Perfil de trabajo: seguridad básica (nivel 1)      |N/D         |
|Enterprise     |Perfil de trabajo: seguridad básica (nivel 1)         |N/D         |
|Punto de inicio     |Totalmente administrado: seguridad mejorada (nivel 2)       |La configuración de directiva aplicada en el nivel 2 incluye todas las opciones de configuración de directiva recomendadas para el nivel 1 y solo agrega o actualiza la siguiente configuración de directiva para implementar más controles y una configuración más sofisticada que el nivel 1.         |
|Enterprise     |Totalmente administrado: seguridad mejorada (nivel 2)         |La configuración de directiva aplicada en el nivel 2 incluye todas las opciones de configuración de directiva recomendadas para el nivel 1 y solo agrega o actualiza la siguiente configuración de directiva para implementar más controles y una configuración más sofisticada que el nivel 1.         |
|Seguridad especializada     |Seguridad alta (nivel 3)         |La configuración de directiva aplicada en el nivel 3 incluye todas las opciones de configuración de directiva recomendadas para los niveles 1 y 2 y solo agrega o actualiza la siguiente configuración de directiva para implementar más controles y una configuración más sofisticada que el nivel 2.         |

Para ver las recomendaciones específicas de cumplimiento de dispositivos y restricciones de dispositivos para cada nivel de configuración, revise [Android Enterprise Security Configuration Framework](/mem/intune/enrollment/android-configuration-framework).

### <a name="recommended-settings-for-windows-10-and-later"></a>Configuración recomendada para Windows 10 y versiones posteriores

Se recomienda la siguiente configuración para los equipos que ejecutan Windows 10 y versiones posteriores, tal como se configura en **Paso 2: Configuración de cumplimiento**, del proceso de creación de directivas.

Para **las reglas de evaluación del servicio de atestación de estado de Windows >** dispositivo, consulte esta tabla.

|Propiedades|Valor|Acción|
|---|---|---|
|Require BitLocker|Obligatoria|Seleccionar|
|Requerir que arranque seguro esté habilitado en el dispositivo|Obligatoria|Seleccionar|
|Requerir integridad de código|Obligatoria|Seleccionar|

En **Propiedades del dispositivo**, especifique los valores adecuados para las versiones del sistema operativo en función de las directivas de TI y seguridad.

En **Cumplimiento de Configuration Manager**, seleccione **Requerir**.

Para **Seguridad del sistema**, consulte esta tabla.

|Tipo|Propiedades|Valor|Acción|
|---|---|---|---|
|Password|Requerir una contraseña para desbloquear dispositivos móviles|Obligatoria|Seleccionar|
||Contraseñas sencillas|Bloquear|Seleccionar|
||Tipo de contraseña|Valor predeterminado del dispositivo|Seleccionar|
||Longitud mínima de la contraseña|6|Tipo|
||Máximo de minutos de inactividad antes de solicitar la contraseña|15 |Tipo <p> Esta configuración es compatible con las versiones 4.0 y posteriores de Android o KNOX 4.0 y versiones posteriores. Para dispositivos iOS, es compatible con iOS 8.0 y versiones posteriores.|
||Expiración de contraseña (días)|41|Tipo|
||Número de contraseñas anteriores que no se pueden reutilizar|5|Tipo|
||Requerir contraseña cuando el dispositivo vuelva del estado de inactividad (móvil y holográfico)|Obligatoria|Disponible para Windows 10 y versiones posteriores|
|Cifrado|Cifrado de almacenamiento de datos en el dispositivo|Obligatoria|Seleccionar|
|Seguridad del dispositivo|Firewall|Obligatoria|Seleccionar|
||Antivirus|Obligatoria|Seleccionar|
||Antiespía|Obligatoria|Seleccionar <p> Esta configuración requiere una solución anti spyware registrada con la aplicación Seguridad de Windows.|
|Defender for Cloud|Antimalware de Microsoft Defender|Obligatoria|Seleccionar|
||Versión mínima de Antimalware de Microsoft Defender||Tipo <p> Solo se admite para Windows 10 escritorio. Microsoft recomienda versiones no más de cinco detrás de la versión más reciente.|
||Firma antimalware de Microsoft Defender actualizada|Obligatoria|Seleccionar|
||Protección en tiempo real|Obligatoria|Seleccionar <p> Solo se admite para el escritorio de Windows 10 y versiones posteriores|

#### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender para punto de conexión

|Tipo|Propiedades|Valor|Acción|
|---|---|---|---|
|Microsoft Defender para punto de conexión reglas en el Centro de administración de Microsoft Endpoint Manager|[Requerir que el dispositivo esté en o bajo la puntuación de riesgo de la máquina](/mem/intune/protect/advanced-threat-protection-configure#create-and-assign-compliance-policy-to-set-device-risk-level)|Mediano|Seleccionar|

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

## <a name="require-compliant-pcs-and-mobile-devices"></a>Requerir equipos compatibles y dispositivos móviles

Para requerir el cumplimiento de todos los dispositivos:

1. Vaya al [Azure Portal](https://portal.azure.com) e inicie sesión con sus credenciales.
2. En la lista de servicios de Azure, elija **Azure Active Directory**.
3. En la lista **Administrar** , elija **Seguridad** y, después, **Acceso condicional**.
4. Elija **Nueva directiva** y escriba el nombre de la nueva directiva.

5. En **Asignaciones**, elija **Usuarios y grupos** e incluya a quién quiere que se aplique la directiva. También excluya el grupo de exclusión de acceso condicional.

6. En **Asignaciones**, elija **Aplicaciones o acciones en la nube**.

7. En **Incluir**, elija **Seleccionar aplicaciones > Seleccionar** y, a continuación, seleccione las aplicaciones deseadas en la lista **Aplicaciones** en la nube. Por ejemplo, seleccione Office 365. Elija **Seleccionar** cuando haya terminado.

8. En **Controles de acceso**, elija **Conceder** .

9. Elija **Conceder acceso** y, a continuación, active **Requerir que el dispositivo se marque como compatible**. Para varios controles, seleccione **Requerir todos los controles seleccionados**. Cuando haya terminado, elija **Seleccionar**.

10. Seleccione **Activado** para **Habilitar directiva** y, a continuación, elija **Crear**.

> [!NOTE]
> Asegúrese de que el dispositivo es compatible antes de habilitar esta directiva. De lo contrario, podría bloquearse y no podrá cambiar esta directiva hasta que la cuenta de usuario se haya agregado al grupo de exclusión de acceso condicional.

## <a name="next-step"></a>Paso siguiente

[![Paso 3: Directivas para usuarios invitados y externos.](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png#lightbox)](identity-access-policies-guest-access.md)

[Más información sobre las recomendaciones de directiva para usuarios invitados y externos](identity-access-policies-guest-access.md)
