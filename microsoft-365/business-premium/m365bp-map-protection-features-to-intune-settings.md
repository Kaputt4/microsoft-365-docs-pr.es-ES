---
title: Cómo se asignan las características de protección de Microsoft 365 Empresa Premium a la configuración de Intune
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-security
ms.subservice: other
ms.date: 09/15/2022
ms.localizationpriority: high
ms.collection:
- tier1
ms.custom:
- MiniMaven
search.appverid:
- BCS160
- MET150
description: Obtenga más información sobre cómo se asignan las características de protección de Microsoft 365 Empresa Premium a la configuración de Intune. La suscripción proporciona una licencia para modificar la configuración de Intune.
ms.openlocfilehash: 185eda9e5b5e214716608d4232a0ea81c00d6b4b
ms.sourcegitcommit: 0283c436f3ba61a708b52b57a1955f5ea74376a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2022
ms.locfileid: "68096377"
---
# <a name="how-do-protection-features-in-microsoft-365-business-premium-map-to-intune-settings"></a>Cómo se asignan las características de protección de Microsoft 365 Empresa Premium a la configuración de Intune

## <a name="android-and-ios-application-protection-settings"></a>Configuración de protección de aplicación Android o iOS

En la siguiente tabla, se detalla cómo se asigna a la configuración de Intune la configuración de directiva de aplicaciones de Android o iOS.
  
Para buscar la configuración de Intune, inicie sesión con las credenciales de administrador de Microsoft 365 Empresa Premium, vaya a **centros de administración** y, a continuación, **Intune**.
  
 > [!IMPORTANT]
 > 
 > A Microsoft 365 Business Premium subscription gives you a license to modify all the Intune settings. See [Introduction to Intune to get started.](/intune/introduction-intune)
  
Haga clic en el nombre de la directiva que desea &mdash;, por ejemplo, la directiva de aplicación para Android &mdash; y luego elija **Configuración de la directiva**.
  
En **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo**
  
|**Configuración de directiva de aplicación Android o iOS**|**Configuración de Intune**|
|:-----|:-----|
|Eliminar archivos de trabajo de un dispositivo inactivo después de  |Intervalo sin conexión (días) antes de que se realice el borrado de datos de la aplicación  |
|Forzar el almacenamiento por parte de los usuarios de los archivos de trabajo en OneDrive para la Empresa  <br/> Tenga en cuenta que solo está permitido OneDrive para la Empresa  |Seleccione qué datos corporativos de servicios de almacenamiento se pueden guardar en  |
   
En **Administrar la forma en la que los usuarios obtienen acceso a los archivos de Office desde dispositivos móviles**
  
|**Configuración de directiva de aplicación Android o iOS**|**Configuración de Intune**|
|:-----|:-----|
|Eliminar archivos de trabajo de un dispositivo inactivo después de  |Intervalo sin conexión (días) antes de que se realice el borrado de datos de la aplicación  |
|Forzar el almacenamiento por parte de los usuarios de los archivos de trabajo en OneDrive para la Empresa  <br/> Tenga en cuenta que solo está permitido OneDrive para la Empresa  |Seleccione qué datos corporativos de servicios de almacenamiento se pueden guardar en  |
|Cifrar los archivos de trabajo  |Cifrar los datos de la aplicación  |
|En **Administrar la forma en la que los usuarios obtienen acceso a los archivos de Office desde dispositivos móviles** ||
|Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office  | Requiere un PIN para acceder  <br/>  Esto también establece:  <br/> **Permitir PIN simple** en **Sí** <br/> **Longitud del pin** en 4  <br/> **Permitir la firma digital en lugar de PIN** en **Sí** <br/> **Deshabilitar el PIN de aplicación cuando se administra el PIN del dispositivo** en **No** |
|Restablecer el PIN cuando no se pueda iniciar sesión este número de veces (esta opción está deshabilitada si el PIN no es necesario)  |Número de intentos antes de restablecimiento del PIN  |
|Requerir que los usuarios inicien sesión de nuevo si las aplicaciones de Office han estado inactivas durante (esta opción está deshabilitada si el PIN no es necesario)  | Volver a revisar los requisitos de acceso después (minutos)  <br/>  Esto también establece:  <br/> **El tiempo de espera** se establece en minutos  <br/>  Este es el mismo número de minutos que estableció en Microsoft 365 Business.  <br/> **El período de gracia sin conexión** se establece en 720 minutos de forma predeterminada  |
|Denegar el acceso a los archivos de trabajo en dispositivos con jailbreak o rooting  |Bloquear la ejecución de aplicaciones administradas en dispositivos con Jailbreak o rooting  |
|Permitir a los usuarios copiar contenido de aplicaciones de Office en aplicaciones personales  | Restringir cortar, copiar y pegar con otras aplicaciones  <br/>  Si la opción Microsoft 365 Empresa Premium se establece en **Activada**, a continuación, estas tres opciones también se establecen en **Todas las aplicaciones** en Intune:  <br/> **Permitir a la aplicación transferir datos a otras aplicaciones** <br/> **Permitir a la aplicación recibir datos de otras aplicaciones** <br/> **Restringir cortar, copiar y pegar con otras aplicaciones** <br/>  Si la opción Microsoft 365 Business se establece en **Activar**, a continuación, todas las opciones de Intune se establecen en:  <br/> **Permitir a la aplicación transferir datos a otras aplicaciones** se establece en **Aplicaciones administradas de la directiva** <br/> **Permitir a la aplicación recibir datos de otras aplicaciones** se establece en **Todas las aplicaciones** <br/> **Restringir cortar, copiar y pegar con otras aplicaciones** se establece en **Aplicaciones administradas de la directiva con pegado en** |
   
