---
title: Identidad y dispositivo comunes, obtener acceso a directivas - Microsoft 365 Enterprise | Documentos de Microsoft
description: Explica las directivas recomendadas por Microsoft para aplicar directivas y configuraciones de identidad y acceso a dispositivos.
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: ab8454c27cd57b6bd5cc8df6e1526ee2950ac998
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "26871794"
---
# <a name="common-identity-and-device-access-policies"></a>Directivas comunes de acceso a dispositivos e identidades
Este artículo describe la común recomendada directivas para proteger el acceso a los servicios, de la nube, con aplicaciones locales publicarán con Proxy de aplicación de Azure AD. 

Esta guía explica cómo implementar las directivas recomendadas en un entorno recién aprovisionado. Configuración de estas directivas en un entorno de laboratorio independiente le permite a comprender y evaluar las directivas recomendadas antes de la implantación para los entornos de preproducción y producción de ensayo. Puede ser de su entorno recientemente aprovisionado sólo en la nube o híbridas.  

## <a name="policy-set"></a>Conjunto de directivas 

El siguiente diagrama ilustra el conjunto de directivas recomendado. Muestra qué niveles de protecciones de cada directiva se aplica a y si las directivas se aplican a equipos o teléfonos y tabletas o ambas categorías de dispositivos. También indica donde se configuran estas directivas.

![Directivas comunes para configurar el acceso de identidad y dispositivos](../images/Identity_device_access_policies_byplan.png)


El resto de este artículo describe cómo configurar estas directivas. 

Se recomienda el uso de la autenticación multifactor antes de dispositivos que se inscriben en Intune para garantía de que el dispositivo está en posesión del usuario previsto. También debe inscribirse dispositivos en Intune antes de aplicar las directivas de cumplimiento de normas de dispositivo.

Para dar tiempo para realizar estas tareas, se recomienda implementar las directivas de línea de base en el orden en que aparecen en esta tabla. Sin embargo, las directivas MFA para protección confidencial y altamente regulada pueden implementarse en cualquier momento.


