---
title: Directivas comunes de identidad y acceso a dispositivos-Microsoft 365 Enterprise | Microsoft docs
description: Explica las directivas recomendadas por Microsoft para aplicar directivas y configuraciones de identidad y acceso a dispositivos.
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: b6e10757c3a4370c83b6ee0c1fb6c818a13089ea
ms.sourcegitcommit: 7eaecb91c7cb1f8679f99882563f5c1149175992
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "43022926"
---
# <a name="common-identity-and-device-access-policies"></a>Directivas comunes de acceso a dispositivos e identidades
En este artículo se describen las directivas comunes recomendadas para proteger el acceso a los servicios en la nube, incluidas las aplicaciones locales publicadas con el proxy de aplicación de Azure AD. 

En esta guía se explica cómo implementar las directivas recomendadas en un entorno recién aprovisionado. La configuración de estas directivas en un entorno de laboratorio independiente permite comprender y evaluar las directivas recomendadas antes de ensayar la implementación en los entornos de preproducción y producción. El entorno recién aprovisionado puede ser solo de nube o híbrido.  

## <a name="policy-set"></a>Conjunto de directivas 

El siguiente diagrama ilustra el conjunto de directivas recomendado. Muestra el nivel de protección al que se aplica cada directiva y si las directivas se aplican a equipos, teléfonos y tabletas o a ambas categorías de dispositivos. También indica dónde están configuradas estas directivas.

![Directivas comunes para configurar el acceso a los dispositivos e identidades](../media/Identity_device_access_policies_byplan.png)


En el resto de este artículo se describe cómo configurar estas directivas. 

Se recomienda usar la autenticación multifactor antes de inscribir los dispositivos en Intune para asegurarse de que el dispositivo está en la posesión del usuario deseado. También debe inscribir los dispositivos en Intune antes de aplicar las directivas de cumplimiento de dispositivos.

Para darle tiempo para llevar a cabo estas tareas, se recomienda implementar las directivas de línea de base en el orden que se indica en esta tabla. Sin embargo, las directivas de MFA para la protección sensible y altamente regulada pueden implementarse en cualquier momento.


