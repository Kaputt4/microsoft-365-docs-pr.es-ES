---
title: 'Directivas comunes de identidad y acceso a dispositivos: Microsoft 365 para Enterprise | Microsoft docs'
description: Describe las directivas y configuraciones de acceso a dispositivos y de identidad comunes recomendadas.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
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
ms.openlocfilehash: b4468bfc7ef4b6f76d44b328f4e5b6d61d7f06ac
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357844"
---
# <a name="common-identity-and-device-access-policies"></a>Directivas comunes de acceso a dispositivos e identidades

En este artículo se describen las directivas comunes recomendadas para proteger el acceso a los servicios en la nube de Microsoft 365, incluidas las aplicaciones locales publicadas con el proxy de aplicación de Azure Active Directory (Azure AD).

En esta guía se explica cómo implementar las directivas recomendadas en un entorno recién aprovisionado. La configuración de estas directivas en un entorno de laboratorio independiente permite comprender y evaluar las directivas recomendadas antes de ensayar la implementación en los entornos de preproducción y producción. El entorno recién aprovisionado puede ser solo de nube o híbrido para reflejar las necesidades de evaluación.

## <a name="policy-set"></a>Conjunto de directivas

El siguiente diagrama ilustra el conjunto de directivas recomendado. Muestra el nivel de protección al que se aplica cada directiva y si las directivas se aplican a equipos, teléfonos y tabletas o a ambas categorías de dispositivos. También indica dónde se configuran estas directivas.

