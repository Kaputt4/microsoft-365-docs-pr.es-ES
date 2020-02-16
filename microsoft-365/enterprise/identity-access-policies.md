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
ms.openlocfilehash: 272e8a76cdb3a1555f561bd56e63422f14394904
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067437"
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
|        |[Requerir aplicaciones aprobadas](#require-approved-apps)|Fuerza la protección de aplicaciones móviles para teléfonos y tabletas|
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
|      | Access     | Exigir cambio de contraseña | True  |

**Revisión:** no aplicable

> [!NOTE]
> Asegúrese de habilitar esta directiva; para ello, seleccione **activado**. También considere la posibilidad de usar la herramienta [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para probar la Directiva

## <a name="define-app-protection-policies"></a>Definir directivas de protección de aplicaciones
Las directivas de protección de aplicaciones definen qué aplicaciones están permitidas y las acciones que pueden llevar a cabo con los datos de la organización. Cree directivas de protección de aplicaciones de Intune desde dentro de Azure portal. 

Cree una directiva para cada plataforma:
- iOS
- Android
- Windows 10

Para crear una nueva Directiva de protección de aplicaciones, inicie sesión en el portal de Microsoft Azure con sus credenciales de administrador y, a continuación, navegue a > **directivas de protección**de aplicaciones de **aplicaciones cliente**. Elija **crear Directiva**.

Hay ligeras diferencias en las opciones de directiva de protección de aplicaciones entre iOS y Android. La siguiente directiva es específicamente para Android. Use esto como guía para sus otras directivas.

La lista de aplicaciones recomendada incluye lo siguiente:
- PowerPoint
- Excel
- Word
- Microsoft Teams
- Microsoft SharePoint
- Microsoft Visio Viewer
- OneDrive
- OneNote
- Outlook

En las siguientes tablas se describe la configuración recomendada:

|Tipo|Propiedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Reubicación de datos|Impedir copias de seguridad de Android|Sí|En iOS esto específicamente llama a iTunes e iCloud|
||Permitir que la aplicación transfiera datos a otras aplicaciones|Aplicaciones administradas por directivas||
||Permitir a la aplicación recibir datos de otras aplicaciones|Aplicaciones administradas por directivas||
||Impedir "Guardar como"|Sí||
||Seleccione qué datos corporativos de servicios de almacenamiento se pueden guardar en|OneDrive para la empresa, SharePoint||
||Restringir cortar, copiar y pegar con otras aplicaciones|Aplicaciones administradas por directiva con pegar||
||Restringir contenido web para mostrar en Managed Browser|No||
||Cifrar datos de aplicación|Sí|En iOS, seleccione la opción: Cuando el dispositivo está bloqueado|
||Deshabilitar el cifrado de aplicaciones cuando el dispositivo está habilitado|Sí|Deshabilitar esta opción para evitar el cifrado doble|
||Deshabilitar la sincronización de contactos|No||
||Deshabilitar impresión|No||
|Acceso|Requerir PIN para acceder|Sí||
||Tipo de selección|Numérico||
||Permitir PIN sencillo|No||
||Longitud del PIN|6 ||
||Permitir desbloqueo mediante huellas digitales en lugar de mediante PIN|Sí||
||Deshabilitar PIN de la aplicación cuando el PIN del dispositivo esté administrado|Sí||
||Requerir credenciales corporativas para el acceso|No||
||Volver a comprobar los requisitos de acceso después de (minutos)|semestre||
||Bloquear captura de pantalla y asistente de Android|No|En iOS esta opción no está disponible|
|Requisitos de seguridad de inicio de sesión|Número máximo de intentos de PIN|5 |Restablecer PIN|
||Período de gracia sin conexión|720|Bloquear acceso|
||Intervalo sin conexión (días) antes de que se borren los datos de la aplicación|90|Borrar datos|
||Dispositivos con jailbreak o Rooting| |Borrar datos|

Cuando termine, recuerde seleccionar "crear". Repita los pasos anteriores y reemplace la plataforma seleccionada (desplegable) por iOS. Esto crea dos directivas de aplicación, por lo que una vez creada la directiva, asígnele grupos e impleméntela.

Para editar las directivas y asignar estas directivas a los usuarios, vea [Cómo crear y asignar directivas de protección de aplicaciones](https://docs.microsoft.com/intune/app-protection-policies). 

## <a name="require-approved-apps"></a>Requerir aplicaciones aprobadas
Para requerir aplicaciones aprobadas:

1. Vaya al [Azure Portal](https://portal.azure.com) e inicie sesión con sus credenciales. Una vez que haya iniciado sesión correctamente, verá el panel de Azure.

2. En el menú de la izquierda, seleccione **Azure Active Directory**.

3. En la sección **Seguridad**, seleccione **Acceso condicional**.

4. Pulse **Nueva directiva**.

5. Escriba un nombre de directiva y seleccione los **Usuarios y grupos** a los que quiera que se aplique la directiva.

6. Seleccione **Aplicaciones en la nube**.

7. Elija **seleccionar aplicaciones**y seleccione las aplicaciones que desee en la lista de **aplicaciones de nube** . Por ejemplo, seleccione Office 365 Exchange Online. Elija **seleccionar** y **listo**.

8. Elija **condiciones**, seleccione **plataformas de dispositivos**y, a continuación, elija **configurar** .

9. En **incluir**, elija **seleccionar plataformas de dispositivos**, seleccione **Android** e **iOS**. Haga clic en **listo** y vuelva a **realizar**

10. Pulse **Conceder** en la sección **Controles de acceso**.

11. Elija **conceder acceso**y seleccione **requerir aplicación cliente aprobada**. Para varios controles, seleccione **requerir los controles seleccionados**y, a continuación, elija **seleccionar**. 

12. Seleccione **Crear**.

## <a name="define-device-compliance-policies"></a>Definir directivas de cumplimiento de dispositivos

Las directivas de cumplimiento de dispositivos definen los requisitos que deben cumplir los dispositivos para que se marquen como compatibles. Cree directivas de cumplimiento de dispositivos de Intune desde dentro del portal de Azure. 

Cree una directiva para cada plataforma:
- Android
- Android Enterprise
- iOS
- macOS
- Esta opción está disponible en los siguientes tipos de dispositivos:
- Windows 8,1 y versiones posteriores
- Windows 10 y versiones posteriores

Para crear directivas de cumplimiento de dispositivos, inicie sesión en el portal de Microsoft Azure con sus credenciales de administración y, a continuación, navegue hasta **Intune > el cumplimiento de dispositivos**. Seleccione **Crear directiva**.

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

Para que todas las directivas anteriores se consideren implementadas, deben establecerse como destinos en los grupos de usuarios. Para ello, cree la Directiva (al guardar) o una versión posterior seleccionando **administrar la implementación** en la sección **Directiva** (mismo nivel que agregar).

**Seguridad del sistema**

|Tipo|Propiedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Contraseña|Requerir una contraseña para desbloquear dispositivos móviles|Obligatoria||
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
|Defender|Antimalware de Windows Defender|Obligatoria||
||Versión mínima de antimalware de Windows Defender||Solo se admite en el escritorio de Windows 10. Microsoft recomienda versiones no más de cinco versiones anteriores a la más reciente|
||Firma antimalware de Windows Defender actualizada hasta la fecha|Obligatoria||
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