## <a name="windows-10-app-protection-settings"></a>Configuración de protección de la aplicación de Windows 10

La siguiente tabla detalla cómo se asigna a la configuración de Intune la configuración de directiva de aplicaciones de Windows 10.
  
To find the Intune setting, sign in with your Microsoft 365 Business Premium admin credentials, and go to [Azure portal](https://portal.azure.com). Select **More services**, and type Intune into the **Filter**. Select **Intune App Protection** \> **App Policy**.
  
 > [!IMPORTANT]
 > La suscripción de Microsoft 365 Empresa Premium le proporciona una licencia para modificar solo la configuración de Intune que se asigna a la configuración disponible en Microsoft 365 Empresa Premium. 
  
Haga clic en el nombre de la directiva que desea seleccionar y, a continuación, elija **General, asignaciones**, **Aplicaciones permitidas**, **Aplicaciones excluidas**, **Configuración necesaria** o **Configuración avanzada** en la barra de navegación izquierda. 
  
|**Configuración de directiva de aplicación de Windows 10**|**Configuración de Intune**|
|:-----|:-----|
|Cifrar los archivos de trabajo  |**Configuración avanzada** \> **Protección de datos**: **Revocar las claves de cifrado en la inscripción** y **Revocar acceso al dispositivo de datos protegidos inscrito a MDM** se establecen en **Activar**.  |
|Impedir que los usuarios copien datos de la empresa en archivos personales.  |**Required settings** \> **Windows Information Protection mode**. **On** in Microsoft 365 Business Premium maps to: **Hide Overrides**, **Off** in Microsoft 365 Business Premium maps to: **Off**.  |
|Control de acceso a documentos de Office  | Si se establece en **Activado** en Microsoft 365 Empresa Premium, entonces  <br/> **Configuración avanzada** \> **Acceso**, **Usar Windows Hello para empresas como método para iniciar sesión en Windows** se establece en **Activar**, con la siguiente configuración adicional:  <br/> **Establecer el número mínimo de caracteres necesarios para el PIN** se establece en **4**.  <br/> **Configurar el uso de mayúsculas en el PIN de Windows Hello para empresas** se establece en **No se permite el uso de mayúsculas para el PIN**.  <br/> **Configurar el uso de minúsculas en el PIN de Windows Hello para empresas** se establece en **No se permite el uso de minúsculas para el PIN**.  <br/> **Configurar el uso de caracteres especiales en el PIN de Windows Hello para empresas** se establece en **No se permite el uso de caracteres especiales para el PIN**.  <br/> **Especificar el período de tiempo (en días) que se puede usar el PIN antes de que el sistema necesite que el usuario lo cambie** se establece en **0**.  <br/> **Especificar el número de PIN anteriores que pueden estar asociados a una cuenta de usuario que no se puede volver a utilizar** se establece en **0**.  <br/> **Número de errores de autenticación permitidos antes de que el dispositivo se borre** se establece en el mismo que en Microsoft 365 Business (5 de forma predeterminada).  <br/> **Cantidad máxima de tiempo (en minutos) permitido después de que el dispositivo esté inactivo que hará que el dispositivo se bloquee con la contraseña o el PIN** se establece en el mismo que en Microsoft 365 Business.  |
|Habilitar la recuperación de datos protegidos  |**Configuración avanzada** \> **Protección de datos**: **Mostrar el icono de protección de datos de empresa** y **Usar Azure RMS para el trabajo en curso** se establecen en **Activar**.  |
|Proteger las ubicaciones de la empresa y de la nube adicionales  |**Configuración avanzada** \> **Dominios protegidos** y **Recursos en nube** muestran los sitios de SharePoint y los dominios.  |
|Los archivos que usan estas aplicaciones están protegidos  |La lista de aplicaciones protegidas aparece en **Aplicaciones permitidas**.  |
   
## <a name="windows-10-device-protection-settings"></a>Configuración de protección del dispositivo de Windows 10

La siguiente tabla detalla cómo se asigna a la configuración de Intune los valores de configuración del dispositivo de Windows 10.
  
To find the Intune setting, sign in with your Microsoft 365 Business Premium admin credentials, and go to [Azure portal](https://portal.azure.com), then select **More services**, and type in Intune into the **Filter**, select **Intune** \> **Device configuration** \> **Profiles**. Then select **Device policy for Windows 10** \> **Properties** \> **Settings**.
  
|**Configuración de la directiva de dispositivo de Windows 10**|**Configuración de Intune**|
|:-----|:-----|
|Ayudar a proteger los equipos frente a virus y otras amenazas mediante Antivirus de Microsoft Defender  |Permitir la supervisión en tiempo real = Activado  <br/> Permitir la protección de la nube = Activado  <br/> Solicitar a los usuarios el envío de ejemplos = Enviar ejemplos seguros automáticamente (envío automático de DCP predeterminada)  |
|Proteger los equipos PC de amenazas basadas en web en Microsoft Edge  |**SmartScreen** en **Configuración del Explorador de Edge** se establece en **Requerir**.  |
|Desactivar la pantalla del dispositivo cuando haya estado inactivo durante (minutos)  |Número máximo de minutos de inactividad hasta que se bloquea la pantalla (minutos)  |
|Permitir a los usuarios descargar aplicaciones desde la Microsoft Store  |Directiva URI personalizada  |
|Permitir a los usuarios acceder a Cortana  |**General** \> **Cortana** se establece como **bloqueado** en Intune cuando se establece en **desactivado** en Microsoft 365 Empresa Premium.  |
|Permitir a los usuarios recibir sugerencias de Windows y anuncios de Microsoft  |**Destacados de Windows**, todo bloqueado si está **desactivado** en Microsoft 365 Empresa Premium.  |
|Mantener actualizados automáticamente los dispositivos con Windows 10  | Esta configuración está en **Microsoft Intune** \> **Actualizaciones del servicio: Windows 10 anillos de actualización**, elija **Actualizar directiva para dispositivos Windows 10** y, a continuación, **Propiedades** \> **Configuración**.  <br/>  Cuando la configuración de Microsoft 365 Empresa Premium está establecida en **Activado**, se establecen todas las opciones siguientes:  <br/> La **rama de servicio** se establece en **CB** (CBB cuando se desactiva en Microsoft 365 Empresa Premium).  <br/> **Actualizaciones de productos de Microsoft** se establece en **Permitir**.  <br/> **Controladores de Windows** se establece en **Permitir**.  <br/> **Comportamiento de la actualización automática** se establece en **Instalar automáticamente en el momento de mantenimiento** con:  <br/> **El inicio fuera del horario laboral** se establece en **6 a.m.**.  <br/> **El final de las horas activas** se establece en **10 p.m.**.  <br/> **El período de aplazamiento de la actualización de calidad (días)** se establece en **0**.  <br/> **El período de aplazamiento de la actualización de características (días)** se establece en **0**.  <br/> **El modo de descarga de optimización de entrega** se establece en **HTTP combinado con el emparejamiento que se encuentra en la misma NAT**.  |

## <a name="see-also"></a>Vea también

[Procedimientos recomendados para proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md)