[![Directivas comunes para configurar el acceso a los dispositivos e identidades](../../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

[Ver una versión más grande de esta imagen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

Este es un resumen de PDF de una página con vínculos a las directivas individuales:

[![Imagen en miniatura para la protección de identidades y dispositivos para el documento de Microsoft 365](../../media/microsoft-365-policies-configurations/MSFT-cloud-architecture-identity-device-protection-handout.png)](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) <br/>  [Ver como PDF](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) \| [Descargar como PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf)

En el resto de este artículo se describe cómo configurar estas directivas.

> [!NOTE]
> Se recomienda requerir el uso de la autenticación multifactor (MFA) antes de inscribir dispositivos en Intune para asegurarse de que el dispositivo está en la posesión del usuario deseado. Debe inscribir los dispositivos en Intune para poder aplicar directivas de cumplimiento de dispositivos.

Para darle tiempo para llevar a cabo estas tareas, se recomienda implementar las directivas de línea de base en el orden que se indica en esta tabla. Sin embargo, las directivas de MFA para niveles de protección confidenciales y altamente regulados se pueden implementar en cualquier momento.

|Nivel de protección|Directivas|Más información|
|---|---|---|
|**Baseline**|[Requerir MFA cuando el riesgo de inicio de sesión sea *medio* o *alto*](#require-mfa-based-on-sign-in-risk)||
||[Bloquear a los clientes que no sean compatibles con la autenticación moderna](#block-clients-that-dont-support-modern-authentication)|Los clientes que no usan la autenticación moderna pueden omitir las directivas de acceso condicional, por lo que es importante bloquearlos.|
||[Los usuarios de riesgo alto tienen que cambiar la contraseña](#high-risk-users-must-change-password)|Obliga a los usuarios a cambiar su contraseña al iniciar sesión si se detecta actividad de alto riesgo para su cuenta.|
||[Aplicar directivas de protección de datos de aplicaciones](#apply-app-data-protection-policies)|Una directiva de protección de aplicaciones de Intune por plataforma (Windows, iOS/iPad, Android).|
||[Requerir aplicaciones aprobadas y protección de aplicaciones](#require-approved-apps-and-app-protection)|Habilita la protección de aplicaciones móviles para teléfonos y tabletas con iOS, iPados o Android.|
||[Definir directivas de cumplimiento de dispositivos](#define-device-compliance-policies)|Una directiva para cada plataforma.|
||[Exigir equipos PC compatibles](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Aplica la administración de Intune de los equipos con Windows o MacOS.|
|**Confidencial**|[Requerir MFA cuando el riesgo de inicio de sesión sea *bajo*, *medio* o *alto*](#require-mfa-based-on-sign-in-risk)||
||[Requerir equipos *y* dispositivos móviles compatibles](#require-compliant-pcs-and-mobile-devices)|Aplica la administración de Intune para equipos PC (Windows o Mac OS) y teléfonos o tabletas (iOS, iPados o Android).|
|**Extremadamente regulado**|[Requerir *siempre* MFA](#require-mfa-based-on-sign-in-risk)|
|

## <a name="assigning-policies-to-groups-and-users"></a>Asignar directivas a grupos y usuarios

Antes de configurar directivas, identifique los grupos de Azure AD que está usando para cada nivel de protección. Normalmente, la protección de línea de base se aplica a todos los de la organización. Un usuario que se incluya para la protección de línea base y sensible tendrá todas las directivas de línea de base aplicadas, además de las directivas confidenciales. La protección es acumulativa y se aplica la directiva más restrictiva.

Una práctica recomendada es crear un grupo de Azure AD para la exclusión de acceso condicional. Agregue este grupo a todas las directivas de acceso condicional en el valor **excluir** de la opción **usuarios y grupos** de la sección **asignaciones** . Esto le proporciona un método para proporcionar acceso a un usuario mientras se solucionan problemas de acceso. Solo se recomienda como solución temporal. Supervise si hay cambios en este grupo y asegúrese de que el grupo de exclusión solo se usa como se esperaba.

A continuación, se muestra un ejemplo de asignación de grupo y exclusiones para requerir MFA.

![Ejemplo de asignación y exclusiones de grupo para directivas de MFA](../../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

Estos son los resultados:

- Todos los usuarios deben usar la MFA cuando el riesgo de inicio de sesión sea medio o alto.

- Los miembros del grupo de personal ejecutivo deben usar la MFA cuando el riesgo de inicio de sesión sea bajo, medio o alto.

  En este caso, los miembros del grupo de personal ejecutivo coinciden con las directivas de acceso condicional de línea base y confidencial. Se combinan los controles de acceso de ambas directivas, que en este caso es equivalente a la Directiva de acceso condicional confidencial.

- Los miembros del grupo X de proyecto superior secreto siempre son necesarios para usar MFA

  En este caso, los miembros del grupo de proyecto X superior secreto coinciden con las directivas de acceso condicional de línea base y altamente reguladas. Se combinan los controles de acceso de ambas directivas. Como el control de acceso de la Directiva de acceso condicional altamente regulado es más restrictivo, se utiliza.

Tenga cuidado al aplicar más niveles de protección a grupos y usuarios. Por ejemplo, los miembros del grupo de proyecto X superior secreto deberán usar MFA cada vez que inicien sesión, aunque no estén trabajando en el contenido altamente regulado para el proyecto X.

Todos los grupos de Azure AD creados como parte de estas recomendaciones deben crearse como grupos de Microsoft 365. Esto es importante para la implementación de las etiquetas de confidencialidad al proteger documentos en Microsoft Teams y SharePoint.

![Captura de pantalla para crear grupos de 365 de Microsoft](../../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)

## <a name="require-mfa-based-on-sign-in-risk"></a>Requerir MFA según el riesgo de inicio de sesión

Debe pedir a los usuarios que se registren para MFA antes de que se requiera su uso. Si tiene Microsoft 365 E5, Microsoft 365 E3 con el complemento Identity & Threat Protection, Office 365 con EMS E5 o licencias individuales de Azure AD Premium P2, puede usar la Directiva de registro de MFA con Azure AD Identity Protection para requerir que los usuarios se registren para MFA. El [trabajo de requisitos previos](identity-access-prerequisites.md) incluye el registro de todos los usuarios con MFA.

Una vez registrados los usuarios, puede solicitar MFA para iniciar sesión con una nueva Directiva de acceso condicional.

1. Vaya al [Azure Portal](https://portal.azure.com) e inicie sesión con sus credenciales.
2. En la lista de servicios de Azure, elija **Azure Active Directory**.
3. En la lista **administrar** , elija **seguridad** y, después, elija **acceso condicional**.
4. Elija **nueva Directiva** y escriba el nombre de la nueva Directiva.

En las tablas siguientes se describen las opciones de configuración de directivas de acceso condicional para requerir MFA en función del riesgo de inicio de sesión.

En la sección **asignaciones** :

|Setting|Propiedades|Valores|Notas|
|---|---|---|---|
|Usuarios y grupos|Incluir|**Seleccione usuarios y grupos > usuarios y grupos**: seleccione grupos específicos que contengan cuentas de usuario de destino.|Comience con el grupo que incluye las cuentas de usuario piloto.|
||Excluir|**Usuarios y grupos**: seleccione el grupo de excepciones de acceso condicional; cuentas de servicio (identidades de aplicaciones).|La pertenencia debe modificarse en función de las necesidades temporales.|
|Aplicaciones o acciones en la nube|**Las aplicaciones en la nube > incluyen**|**Seleccione aplicaciones**: seleccione las aplicaciones a las que quiere aplicar esta Directiva. Por ejemplo, seleccione Exchange Online.||
|Condiciones|||Configure las condiciones específicas de su entorno y necesidades.|
||Riesgo de inicio de sesión||Vea las instrucciones de la tabla siguiente.|
|

### <a name="sign-in-risk-condition-settings"></a>Configuración de las condiciones de riesgo de inicio de sesión

Aplique la configuración del nivel de riesgo en función del nivel de protección de destino.

|Nivel de protección|Valores de nivel de riesgo necesarios|Action|
|---|---|---|
|Línea base|Alto, medio|Compruebe ambos.|
|Confidencial|Alta, media, baja|Compruebe los tres.|
|Extremadamente regulado||Deje todas las opciones desactivadas para exigir siempre la MFA.|
|

En la sección **controles de acceso** :

|Setting|Propiedades|Valores|Action|
|---|---|---|---|
|Conceder|**Conceder acceso**||Select|
|||**Requerir multi-factor Authentication**|Check|
||**Exigir todos los controles seleccionados**||Select|
|

Elija **seleccionar** para guardar la configuración de **concesión** .

Por último, seleccione **activado** para **Habilitar Directiva** y, a continuación, elija **crear**.

También considere la posibilidad de usar la herramienta [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para probar la Directiva.

## <a name="block-clients-that-dont-support-modern-authentication"></a>Bloquear a los clientes que no sean compatibles con la autenticación moderna

Use la configuración de estas tablas para una directiva de acceso condicional para bloquear clientes que no admitan la autenticación moderna.

Consulte [este artículo](../../enterprise/microsoft-365-client-support-modern-authentication.md) para obtener una lista de clientes en Microsoft 365 que realizan la autenticación moderna de admitidas.

En la sección **asignaciones** :

|Setting|Propiedades|Valores|Notas|
|---|---|---|---|
|Usuarios y grupos|Incluir|**Seleccione usuarios y grupos > usuarios y grupos**: seleccione grupos específicos que contengan cuentas de usuario de destino.|Comience con el grupo que incluye las cuentas de usuario piloto.|
||Excluir|**Usuarios y grupos**: seleccione el grupo de excepciones de acceso condicional; cuentas de servicio (identidades de aplicaciones).|La pertenencia debe modificarse en función de las necesidades temporales.|
|Aplicaciones o acciones en la nube|**Las aplicaciones en la nube > incluyen**|**Seleccione aplicaciones**: seleccione las aplicaciones correspondientes a los clientes que no admiten la autenticación moderna.||
|Condiciones|**Aplicaciones cliente**|Elija **sí** para **configurar** <br/> Desactivar las marcas de verificación para **exploradores** y **aplicaciones móviles y clientes de escritorio**||
|

En la sección **controles de acceso** :

|Setting|Propiedades|Valores|Action|
|---|---|---|---|
|Conceder|**Bloquear acceso**||Select|
||**Exigir todos los controles seleccionados**||Select|
|

Elija **seleccionar** para guardar la configuración de **concesión** .

Por último, seleccione **activado** para **Habilitar Directiva** y, a continuación, elija **crear**.

Considere la posibilidad de usar la herramienta [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para probar la Directiva.

Para Exchange Online, puede usar directivas de autenticación para [deshabilitar la autenticación básica](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online), lo que obliga a todas las solicitudes de acceso de cliente a usar la autenticación moderna.

## <a name="high-risk-users-must-change-password"></a>Los usuarios de riesgo alto tienen que cambiar la contraseña

Para asegurarse de que todas las cuentas de usuarios de alto riesgo se vean obligadas a realizar un cambio de contraseña al iniciar sesión, debe aplicar la siguiente directiva.

Inicie sesión en [Microsoft Azure Portal (https://portal.azure.com)](https://portal.azure.com/) con las credenciales de administrador y luego vaya a **Azure AD Identity Protection > Directiva de riesgo de usuario**.

En la sección **asignaciones** :

|Tipo|Propiedades|Valores|Action|
|---|---|---|---|
|Usuarios|Incluir|**Todos los usuarios**|Select|
|Riesgo de usuario|**Alto**||Select|
|

En la segunda sección **asignaciones** :

|Tipo|Propiedades|Valores|Action|
|---|---|---|---|
|Access|**Permitir acceso**||Select|
|||**Exigir cambio de contraseña**|Check|
|

Elija **listo** para guardar la configuración de **acceso** .

Por último, seleccione **activado** para **exigir Directiva** y, a continuación, elija **Guardar**.

Considere la posibilidad de usar la herramienta [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para probar la Directiva.

Use esta directiva junto con [configurar la protección con contraseña de Azure ad](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad), que detecta y bloquea contraseñas débiles conocidas y sus variantes, así como términos débiles adicionales específicos de la organización. El uso de la protección con contraseña de Azure AD garantiza que las contraseñas modificadas sean fuertes.

## <a name="apply-app-data-protection-policies"></a>Aplicar directivas de protección de datos de aplicaciones

Las directivas de protección de aplicaciones (aplicación) definen qué aplicaciones están permitidas y las acciones que pueden llevar a cabo con los datos de la organización. Las opciones disponibles en la aplicación permiten a las organizaciones adaptar la protección a sus necesidades específicas. Para algunos, puede que no sea obvio qué configuración de directiva es necesaria para implementar un escenario completo. Para ayudar a las organizaciones a priorizar la protección de extremos de extremos de cliente móvil, Microsoft ha lanzado una taxonomía para el marco de protección de datos de aplicaciones para iOS y la administración de aplicaciones móviles de Android.

El marco de protección de datos de la aplicación está organizado en tres niveles de configuración distintos, donde cada nivel se basa en el nivel anterior:

- **Enterprise Basic Data Protection** (nivel 1) garantiza que las aplicaciones están protegidas con PIN y se cifran y realizan operaciones selectivas de borrado. Para dispositivos Android, este nivel valida la atestación del dispositivo de Android. Se trata de una configuración de nivel de entrada que proporciona un control de protección de datos similar en las directivas de buzones de correo de Exchange Online y lo presenta y el llenado del usuario a la aplicación.
- La **protección de datos mejorada** de la empresa (nivel 2) introduce los mecanismos de prevención de fugas de datos de aplicaciones y los requisitos mínimos del sistema operativo. Esta es la configuración que se aplica a la mayoría de los usuarios móviles que tienen acceso a datos de trabajo o escuela.
- La **alta protección de datos empresariales** (nivel 3) introduce mecanismos avanzados de protección de datos, configuración mejorada de PIN y defensa para la amenaza de aplicaciones móviles. Esta configuración es preferible para los usuarios que tienen acceso a datos de alto riesgo.

Para ver las recomendaciones específicas para cada nivel de configuración y las aplicaciones mínimas que deben protegerse, revise el [marco de protección de datos con directivas de protección de aplicaciones](https://docs.microsoft.com/mem/intune/apps/app-protection-framework).

Mediante el uso de los principios descritos en [configuraciones de identidad y acceso a dispositivos](microsoft-365-policies-configurations.md), los niveles de protección base y confidencial se asignan estrechamente con la configuración de protección de datos mejorada de nivel 2. El nivel de protección altamente regulado se asigna estrechamente a la configuración de la protección de datos de nivel 3 Enterprise High.

|Nivel de protección|Directiva de protección de aplicaciones|Más información|
|---|---|---|
|Línea base|[Protección de datos mejorada de nivel 2](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|La configuración de la Directiva que se aplica en el nivel 2 incluye todas las configuraciones de directiva recomendadas para el nivel 1 y solo agrega o actualiza la configuración de directivas siguiente para implementar más controles y una configuración más sofisticada que el nivel 1.|
|Confidencial|[Protección de datos mejorada de nivel 2](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|La configuración de la Directiva que se aplica en el nivel 2 incluye todas las configuraciones de directiva recomendadas para el nivel 1 y solo agrega o actualiza la configuración de directivas siguiente para implementar más controles y una configuración más sofisticada que el nivel 1.|
|Altamente regulado|[Nivel 3 de protección empresarial alta para la información](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)|La configuración de la Directiva que se aplica en el nivel 3 incluye todas las configuraciones de directiva recomendadas para los niveles 1 y 2 y solo agrega o actualiza la configuración de directivas siguiente para implementar más controles y una configuración más sofisticada que el nivel 2.|
|

Para crear una nueva Directiva de protección de aplicaciones para cada plataforma (iOS y Android) en Microsoft Endpoint Manager con la configuración del marco de protección de datos, puede:

1. Cree manualmente las directivas siguiendo los pasos de [Cómo crear e implementar directivas de protección de aplicaciones con Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/app-protection-policies).
2. Importe las [plantillas JSON del marco de configuración de la Directiva de protección de aplicaciones de Intune](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) de ejemplo con los [scripts de PowerShell de Intune](https://github.com/microsoftgraph/powershell-intune-samples).

## <a name="require-approved-apps-and-app-protection"></a>Requerir aplicaciones aprobadas y protección de aplicaciones

Para aplicar las directivas de protección de aplicaciones que ha aplicado en Intune, debe crear una directiva de acceso condicional que requiera aplicaciones cliente aprobadas y las condiciones establecidas en las directivas de protección de aplicaciones.

La aplicación de directivas de protección de aplicaciones requiere un conjunto de directivas que se describen en en [requerir la Directiva de protección de aplicaciones para Cloud Access Access con acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access). Estas directivas se incluyen en este conjunto recomendado de directivas de configuración de identidad y acceso.

Para crear la Directiva de acceso condicional que requiere aplicaciones aprobadas y protección de aplicaciones, siga "paso 1: configurar una directiva de acceso condicional de Azure AD para Microsoft 365" en el [escenario 1: las aplicaciones de Microsoft 365 requieren aplicaciones aprobadas con directivas de protección de aplicaciones](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), lo que permite a Outlook para iOS y Android, pero bloquea la conexión de los clientes de Exchange ActiveSync a Exchange Online

   > [!NOTE]
   > Esta Directiva garantiza que los usuarios móviles puedan acceder a todos los puntos de conexión de Office con las aplicaciones correspondientes.

Si va a habilitar el acceso móvil a Exchange Online, implemente [los clientes de Block ActiveSync](secure-email-recommended-policies.md#block-activesync-clients), que impide que los clientes de Exchange ActiveSync que aprovechan la autenticación básica se conecten a Exchange Online. Esta Directiva no se ilustra en la ilustración de la parte superior de este artículo. Se describe y se describen en [recomendaciones de directivas para proteger el correo electrónico](secure-email-recommended-policies.md).

 Estas directivas aprovechan los controles Grant [requieren la aplicación cliente aprobada](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) y [requieren la Directiva de protección de aplicaciones](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

Por último, el bloqueo de la autenticación heredada para otras aplicaciones cliente en dispositivos iOS y Android garantiza que estos clientes no puedan eludir las directivas de acceso condicional. Si sigue las instrucciones de este artículo, ya ha configurado [bloquear clientes que no admiten la autenticación moderna](#block-clients-that-dont-support-modern-authentication).

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>Definir directivas de cumplimiento de dispositivos

Las directivas de cumplimiento de dispositivos definen los requisitos que deben cumplir los dispositivos para que se determinen como compatibles. Puede crear directivas de cumplimiento de dispositivos de Intune desde el centro de administración de Microsoft Endpoint Manager.

Debe crear una directiva para cada plataforma de PC, teléfono o tableta:

- Administrador de dispositivos Android
- Android Enterprise
- iOS/iPados
- macOS
- Windows 8,1 y versiones posteriores
- Windows 10 y versiones posteriores

Para crear directivas de cumplimiento de dispositivos, inicie sesión en el [centro de administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com) con sus credenciales de administrador y, a continuación, navegue a directivas de directivas de cumplimiento de **dispositivos**  >  **Compliance policies**  >  **Policies**. Seleccione **crear Directiva**.

Para que se implementen las directivas de cumplimiento de dispositivos, se deben asignar a grupos de usuarios. Una directiva se asigna después de crearla y guardarla. En el centro de administración, seleccione la Directiva y, a continuación, seleccione **asignaciones**. Después de seleccionar los grupos que desea que reciban la Directiva, seleccione **Guardar** para guardar esa asignación de grupo e implementar la Directiva.

Para obtener instrucciones paso a paso sobre cómo crear directivas de cumplimiento en Intune, consulte [Create a Compliance Policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy) en la documentación de Intune.

### <a name="recommended-settings-for-windows-10-and-later"></a>Configuración recomendada para Windows 10 y versiones posteriores

Se recomiendan los siguientes valores para equipos que ejecutan Windows 10 y versiones posteriores, tal como se ha configurado en el **paso 2: configuración de cumplimiento**, del proceso de creación de la Directiva.

Para el **Estado del dispositivo > reglas de evaluación del servicio de atestación de estado de Windows**, vea esta tabla.

|Propiedades|Valor|Action|
|---|---|---|
|Requerir BitLocker|Obligatoria|Select|
|Requerir el arranque seguro para habilitarse en el dispositivo|Obligatoria|Select|
|Requerir integridad de código|Obligatoria|Select|
|

Para **las propiedades de dispositivo**, especifique los valores adecuados para las versiones de sistema operativo en función de las directivas de seguridad y de ti.

Para el **cumplimiento del administrador de configuración**, seleccione **requerir**.

Para la **seguridad del sistema**, vea esta tabla.

|Tipo|Propiedades|Valor|Action|
|---|---|---|---|
|Password|Requerir una contraseña para desbloquear dispositivos móviles|Obligatoria|Select|
||Contraseñas sencillas|Bloquear|Select|
||Tipo de contraseña|Valor predeterminado del dispositivo|Select|
||Longitud mínima de la contraseña|6 |Tipo|
||Minutos máximos de inactividad antes de que se requiera la contraseña|15 |Tipo <br/> Esta configuración es compatible con las versiones 4,0 y anteriores de Android o KNOX 4,0 y superior. Para dispositivos iOS, es compatible con iOS 8,0 y versiones posteriores.|
||Expiración de contraseña (días)|41|Tipo|
||Número de contraseñas anteriores para impedir la reutilización|5 |Tipo|
||Requerir contraseña cuando el dispositivo vuelve del estado de inactividad (móvil y holográfica)|Obligatoria|Disponible para Windows 10 y versiones posteriores|
|Cifrado|Cifrado del almacenamiento de datos en el dispositivo|Obligatoria|Select|
|Seguridad del dispositivo|Éste|Obligatoria|Select|
||Antivirus|Obligatoria|Select|
||Actualizados|Obligatoria|Select <br/> Esta configuración requiere una solución anti-spyware registrada en el centro de seguridad de Windows.|
|Defender|Antimalware de Microsoft defender|Obligatoria|Select|
||Versión mínima de antimalware de Microsoft defender||Tipo <br/> Solo se admite en el escritorio de Windows 10. Microsoft recomienda no tener más de cinco versiones de la versión más reciente.|
||La firma antimalware de Microsoft defender actualizada|Obligatoria|Select|
||Protección en tiempo real|Obligatoria|Select <br/> Solo se admite en el escritorio de Windows 10|
|

#### <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender para punto de conexión

|Tipo|Propiedades|Valor|Action|
|---|---|---|---|
|Microsoft defender para reglas de extremo|Requerir que el dispositivo esté por encima o por debajo de la puntuación de riesgo de la máquina|Mediano|Select|
|

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Requerir equipos compatibles (pero no teléfonos y tabletas compatibles)

Antes de agregar una directiva para requerir equipos compatibles, asegúrese de inscribir los dispositivos para la administración en Intune. Se recomienda usar la autenticación multifactor antes de inscribir los dispositivos en Intune para asegurarse de que el dispositivo está en la posesión del usuario deseado.

Para requerir equipos compatibles:

1. Vaya al [Azure Portal](https://portal.azure.com) e inicie sesión con sus credenciales.
2. En la lista de servicios de Azure, elija **Azure Active Directory**.
3. En la lista **administrar** , elija **seguridad** y, después, elija **acceso condicional**.
4. Elija **nueva Directiva** y escriba el nombre de la nueva Directiva.

5. En **tareas**, elija **usuarios y grupos** e incluya a quién desea que se aplique la Directiva. También excluya el grupo de exclusión de acceso condicional.

6. En **tareas**, elija **aplicaciones o acciones en la nube**.

7. Para **incluir**, elija **seleccionar aplicaciones > seleccionar** y, a continuación, seleccione las aplicaciones que desee en la lista de **aplicaciones de nube** . Por ejemplo, seleccione Exchange Online. Elija **seleccionar** cuando haya terminado.

8. Para requerir equipos compatibles (pero no teléfonos y tabletas compatibles), en **asignaciones**, elija **condiciones > plataformas de dispositivos**. Seleccione **sí** para **configurar**. Elija  **seleccionar plataformas de dispositivos**, seleccione **Windows** y **MacOS** y, a continuación, elija **listo**.

9. En **controles de acceso**, elija **conceder** .

10. Elija **conceder acceso** y, a continuación, compruebe que el **dispositivo esté marcado como compatible**. Para varios controles, seleccione **requerir todos los controles seleccionados**. Cuando termine, elija **seleccionar**.

11. Seleccione **activado** para **Habilitar Directiva** y, a continuación, elija **crear**.

> [!NOTE]
> Asegúrese de que el dispositivo es compatible antes de habilitar esta Directiva. De lo contrario, podría obtener el bloqueo y no podrá cambiar esta Directiva hasta que su cuenta de usuario se haya agregado al grupo de exclusión de acceso condicional.

## <a name="require-compliant-pcs-and-mobile-devices"></a>Requerir equipos *y* dispositivos móviles compatibles

Para requerir el cumplimiento de todos los dispositivos:

1. Vaya al [Azure Portal](https://portal.azure.com) e inicie sesión con sus credenciales.
2. En la lista de servicios de Azure, elija **Azure Active Directory**.
3. En la lista **administrar** , elija **seguridad** y, después, elija **acceso condicional**.
4. Elija **nueva Directiva** y escriba el nombre de la nueva Directiva.

5. En **tareas**, elija **usuarios y grupos** e incluya a quién desea que se aplique la Directiva. También excluya el grupo de exclusión de acceso condicional.

6. En **tareas**, elija **aplicaciones o acciones en la nube**.

7. Para **incluir**, elija **seleccionar aplicaciones > seleccionar** y, a continuación, seleccione las aplicaciones que desee en la lista de **aplicaciones de nube** . Por ejemplo, seleccione Exchange Online. Elija **seleccionar** cuando haya terminado.

8. En **controles de acceso**, elija **conceder** .

9. Elija **conceder acceso** y, a continuación, compruebe que el **dispositivo esté marcado como compatible**. Para varios controles, seleccione **requerir todos los controles seleccionados**. Cuando termine, elija **seleccionar**.

10. Seleccione **activado** para **Habilitar Directiva** y, a continuación, elija **crear**.

> [!NOTE]
> Asegúrese de que el dispositivo es compatible antes de habilitar esta Directiva. De lo contrario, podría obtener el bloqueo y no podrá cambiar esta Directiva hasta que su cuenta de usuario se haya agregado al grupo de exclusión de acceso condicional.

## <a name="next-step"></a>Paso siguiente

[![Paso 3: directivas para usuarios externos y invitados](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png)](identity-access-policies-guest-access.md)

[Obtener información sobre recomendaciones de directivas para usuarios externos y invitados](identity-access-policies-guest-access.md)