|Nivel de protección|Directivas|Más información|
|:---------------|:-------|:----------------|
|**Baseline**|[Requerir MFA cuando el riesgo de inicio de sesión sea *medio* o *alto*](#require-mfa-based-on-sign-in-risk)| |
|        |[Bloquear a los clientes que no sean compatibles con la autenticación moderna](#block-clients-that-dont-support-modern-authentication)|Los clientes que no usan la autenticación moderna pueden omitir las reglas de acceso condicional, por lo que es importante bloquear estos|
|        |[Los usuarios de riesgo alto deben cambiar la contraseña](#high-risk-users-must-change-password)|Obliga a los usuarios a cambiar su contraseña al iniciar sesión si se detecta actividad de alto riesgo para su cuenta|
|        |[Definir directivas de protección de aplicaciones](#define-app-protection-policies)|Una directiva por plataforma (iOS, Android, Windows).|
|        |[Requerir aplicaciones compatibles con las directivas de protección de aplicaciones de Intune](#require-apps-that-support-intune-app-protection-policies)|Fuerza la protección de aplicaciones móviles para teléfonos y tabletas|
|        |[Definir directivas de cumplimiento de dispositivos](#define-device-compliance-policies)|Una directiva para cada plataforma|
|        |[Exigir equipos PC compatibles](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Fuerza la administración de los equipos de Intune|
|**Confidencial**|[Requerir MFA cuando el riesgo de inicio de sesión es *bajo*, *medio* o *alto*](#require-mfa-based-on-sign-in-risk)| |
|         |[Requerir equipos *y* dispositivos móviles compatibles](#require-compliant-pcs-and-mobile-devices)|Fuerza la administración de Intune para los PC y el teléfono/tabletas|
|**Extremadamente regulado**|[Requerir *siempre* MFA](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a>Asignar directivas a usuarios
Antes de configurar directivas, identifique los grupos de Azure AD que está usando para cada nivel de protección. Normalmente, la protección de línea de base se aplica a todos los de la organización. Un usuario que se incluya para la protección de línea base y sensible tendrá todas las directivas de línea de base aplicadas, además de las directivas confidenciales. La protección es acumulativa y se aplica la directiva más restrictiva. 

Una práctica recomendada es crear un grupo de Azure AD para la exclusión de acceso condicional. Agregue este grupo a todas las reglas de acceso condicional en "excluir". Esto le proporciona un método para proporcionar acceso a un usuario mientras se solucionan problemas de acceso. Solo se recomienda como solución temporal. Supervise si hay cambios en este grupo y asegúrese de que el grupo de exclusión solo se usa como se esperaba. 

El siguiente diagrama muestra un ejemplo de asignación de usuarios y exclusiones.

![Ejemplo de asignaciones y exclusiones de usuario para las reglas de MFA](../media/identity-access-policies-assignment.png)

En la ilustración, se asigna una directiva de acceso condicional que requiere MFA *siempre*a "Top Secret Project X Team". Tenga cuidado al aplicar niveles más altos de protección a los usuarios. Los miembros de este equipo de proyecto tendrán que proporcionar dos formas de autenticación cada vez que inicien sesión, incluso si no están viendo contenido altamente regulado.  

Todos los grupos de Azure AD creados como parte de estas recomendaciones deben crearse como grupos de Office 365. Esto es especialmente importante para la implementación de Azure Information Protection (AIP) al proteger documentos en SharePoint Online.

![Captura de pantalla para crear grupos de Office 365](../media/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a>Requerir MFA según el riesgo de inicio de sesión
Antes de requerir MFA, use primero una directiva de registro de la identidad de MFA de protección para registrar usuarios para MFA. Una vez que se hayan registrado los usuarios, puede exigir MFA para iniciar sesión. El [trabajo de requisitos previos](identity-access-prerequisites.md) incluye el registro de todos los usuarios con MFA.

Para crear una directiva de acceso condicional, haga lo siguiente: 

1. Vaya al [Azure Portal](https://portal.azure.com) e inicie sesión con sus credenciales. Una vez que haya iniciado sesión correctamente, verá el panel de Azure.

2. En el menú de la izquierda, seleccione **Azure Active Directory**.

3. En la sección **Seguridad**, seleccione **Acceso condicional**.

4. Pulse **Nueva directiva**.

![Directiva de acceso condicional de base de referencia](../media/secure-email/CA-EXO-policy-1.png)

 En las tablas siguientes se describen las opciones de configuración de directivas de acceso condicional para implementarlas en esta Directiva.

**Asignaciones**

|Tipo|Propiedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Usuarios y grupos|Incluir|Seleccionar usuarios y grupos: selecciona un grupo de seguridad específico que contiene usuarios de destino|Comenzar con el grupo de seguridad que incluye usuarios de prueba|
||Excluir|Grupo de seguridad de excepción; cuentas de servicio (identidades de aplicación)|Pertenencia modificada en una base de tiempo necesaria|
|Aplicaciones en la nube|Incluir|Seleccione las aplicaciones a las que desea que se aplique esta regla. Por ejemplo, seleccione Office 365 Exchange Online||
|Condiciones|Configurado|Sí|Configuración específica del entorno y las necesidades|
|Riesgo de inicio de sesión|Nivel de riesgo||Vea las instrucciones de la tabla siguiente|

**Riesgo de inicio de sesión**

Aplique la configuración en función del nivel de protección de destino.

|Propiedad|Nivel de protección|Valores|Notas|
|:---|:---------|:-----|:----|
|Nivel de riesgo|Línea base|Alto, medio|Comprobar ambos|
| |Confidencial|Alta, media, baja|Marcar los tres|
| |Extremadamente regulado| |Dejar todas las opciones desactivadas para exigir siempre la MFA|

**Controles de acceso**

|Tipo|Propiedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Conceder|Conceder acceso|True|Seleccionado|
||Exigir MFA|True|Check|
||Requerir que el dispositivo esté marcado como compatible|False||
||Requerir un dispositivo híbrido de Azure AD conectado|False||
||Requerir aplicación cliente aprobada|False||
||Exigir todos los controles seleccionados|True|Seleccionado|

> [!NOTE]
> Asegúrese de habilitar esta directiva; para ello, seleccione **activado**. También considere la posibilidad de usar la herramienta [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para probar la Directiva.



## <a name="block-clients-that-dont-support-modern-authentication"></a>Bloquear a los clientes que no sean compatibles con la autenticación moderna
1. Vaya al [Azure Portal](https://portal.azure.com) e inicie sesión con sus credenciales. Una vez que haya iniciado sesión correctamente, verá el panel de Azure.

2. En el menú de la izquierda, seleccione **Azure Active Directory**.

3. En la sección **Seguridad**, seleccione **Acceso condicional**.

4. Pulse **Nueva directiva**.

En las tablas siguientes se describen las opciones de configuración de directivas de acceso condicional para implementarlas en esta Directiva.

**Asignaciones**

|Tipo|Propiedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Usuarios y grupos|Incluir|Seleccionar usuarios y grupos: selecciona un grupo de seguridad específico que contiene usuarios de destino|Comenzar con el grupo de seguridad que incluye usuarios de prueba|
||Excluir|Grupo de seguridad de excepción; cuentas de servicio (identidades de aplicación)|Pertenencia modificada de forma temporal según necesidad|
|Aplicaciones en la nube|Incluir|Seleccione las aplicaciones a las que desea que se aplique esta regla. Por ejemplo, seleccione Office 365 Exchange Online||
|Condiciones|Configurado|Sí|Configurar las aplicaciones cliente|
|Aplicaciones cliente|Configurado|Sí|Aplicaciones móviles y clientes de escritorio, otros clientes (seleccione ambos)|

**Controles de acceso**

|Tipo|Propiedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Conceder|Bloquear acceso|True|Seleccionado|
||Exigir MFA|False||
||Requerir que el dispositivo esté marcado como compatible|False||
||Requerir un dispositivo híbrido de Azure AD conectado|False||
||Requerir aplicación cliente aprobada|False||
||Exigir todos los controles seleccionados|True|Seleccionado|

> [!NOTE]
> Asegúrese de habilitar esta directiva; para ello, seleccione **activado**. También considere la posibilidad de usar la herramienta [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para probar la Directiva.



## <a name="high-risk-users-must-change-password"></a>Los usuarios de riesgo alto deben cambiar la contraseña
Para asegurarse de que todas las cuentas de usuarios de alto riesgo se vean obligadas a realizar un cambio de contraseña al iniciar sesión, debe aplicar la siguiente directiva.

Inicie sesión en [Microsoft Azure Portal (https://portal.azure.com)](https://portal.azure.com/) con las credenciales de administrador y luego vaya a **Azure AD Identity Protection > Directiva de riesgo de usuario**.

**Asignaciones**

|Tipo|Propiedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Usuarios|Incluir|Todos los usuarios|Seleccionado|
||Excluir|Ninguno||
|Condiciones|Riesgo de usuario|Alto|Seleccionado|

**Controles**

| Tipo | Propiedades | Valores                  | Notas |
|:-----|:-----------|:------------------------|:------|
|      | Access     | Permitir acceso            | True  |
|      | Acceso     | Exigir cambio de contraseña | True  |

**Revisión:** no aplicable

> [!NOTE]
> Asegúrese de habilitar esta directiva; para ello, seleccione **activado**. También considere la posibilidad de usar la herramienta [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para probar la Directiva

## <a name="define-app-protection-policies"></a>Definir directivas de protección de aplicaciones
Las directivas de protección de aplicaciones (aplicación) definen qué aplicaciones están permitidas y las acciones que pueden llevar a cabo con los datos de la organización. Las opciones disponibles en la aplicación permiten a las organizaciones adaptar la protección a sus necesidades específicas. Para algunos, puede que no sea obvio qué configuración de directiva es necesaria para implementar un escenario completo. Para ayudar a las organizaciones a priorizar la protección de extremos de extremos de cliente móvil, Microsoft ha lanzado una taxonomía para el marco de protección de datos de aplicaciones para iOS y la administración de aplicaciones móviles de Android. 

El marco de protección de datos de la aplicación está organizado en tres niveles de configuración distintos, donde cada nivel se basa en el nivel anterior: 

- La protección de datos básicos de empresa garantiza que las aplicaciones estén protegidas con PIN y cifrados y realice operaciones selectivas de borrado. Para dispositivos Android, este nivel valida la atestación del dispositivo de Android. Se trata de una configuración de nivel de entrada que proporciona un control de protección de datos similar en las directivas de buzones de correo de Exchange Online y lo presenta y el llenado del usuario a la aplicación. 
- La protección de datos mejorada de la empresa presenta los mecanismos de prevención de fugas de datos y los requisitos mínimos del sistema operativo. Esta es la configuración que se aplica a la mayoría de los usuarios móviles que tienen acceso a datos de trabajo o escuela. 
- La protección de datos empresariales de alta calidad presenta mecanismos avanzados de protección de datos, configuración mejorada de PIN y defensa para amenazas de aplicaciones móviles. Esta configuración es preferible para los usuarios que tienen acceso a datos de alto riesgo. 

Para ver las recomendaciones específicas para cada nivel de configuración y las aplicaciones mínimas que deben protegerse, revise el [marco de protección de datos con directivas de protección de aplicaciones](https://docs.microsoft.com/mem/intune/apps/app-protection-framework). 

Mediante el uso de los principios descritos en [configuraciones de identidad y acceso a dispositivos](microsoft-365-policies-configurations.md), los niveles de protección base y confidencial se asignan estrechamente con la configuración de protección de datos mejorada de nivel 2. El nivel de protección altamente regulado se asigna estrechamente a la configuración de la protección de datos de nivel 3 Enterprise High.

|Nivel de protección |Directiva de protección de aplicaciones  |Más información  |
|---------|---------|---------|
|Línea base     | [Protección de datos mejorada de nivel 2](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | La configuración de la Directiva que se aplica en el nivel 2 incluye todas las configuraciones de directiva recomendadas para el nivel 1 y solo agrega o actualiza la configuración de directivas siguiente para implementar más controles y una configuración más sofisticada que el nivel 1.         |
|Confidencial     | [Protección de datos mejorada de nivel 2](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | La configuración de la Directiva que se aplica en el nivel 2 incluye todas las configuraciones de directiva recomendadas para el nivel 1 y solo agrega o actualiza la configuración de directivas siguiente para implementar más controles y una configuración más sofisticada que el nivel 1.        |
|Altamente regulado     | [Nivel 3 de protección empresarial alta para la información](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)        | La configuración de la Directiva que se aplica en el nivel 3 incluye todas las configuraciones de directiva recomendadas para los niveles 1 y 2 y solo agrega o actualiza la configuración de directivas siguiente para implementar más controles y una configuración más sofisticada que el nivel 2.        |

Para crear una nueva Directiva de protección de aplicaciones para cada plataforma (iOS y Android) en Microsoft Endpoint Manager con la configuración del marco de protección de datos, los administradores pueden:
1. Cree manualmente las directivas siguiendo los pasos de [Cómo crear e implementar directivas de protección de aplicaciones con Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/app-protection-policies).
2. Importe las [plantillas JSON del marco de configuración de la Directiva de protección de aplicaciones de Intune](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) de ejemplo con los [scripts de PowerShell de Intune](https://github.com/microsoftgraph/powershell-intune-samples).

## <a name="require-apps-that-support-intune-app-protection-policies"></a>Requerir aplicaciones compatibles con las directivas de protección de aplicaciones de Intune
Con el acceso condicional, las organizaciones pueden restringir el acceso a las aplicaciones de cliente de iOS y de iOS aprobadas con las directivas de protección de aplicaciones de Intune que se les aplican. Se requieren varias directivas de acceso condicional, con cada directiva dirigida a todos los usuarios potenciales. Puede encontrar más información sobre la creación de estas directivas en [requerir Directiva de protección de aplicaciones para Cloud Access Access con acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Siga el procedimiento "paso 1: configurar una directiva de acceso condicional de Azure AD para Office 365" en el [escenario 1: las aplicaciones de office 365 requieren aplicaciones aprobadas con directivas de protección de aplicaciones](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), lo que permite a Outlook para iOS y Android, pero impide que los clientes de Exchange ActiveSync con capacidad de OAuth se conecten a Exchange Online.

   > [!NOTE]
   > Esta Directiva garantiza que los usuarios móviles puedan acceder a todos los puntos de conexión de Office con las aplicaciones correspondientes.

2. Si habilita el acceso móvil a Exchange Online, implemente [los clientes de Block ActiveSync](secure-email-recommended-policies.md#block-activesync-clients), que impide que los clientes de Exchange ActiveSync que aprovechan la autenticación básica se conecten a Exchange Online.

   Las directivas anteriores aprovechan los controles Grant [requieren la aplicación cliente aprobada](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) y [requieren la Directiva de protección de aplicaciones](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Deshabilitar la autenticación heredada para otras aplicaciones cliente en dispositivos iOS y Android. Para obtener más información, consulte [bloquear clientes que no admiten la autenticación moderna](#block-clients-that-dont-support-modern-authentication).

## <a name="define-device-compliance-policies"></a>Definir directivas de cumplimiento de dispositivos

Las directivas de cumplimiento de dispositivos definen los requisitos que deben cumplir los dispositivos para que se marquen como compatibles. Cree directivas de cumplimiento de dispositivos de Intune en el centro de administración de Microsoft Endpoint Manager.

Cree una directiva para cada plataforma:
- Administrador de dispositivos Android
- Android Enterprise
- iOS/iPados
- macOS
- Esta opción está disponible en los siguientes tipos de dispositivos:
- Windows 8,1 y versiones posteriores
- Windows 10 y versiones posteriores

Para crear directivas de cumplimiento de dispositivos, inicie sesión en el [centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) con sus credenciales de administración y, a continuación, navegue a**directivas**de**directivas** > de cumplimiento de **dispositivos** > . Seleccione **crear Directiva**.

Para que se implementen las directivas de cumplimiento de dispositivos, se deben asignar a grupos de usuarios. Una directiva se asigna después de crearla y guardarla. En el centro de administración, seleccione la Directiva y, a continuación, seleccione **asignaciones**. Después de seleccionar los grupos que desea que reciban la Directiva, seleccione **Guardar** para guardar esa asignación de grupo e implementar la Directiva.

Para obtener instrucciones paso a paso sobre cómo crear directivas de cumplimiento en Intune, consulte [Create a Compliance Policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy) en la documentación de Intune.

Se recomiendan las siguientes opciones de configuración para Windows 10.

**Estado del dispositivo: reglas de evaluación del servicio de atestación de estado de Windows**

|Propiedades|Valores|Notas|
|:---------|:-----|:----|
|Requerir BitLocker|Obligatoria||
|Requerir el arranque seguro para habilitarse en el dispositivo|Obligatoria||
|Requerir integridad de código|Obligatoria||


**Propiedades del dispositivo**

|Tipo|Propiedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Versión del sistema operativo|Todos|No configurado||

**Seguridad del sistema**

|Tipo|Propiedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Password|Requerir una contraseña para desbloquear dispositivos móviles|Obligatoria||
||Contraseñas sencillas|Desbloquear||
||Tipo de contraseña|Valor predeterminado del dispositivo||
||Longitud mínima de la contraseña|6 ||
||Minutos máximos de inactividad antes de que se requiera la contraseña|15 |Esta configuración es compatible con las versiones 4,0 y anteriores de Android o KNOX 4,0 y superior. Para dispositivos iOS, es compatible con iOS 8,0 y versiones posteriores|
||Expiración de contraseña (días)|41||
||Número de contraseñas anteriores para impedir la reutilización|5 ||
||Requerir contraseña cuando el dispositivo vuelve del estado de inactividad (móvil y holográfica)|Obligatoria|Disponible para Windows 10 y versiones posteriores|
|Cifrado|Cifrado del almacenamiento de datos en el dispositivo|Obligatoria||
|Seguridad del dispositivo|Éste|Obligatoria||
||Antivirus|Obligatoria||
||Actualizados|Obligatoria|Esta configuración requiere una solución anti-spyware registrada en el centro de seguridad de Windows|
|Defender|Antimalware de Microsoft defender|Obligatoria||
||Versión mínima de antimalware de Microsoft defender||Solo se admite en el escritorio de Windows 10. Microsoft recomienda versiones no más de cinco versiones anteriores a la más reciente|
||La firma antimalware de Microsoft defender actualizada|Obligatoria||
||Protección en tiempo real|Obligatoria|Solo se admite en el escritorio de Windows 10|

**ATP de Microsoft Defender**

|Tipo|Propiedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Reglas de protección contra amenazas avanzada de Microsoft defender|Requerir que el dispositivo esté por encima o por debajo de la puntuación de riesgo de la máquina|Medio||


## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Requerir equipos compatibles (pero no teléfonos y tabletas compatibles)
Antes de agregar una directiva para requerir equipos compatibles, asegúrese de inscribir los dispositivos para la administración en Intune. Se recomienda usar la autenticación multifactor antes de inscribir los dispositivos en Intune para asegurarse de que el dispositivo está en la posesión del usuario deseado. 

Para requerir equipos compatibles:

1. Vaya al [Azure Portal](https://portal.azure.com) e inicie sesión con sus credenciales. Una vez que haya iniciado sesión correctamente, verá el panel de Azure.

2. En el menú de la izquierda, seleccione **Azure Active Directory**.

3. En la sección **Seguridad**, seleccione **Acceso condicional**.

4. Pulse **Nueva directiva**.

5. Escriba un nombre de directiva y seleccione los **Usuarios y grupos** a los que quiera que se aplique la directiva.

6. Seleccione **Aplicaciones en la nube**.

7. Elija **seleccionar aplicaciones**y seleccione las aplicaciones que desee en la lista de **aplicaciones de nube** . Por ejemplo, seleccione Office 365 Exchange Online. Elija **seleccionar** y **listo**.

8. Para requerir equipos compatibles, pero no teléfonos y tabletas compatibles, elija **condiciones** y **plataformas de dispositivos**. Elija **seleccionar plataformas de dispositivos** y seleccione **Windows** y **MacOS**.

9. Pulse **Conceder** en la sección **Controles de acceso**.

10. Elija **conceder acceso**, seleccione requerir que el **dispositivo esté marcado como compatible**. Para varios controles, seleccione **requerir todos los controles seleccionados**y, a continuación, elija **seleccionar**. 

11. Seleccione **Crear**.

Si su objetivo es requerir equipos *y* dispositivos móviles compatibles, no seleccione plataformas. Esto exige el cumplimiento para todos los dispositivos. 

## <a name="require-compliant-pcs-and-mobile-devices"></a>Requerir equipos *y* dispositivos móviles compatibles

Para requerir el cumplimiento de todos los dispositivos:

1. Vaya al [Azure Portal](https://portal.azure.com) e inicie sesión con sus credenciales. Una vez que haya iniciado sesión correctamente, verá el panel de Azure.

2. En el menú de la izquierda, seleccione **Azure Active Directory**.

3. En la sección **Seguridad**, seleccione **Acceso condicional**.

4. Pulse **Nueva directiva**.

5. Escriba un nombre de directiva y seleccione los **Usuarios y grupos** a los que quiera que se aplique la directiva.

6. Seleccione **Aplicaciones en la nube**.

7. Elija **seleccionar aplicaciones**y seleccione las aplicaciones que desee en la lista de **aplicaciones de nube** . Por ejemplo, seleccione Office 365 Exchange Online. Elija **seleccionar** y **listo**.

8. Pulse **Conceder** en la sección **Controles de acceso**.

9. Elija **conceder acceso**, seleccione requerir que el **dispositivo esté marcado como compatible**. Para varios controles, seleccione **requerir todos los controles seleccionados**y, a continuación, elija **seleccionar**. 

10. Seleccione **Crear**.

Al crear esta Directiva, no seleccione plataformas. Esto aplica los dispositivos compatibles.


## <a name="next-steps"></a>Siguientes pasos

[Más información sobre recomendaciones de directivas para proteger el correo electrónico](secure-email-recommended-policies.md)