|Nivel de protección|Policies|Más información|
|:---------------|:-------|:----------------|
|**Línea base**|[Requerir MFA al inicio de sesión de riesgo es *medio* o *alto*](#require-mfa-based-on-sign-in-risk)| |
|        |[Clientes de bloque que no admiten la autenticación moderna](#block-clients-that-dont-support-modern-authentication)|Los clientes que no usan autenticación moderna pueden omitir las reglas de acceso condicional, por lo que es importante bloquear estos mensajes|
|        |[Los usuarios de alto riesgo deben cambiar la contraseña](#high-risk-users-must-change-password)|Obliga a los usuarios cambiar su contraseña al iniciar la sesión si se detecta actividad de alto riesgo por su cuenta|
|        |[Definir directivas de protección de aplicaciones](#define-app-protection-policies)|Una directiva por plataforma (iOS, Android, Windows).|
|        |[Requieren aplicaciones aprobadas](#require-approved-apps)|Aplica la protección contra la aplicación móvil para teléfonos y tabletas|
|        |[Definir directivas de cumplimiento de normas de dispositivo](#define-device-compliance-policies)|Una directiva para cada plataforma|
|        |[Requerir PCs compatibles con](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Aplica Intune administración de equipos|
|**Confidencial**|[Requerir MFA al inicio de sesión de riesgo es *bajo*, *medio* o *alto*](#require-mfa-based-on-sign-in-risk)| |
|         |[Requerir compatible con PC *y* dispositivos móviles](#require-compliant-pcs-and-mobile-devices)|Aplica la administración Intune para PC y teléfono/tabletas|
|**Extremadamente regulado**|[*Siempre* requieren MFA](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a>Asignación de directivas a los usuarios
Antes de configurar las directivas, identifique los grupos de Azure AD que utiliza para cada nivel de protección. Normalmente, la protección de línea de base se aplica a todas las personas de la organización. Un usuario que se incluye para la línea de base y protección confidencial tendrá todas las directivas de línea de base que se aplica además de las directivas confidenciales. Protección es acumulativa y se aplica la directiva más restrictiva. 

Un procedimiento recomendado consiste en crear un grupo de Azure AD de exclusión de acceso condicional. Agregar este grupo a todas las reglas de acceso condicional en "Excluir". Esto le ofrece un método para proporcionar acceso a un usuario mientras solucionar problemas de acceso. Esto se recomienda como solución temporal. Supervise este grupo para que los cambios y asegúrese de que se está usando el grupo de exclusión sólo como se esperaba. 

En el siguiente diagrama se proporciona un ejemplo de asignación de usuario y las exclusiones.

![Asignación de usuario de ejemplo y exclusiones para las reglas de MFA](../images/identity-access-policies-assignment.png)

En la ilustración "equipo de proyecto secreto superior X" se asigna una directiva de acceso condicional que requiere MFA *siempre*. Ser razonable al aplicar mayores niveles de protección a los usuarios. Los miembros de este equipo de proyecto será necesario para proporcionar dos formas de autenticación cada vez que inicien sesión, incluso si no están viendo contenido altamente regulado.  

Todos los grupos de Azure AD creados como parte de estas recomendaciones deben crearse como grupos de Office 365. Esto es especialmente importante para la implementación de protección de información de Azure (AIP) cuando la protección de documentos en SharePoint Online.

![Captura de pantalla para la creación de grupos de Office 365](../images/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a>Requerir MFA en función de inicio de sesión de riesgo
Antes de solicitar MFA, utilice en primer lugar una directiva de registro de MFA de protección de identidad para registrar los usuarios de MFA. Después de que se registran los usuarios puede exigir MFA para el inicio de sesión. El [trabajo necesario como requisito previo](identity-access-prerequisites.md) se incluye el registro de todos los usuarios con MFA.

Para crear una directiva de acceso condicional, haga lo siguiente: 

1. Vaya al [portal de Azure](https://portal.azure.com)e iniciar sesión con sus credenciales. Una vez que ha iniciado sesión correctamente, verá el panel de Azure.

2. En el menú de la izquierda, seleccione **Azure Active Directory**.

3. En la sección **Seguridad**, seleccione **Acceso condicional**.

4. Pulse **Nueva directiva**.

![Directiva de acceso condicional de base de referencia](./media/secure-email/CA-EXO-policy-1.png)

 En las tablas siguientes se describe la configuración de directiva de acceso condicional para implementar para esta directiva.

**Asignaciones**

|Tipo|Propiedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Usuarios y grupos|Incluir|Seleccionar usuarios y grupos: selecciona un grupo de seguridad específico que contiene usuarios de destino|Comenzar con el grupo de seguridad que incluye usuarios de prueba|
||Excluir|Grupo de seguridad de excepción; cuentas de servicio (identidades de aplicación)|Pertenencia al modificar en una base de temporal según sea necesario|
|Aplicaciones en la nube|Incluir|Seleccione las aplicaciones que desee aplicar a esta regla. Por ejemplo, seleccione Exchange en línea de Office 365||
|Condiciones|Configurado|Sí|Configuración específica del entorno y las necesidades|
|Riesgo de inicio de sesión|Nivel de riesgo||Vea las instrucciones en la tabla siguiente|

**Riesgo de inicio de sesión**

Aplicar la configuración según el nivel de protección de destino.

|Propiedad|Nivel de protección|Valores|Notas|
|:---|:---------|:-----|:----|
|Nivel de riesgo|Línea base|Alto, medio|Comprobar ambos|
| |Confidencial|Alta, Media, baja|Marcar los tres|
| |Extremadamente regulado| |Deje todas las opciones de verificación desactivada para aplicar siempre MFA|

**Controles de acceso**

|Tipo|Propiedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Conceder|Conceder acceso|True|Seleccionado|
||Exigir MFA|True|Check|
||Requerir dispositivo para ser marcado como compatible|False||
||Requerir híbrida dispositivo unido a AD de Azure|False||
||Requiere aplicación cliente aprobado|False||
||Exigir todos los controles seleccionados|True|Seleccionado|

> [!NOTE]
> Asegúrese de habilitar esta directiva, eligiendo **en**. Tenga en cuenta también con la herramienta de [¿Qué ocurre si](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para probar la directiva.



## <a name="block-clients-that-dont-support-modern-authentication"></a>Clientes de bloque que no admiten la autenticación moderna
1. Vaya al [portal de Azure](https://portal.azure.com)e iniciar sesión con sus credenciales. Una vez que ha iniciado sesión correctamente, verá el panel de Azure.

2. En el menú de la izquierda, seleccione **Azure Active Directory**.

3. En la sección **Seguridad**, seleccione **Acceso condicional**.

4. Pulse **Nueva directiva**.

En las tablas siguientes se describe la configuración de directiva de acceso condicional para implementar para esta directiva.

**Asignaciones**

|Tipo|Propiedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Usuarios y grupos|Incluir|Seleccionar usuarios y grupos: selecciona un grupo de seguridad específico que contiene usuarios de destino|Comenzar con el grupo de seguridad que incluye usuarios de prueba|
||Excluir|Grupo de seguridad de excepción; cuentas de servicio (identidades de aplicación)|Pertenencia modificada de forma temporal según necesidad|
|Aplicaciones en la nube|Incluir|Seleccione las aplicaciones que desee aplicar a esta regla. Por ejemplo, seleccione Exchange en línea de Office 365||
|Condiciones|Configurado|Sí|Configurar aplicaciones de cliente|
|Aplicaciones de cliente|Configurado|Sí|Aplicaciones móviles y los clientes de escritorio, otros clientes (seleccione ambos)|

**Controles de acceso**

|Tipo|Propiedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Conceder|Bloquear acceso|True|Seleccionado|
||Exigir MFA|False||
||Requerir dispositivo para ser marcado como compatible|False||
||Requerir híbrida dispositivo unido a AD de Azure|False||
||Requiere aplicación cliente aprobado|False||
||Exigir todos los controles seleccionados|True|Seleccionado|

> [!NOTE]
> Asegúrese de habilitar esta directiva, eligiendo **en**. Tenga en cuenta también con la herramienta de [¿Qué ocurre si](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para probar la directiva.



## <a name="high-risk-users-must-change-password"></a>Los usuarios de alto riesgo deben cambiar la contraseña
Para garantizar que las cuentas de los usuarios de alto riesgo todas en peligro se ve obligado a realizar un cambio de contraseña al iniciar sesión en, se debe aplicar la siguiente directiva.

Inicie sesión en el [portal de Microsoft Azure (http://portal.azure.com) ](http://portal.azure.com/) con sus credenciales de administrador y, a continuación, navegue hasta **Azure AD identidad protección > directiva de usuario de riesgo**.

**Asignaciones**

|Tipo|Propiedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Usuarios|Incluir|Todos los usuarios|Seleccionado|
||Excluir|Ninguno||
|Condiciones|Riesgo de usuario|Alto|Seleccionado|

**Controles**

| Tipo | Propiedades | Valores                  | Notas |
|:-----|:-----------|:------------------------|:------|
|      | Acceso     | Permitir acceso            | True  |
|      | Acceso     | Exigir cambio de contraseña | True  |

**Revisión:** no es aplicable.

> [!NOTE]
> Asegúrese de habilitar esta directiva, eligiendo **en**. Tenga en cuenta también con la herramienta de [¿Qué ocurre si](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) para probar la directiva

## <a name="define-app-protection-policies"></a>Definir directivas de protección de aplicaciones
Directivas de protección de aplicaciones definición qué aplicaciones se permiten y las acciones pueden realizar con los datos de la organización. Crear aplicación Intune directivas de protección desde dentro del portal de Azure. 

Crear una directiva para cada plataforma:
- iOS
- Android
- Windows 10

Para crear una nueva directiva de protección de la aplicación, inicie sesión el portal de Microsoft Azure con sus credenciales de administrar y, a continuación, vaya a **aplicaciones móviles > directivas de protección de aplicaciones**. Elija **Agregar una directiva**.

Hay ligeras diferencias en la protección de la aplicación en las opciones de directiva entre iOS y Android. La por debajo de la directiva es específicamente para Android. Use esta opción como una guía para las otras directivas.

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

En las tablas siguientes se describen la configuración recomendada:

|Tipo|Propiedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Reubicación de datos|Impedir copias de seguridad de Android|Sí|En iOS esto específicamente llama a iTunes e iCloud|
||Permitir que la aplicación transfiera datos a otras aplicaciones|Aplicaciones administradas por directivas||
||Permitir a la aplicación recibir datos de otras aplicaciones|Aplicaciones administradas por directivas||
||Impedir "Guardar como"|Sí||
||Seleccione qué datos corporativos de servicios de almacenamiento se pueden guardar en|OneDrive para la empresa, SharePoint||
||Restringir cortar, copiar y pegar con otras aplicaciones|Aplicaciones de la directiva administrada con pegar en||
||Restringir contenido web para mostrar en Managed Browser|No||
||Cifrar datos de aplicación|Sí|En iOS, seleccione la opción: Cuando el dispositivo está bloqueado|
||Deshabilitar el cifrado de la aplicación cuando está habilitado el dispositivo|Sí|Deshabilitar esta opción para evitar la doble cifrado|
||Deshabilitar la sincronización de contactos|No||
||Deshabilitar la impresión|No||
|Acceso|Requerir PIN para acceder|Sí||
||Seleccione el tipo de|Numérico||
||Permitir PIN sencillo|No||
||Longitud del PIN|6||
||Permitir desbloqueo mediante huellas digitales en lugar de mediante PIN|Sí||
||Deshabilitar aplicación PIN cuando se administra el NIP del dispositivo|Sí||
||Requerir credenciales corporativas para el acceso|No||
||Volver a comprobar los requisitos de acceso después de (minutos)|30||
||Bloquear captura de pantalla y asistente de Android|No|En iOS esta opción no está disponible|
|Requisitos de seguridad de inicio de sesión|Intentos de PIN de Max|5|Restablecer el Pin|
||Período de gracia sin conexión|720|Bloquear acceso|
||Intervalo sin conexión (días) antes de que se borren los datos de la aplicación|90|Borrar datos|
||Dispositivos Jailbroken/raíz| |Borrar datos|

Cuando haya terminado, no olvide seleccionar "Crear". Repita los pasos anteriores y reemplace la plataforma seleccionada (desplegable) con iOS. Esto crea dos directivas de aplicación, por lo que una vez creada la directiva, a continuación, asignar grupos a la directiva e implementarlo.

Para editar las directivas y asignar estas directivas a los usuarios, vea [cómo crear y asignar directivas de protección de aplicaciones](https://docs.microsoft.com/intune/app-protection-policies). 

## <a name="require-approved-apps"></a>Requieren aplicaciones aprobadas
Para requerir aplicaciones aprobadas:

1. Vaya al [portal de Azure](https://portal.azure.com)e iniciar sesión con sus credenciales. Una vez que ha iniciado sesión correctamente, verá el panel de Azure.

2. En el menú de la izquierda, seleccione **Azure Active Directory**.

3. En la sección **Seguridad**, seleccione **Acceso condicional**.

4. Pulse **Nueva directiva**.

5. Escriba un nombre de directiva y seleccione los **Usuarios y grupos** a los que quiera que se aplique la directiva.

6. Seleccione **Aplicaciones en la nube**.

7. Elija **seleccionar aplicaciones**, seleccione las aplicaciones que desee en la lista de **aplicaciones en la nube** . Por ejemplo, seleccione Exchange en línea de Office 365. Elija **Seleccionar** y **Listo**.

8. Pulse **Conceder** en la sección **Controles de acceso**.

9. Elija **conceder acceso**, seleccione **Requerir aprobada por el cliente app**. Para varios controles, seleccione **requerir los controles seleccionados**, a continuación, elija **Seleccionar**. 

10. Elija **Crear**.

## <a name="define-device-compliance-policies"></a>Definir directivas de cumplimiento de dispositivo

Las directivas de cumplimiento de dispositivo definen los requisitos que deben cumplir para que se marque como compatible con los dispositivos. Crear Intune dispositivo directivas de cumplimiento de normas desde dentro del portal de Azure. 

Crear una directiva para cada plataforma:
- Android
- Enterprise Android
- iOS
- Mac OS
- Windows Phone 8.1
- Windows 8.1 y posterior
- 10 y versiones posteriores de Windows

Para crear directivas de cumplimiento de dispositivo, inicie sesión el portal de Microsoft Azure con sus credenciales de administrar y, a continuación, vaya a **Intune > cumplimiento de dispositivo**. Seleccione **Crear directiva**.

La siguiente configuración se recomienda para 10 de Windows.

**Estado de dispositivo: las reglas de evaluación del servicio de certificación de mantenimiento de Windows**

|Propiedades|Valores|Notas|
|:---------|:-----|:----|
|Requerir BitLocker|Obligatoria||
|Requerir inicio seguro a habilitarse en el dispositivo|Obligatoria||
|Requerir la integridad del código|Obligatoria||


**Propiedades del dispositivo**

|Tipo|Propiedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Versión del sistema operativo|Todos|No configurado||

Para todas las directivas anteriores se considere implementadas, debe dirigirse a grupos de usuarios. Puede hacerlo mediante la creación de la directiva (al guardar) o posterior mediante la selección de **Administración de implementación** en la sección de **Directiva** (mismo nivel que agregar).

**Seguridad del sistema**

|Tipo|Propiedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Contraseña|Requerir una contraseña para desbloquear los dispositivos móviles|Obligatoria||
||Contraseñas simples|Bloque||
||Tipo de contraseña|Valor predeterminado del dispositivo||
||Longitud mínima de la contraseña|6||
||Número máximo de minutos de inactividad antes de que se requiere una contraseña|15 |Esta configuración se admite para Android versiones 4.0 y superior o KNOX 4.0 y anteriores. Para los dispositivos iOS, es compatible con para iOS 8.0 y versiones posteriores|
||Expiración de contraseña (días)|41||
||Número de contraseñas anteriores para evitar que la reutilización|5||
||Requerir contraseña al dispositivo devuelve de estado inactivo (Mobile y Holographic)|Obligatoria|Disponible para Windows 10 y versiones posteriores|
|Cifrado|Cifrado de almacenamiento de datos en el dispositivo|Obligatoria||
|Seguridad de dispositivos|Firewall|Obligatoria||
||Antivirus|Obligatoria||
||Anti spyware|Obligatoria|Esta configuración requiere una solución de Anti-Spyware registrada con el centro de seguridad de Windows|
|Defender|Windows Defender Antimalware|Obligatoria||
||Versión mínima de Windows Defender Antimalware||Solo se admite para el escritorio de Windows 10. Microsoft no recomienda más de cinco detrás de la versión más reciente de versiones|
||Firma de Windows Defender Antimalware actualizado|Obligatoria||
||Protección en tiempo real|Obligatoria|Solo se admite para el escritorio de Windows 10|

**ATP de Windows Defender**

|Tipo|Propiedades|Valores|Notas|
|:---|:---------|:-----|:----|
|Reglas de protección de amenaza avanzada de Windows Defender|Requieren el dispositivo esté en o por debajo de la puntuación de riesgo de máquina|Medio||

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Requieren compatible con PCs (pero no compatible con teléfonos y tabletas)
Antes de agregar una directiva para exigir PCs compatibles con, no olvide inscribirse dispositivos para la administración en Intune. Se recomienda el uso de la autenticación multifactor antes de dispositivos que se inscriben en Intune para garantía de que el dispositivo está en posesión del usuario previsto. 

Para requerir PCs compatibles con:

1. Vaya al [portal de Azure](https://portal.azure.com)e iniciar sesión con sus credenciales. Una vez que ha iniciado sesión correctamente, verá el panel de Azure.

2. En el menú de la izquierda, seleccione **Azure Active Directory**.

3. En la sección **Seguridad**, seleccione **Acceso condicional**.

4. Pulse **Nueva directiva**.

5. Escriba un nombre de directiva y seleccione los **Usuarios y grupos** a los que quiera que se aplique la directiva.

6. Seleccione **Aplicaciones en la nube**.

7. Elija **seleccionar aplicaciones**, seleccione las aplicaciones que desee en la lista de **aplicaciones en la nube** . Por ejemplo, seleccione Exchange en línea de Office 365. Elija **Seleccionar** y **Listo**.

8. Para requerir compatible con PC, pero no compatible con teléfonos y tabletas, elija **las condiciones** y **las plataformas de dispositivo**. Elija **Seleccionar las plataformas de dispositivo** y seleccione **Windows** y **Mac OS**.

9. Pulse **Conceder** en la sección **Controles de acceso**.

10. Elija **conceder acceso**, seleccione **requiere el dispositivo que se marcará como compatible con**. Para varios controles, seleccione **requerir todos los controles seleccionados**, a continuación, elija **Seleccionar**. 

11. Elija **Crear**.

Si su objetivo es que requieren compatible con PC *y* dispositivos móviles, no seleccione plataformas. Esto exige el cumplimiento de normas para todos los dispositivos. 

## <a name="require-compliant-pcs-and-mobile-devices"></a>Requerir compatible con PC *y* dispositivos móviles

Para requerir el cumplimiento de normas para todos los dispositivos:

1. Vaya al [portal de Azure](https://portal.azure.com)e iniciar sesión con sus credenciales. Una vez que ha iniciado sesión correctamente, verá el panel de Azure.

2. En el menú de la izquierda, seleccione **Azure Active Directory**.

3. En la sección **Seguridad**, seleccione **Acceso condicional**.

4. Pulse **Nueva directiva**.

5. Escriba un nombre de directiva y seleccione los **Usuarios y grupos** a los que quiera que se aplique la directiva.

6. Seleccione **Aplicaciones en la nube**.

7. Elija **seleccionar aplicaciones**, seleccione las aplicaciones que desee en la lista de **aplicaciones en la nube** . Por ejemplo, seleccione Exchange en línea de Office 365. Elija **Seleccionar** y **Listo**.

8. Pulse **Conceder** en la sección **Controles de acceso**.

9. Elija **conceder acceso**, seleccione **requiere el dispositivo que se marcará como compatible con**. Para varios controles, seleccione **requerir todos los controles seleccionados**, a continuación, elija **Seleccionar**. 

10. Elija **Crear**.

Al crear esta directiva, no seleccione plataformas. Esto exige dispositivos compatibles con.




<!---
#### Data loss prevention
The goal for your device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain or enroll their PCs into management with Microsoft Intune or System Center Configuration Manager.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact

For most organizations, it is important to be able to set user expectations around when and for which conditions they will be expected to sign into Office 365 to access their email.  

Users typically benefit from single sign-on (SSO) except during the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users may be asked to MFA whenever a **medium or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Sensitive
This section describes the recommendations for the sensitive tier of data, identity, and device protection. These recommendations are for customers who have a subset of data that must be protected at higher levels or require all data to be protected at these higher levels.

You can apply increased protection to all or specific data sets in your Office 365 environment. For example, you can apply policies to ensure sensitive data is only shared between protected apps to prevent data loss. We recommend protecting identities and devices that access sensitive data with comparable levels of security.

### Conditional access policy settings
#### Identity protection

You can give users single sign-on (SSO) experience as described in earlier sections. You only need to intervene when necessary based on [risk events](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events).   

* Require MFA on **low or above** risk sessions
* Require secure password change for high risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data loss prevention

The goal for these device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their PCs to an Active Directory Domain or enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 email.

Users typically benefit from single sign-on (SSO) except under the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to MFA whenever a **low or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Highly regulated
This section describes the recommendations for the highly regulated tier of data, identity, and device protection. These recommendations are for customers who may have a very small amount of data that is highly classified, trade secret, or regulated data. Microsoft provides capabilities to help organizations meet these requirements, including added protection for identities and devices.

### Conditional access policy settings
#### Identity protection

For the highly regulated tier Microsoft recommends enforcing MFA for all new sessions.
* Require MFA for all new sessions
* Require secure password change for **high** risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data Loss Prevention
The goal for these device and app management policies is to prevent data loss in the event of a lost or stolen device. This is done by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

For the highly regulated tier, we recommend requiring apps that support Intune App Protection policy running only on Intune compliant or domain-joined devices.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain, **or** enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that devices used to access Office 365 email and files are managed by Intune or company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are Low risk as determined by a third-party MTP like Lookout or SkyCure.|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 files.

* Users configured as highly regulated will be required to re-authenticate with MFA after their session expires.
* When users at risk sign-in they will be asked to change their password after completing MFA.
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to perform MFA whenever they begin a new session.  
  * Users will be required to use email apps that support the Intune App Protection SDK
  * Users will be required to access emails from Intune compliant or AD domain-joined devices.
--->
## <a name="next-steps"></a>Pasos siguientes

[Más información sobre recomendaciones de directivas para proteger el correo electrónico](secure-email-recommended-policies.md)
