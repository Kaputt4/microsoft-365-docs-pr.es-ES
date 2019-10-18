---
title: Cómo se asignan las características de protección de Microsoft 365 Business a la configuración de Intune
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 8/13/2018
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: aad21b1a-c775-469a-b89c-c5d1d59d27db
description: Obtenga información sobre cómo se asignan las características de protección de Microsoft 365 Business Map a la configuración de Intune. La suscripción le proporciona una licencia para modificar la configuración de Intune.
ms.openlocfilehash: 2e26bffe289170eb17b07325ab8b57285eecee38
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575946"
---
# <a name="how-do-protection-features-in-microsoft-365-business-map-to-intune-settings"></a>Cómo se asignan las características de protección de Microsoft 365 Business a la configuración de Intune

## <a name="android-and-ios-application-protection-settings"></a>Configuración de protección de aplicación Android o iOS

En la siguiente tabla, se detalla cómo se asigna a la configuración de Intune la configuración de directiva de aplicaciones de Android o iOS.
  
Para buscar la configuración de Intune, mientras ha iniciado sesión con las credenciales de administrador de Microsoft 365 Business, vaya a **centros de administración**y, después, **Intune**.
  
 **Importante:** Una suscripción de Microsoft 365 Business le proporciona una licencia para modificar toda la configuración de Intune. Consulte [Introduction to Intune to Get Started.](https://docs.microsoft.com/intune/introduction-intune)
  
Haga clic en el nombre de la directiva que desea seleccionar, por ejemplo, la directiva de aplicación para Android y luego elija **Configuración de la directiva**.
  
En **Proteger los archivos de trabajo cuando los dispositivos se extravían por pérdida o robo**
  
|**Configuración de directiva de aplicación Android o iOS**|**Configuración de Intune**|
|:-----|:-----|
|Eliminar archivos de trabajo de un dispositivo inactivo después de  <br/> |Intervalo sin conexión (días) antes de que se realice el borrado de datos de la aplicación  <br/> |
|Forzar el almacenamiento por parte de los usuarios de los archivos de trabajo en OneDrive para la Empresa  <br/> Tenga en cuenta que solo está permitido OneDrive para la Empresa  <br/> |Seleccione qué datos corporativos de servicios de almacenamiento se pueden guardar en  <br/> |
|||
   
En **Administrar la forma en la que los usuarios obtienen acceso a los archivos de Office desde dispositivos móviles**
  
|**Configuración de directiva de aplicación Android o iOS**|**Configuración de Intune**|
|:-----|:-----|
|Eliminar archivos de trabajo de un dispositivo inactivo después de  <br/> |Intervalo sin conexión (días) antes de que se realice el borrado de datos de la aplicación  <br/> |
|Forzar el almacenamiento por parte de los usuarios de los archivos de trabajo en OneDrive para la Empresa  <br/> Tenga en cuenta que solo está permitido OneDrive para la Empresa  <br/> |Seleccione qué datos corporativos de servicios de almacenamiento se pueden guardar en  <br/> |
|Cifrar los archivos de trabajo  <br/> |Cifrar los datos de la aplicación  <br/> |
|En **Administrar la forma en la que los usuarios obtienen acceso a los archivos de Office desde dispositivos móviles** <br/> ||
|Requerir una huella digital o un PIN para obtener acceso a las aplicaciones de Office  <br/> | Requiere un PIN para acceder  <br/>  Esto también establece:  <br/> **Permitir PIN simple** en **Sí** <br/> **Longitud del pin** en 4  <br/> **Permitir la firma digital en lugar de PIN** en **Sí** <br/> **Deshabilitar el PIN de aplicación cuando se administra el PIN del dispositivo** en **No** <br/> |
|Restablecer el PIN cuando no se pueda iniciar sesión este número de veces (esta opción está deshabilitada si el PIN no es necesario)  <br/> |Número de intentos antes del restablecimiento del PIN  <br/> |
|Requerir que los usuarios inicien sesión de nuevo si las aplicaciones de Office han estado inactivas durante (esta opción está deshabilitada si el PIN no es necesario)  <br/> | Volver a revisar los requisitos de acceso después (minutos)  <br/>  Esto también establece:  <br/> **El tiempo de espera** se establece en minutos  <br/>  Este es el mismo número de minutos que estableció en Microsoft 365 Business.  <br/> **El período de gracia sin conexión** se establece en 720 minutos de forma predeterminada  <br/> |
|Denegar el acceso a los archivos de trabajo en dispositivos con jailbreak o rooting  <br/> |Bloquear la ejecución de aplicaciones administradas en dispositivos con Jailbreak o rooting  <br/> |
|Permitir a los usuarios copiar contenido de aplicaciones de Office en aplicaciones personales  <br/> | Restringir cortar, copiar y pegar con otras aplicaciones  <br/>  Si la opción Microsoft 365 Business se establece en **Activar**, a continuación, estas tres opciones también se establecen en **Todas las aplicaciones** en Intune:  <br/> **Permitir a la aplicación transferir datos a otras aplicaciones** <br/> **Permitir a la aplicación recibir datos de otras aplicaciones** <br/> **Restringir cortar, copiar y pegar con otras aplicaciones** <br/>  Si la opción Microsoft 365 Business se establece en **Activar**, a continuación, todas las opciones de Intune se establecen en:  <br/> **Permitir a la aplicación transferir datos a otras aplicaciones** se establece en **Aplicaciones administradas de la directiva** <br/> **Permitir a la aplicación recibir datos de otras aplicaciones** se establece en **Todas las aplicaciones** <br/> **Restringir cortar, copiar y pegar con otras aplicaciones** se establece en **Aplicaciones administradas de la directiva con pegado en** <br/> |
|||
   
## <a name="windows-10-app-protection-settings"></a>Configuración de protección de la aplicación de Windows 10

La siguiente tabla detalla cómo se asigna a la configuración de Intune la configuración de directiva de aplicaciones de Windows 10.
  
Para buscar la configuración de Intune, mientras inicia sesión con las credenciales de administrador de Microsoft 365 Business, vaya a [Azure portal](https://portal.azure.com), seleccione **más servicios**y escriba Intune en el **filtro**, seleccione **Intune App Protection** \> **. Directiva**de la aplicación.
  
 **Importante**: La suscripción de Microsoft 365 Empresa le proporciona una licencia para modificar solo la configuración de Intune que se asigna a la configuración disponible en Microsoft 365 Empresa. 
  
Haga clic en el nombre de la directiva que desea seleccionar y, a continuación, elija **General, asignaciones**, **Aplicaciones permitidas**, **Excluir aplicaciones**, **Configuración obligatoria** o **Configuración avanzada** en la barra de navegación izquierda para explorar la configuración disponible. 
  
|**Configuración de directiva de aplicación de Windows 10**|**Configuración de Intune**|
|:-----|:-----|
|Cifrar los archivos de trabajo  <br/> |**Configuración avanzada** \> **Protección de datos**: **Revocar las claves de cifrado en la inscripción** y **Revocar acceso al dispositivo de datos protegidos inscrito a MDM** se establecen en **Activar**.  <br/> |
|Impedir que los usuarios copien datos de la empresa en archivos personales.  <br/> |**Configuración necesaria** \> **Modo de protección de la información de Windows**. **Activado** en Microsoft 365 Business se asigna a: **Ocultar reemplazo**, **Desactivar** en Microsoft 365 Business se asigna a: **Desactivar**.  <br/> |
|Control de acceso a documentos de Office  <br/> | Si se establece en **Activar** en Microsoft 365 Business, a continuación,  <br/> **Configuración avanzada** \> **Acceso**, **Usar Windows Hello para empresas como método para iniciar sesión en Windows** se establece en **Activar**, con la siguiente configuración adicional:  <br/> **Establecer el número mínimo de caracteres necesarios para el PIN** se establece en **4**.  <br/> **Configurar el uso de mayúsculas en el PIN de Windows Hello para empresas** se establece en **No se permite el uso de mayúsculas para el PIN**.  <br/> **Configurar el uso de minúsculas en el PIN de Windows Hello para empresas** se establece en **No se permite el uso de minúsculas para el PIN**.  <br/> **Configurar el uso de caracteres especiales en el PIN de Windows Hello para empresas** se establece en **No se permite el uso de caracteres especiales para el PIN**.  <br/> **Especificar el período de tiempo (en días) que puede se puede usar el PIN antes de que el sistema necesite que el usuario lo cambie** se establece en **0**.  <br/> **Especificar el número de PIN anteriores que pueden estar asociados a una cuenta de usuario que no se puede volver a utilizar** se establece en **0**.  <br/> **Número de errores de autenticación permitidos antes de que el dispositivo se borre** se establece en el mismo que en Microsoft 365 Business (5 de forma predeterminada).  <br/> **Cantidad máxima de tiempo (en minutos) permitido después de que el dispositivo esté inactivo que hará que el dispositivo se bloquee con la contraseña o el PIN** se establece en el mismo que en Microsoft 365 Business.  <br/> |
|Habilitar la recuperación de datos protegidos  <br/> |**Configuración avanzada** \> **Protección de datos**: **Mostrar el icono de protección de datos de empresa** y **Usar Azure RMS para el trabajo en curso** se establecen en **Activar**.  <br/> |
|Proteger las ubicaciones de la empresa y de la nube adicionales  <br/> |**Configuración avanzada** \> **Dominios protegidos** y **Recursos en nube** muestran los sitios de SharePoint y los dominios.  <br/> |
|Los archivos que usan estas aplicaciones están protegidos  <br/> |La lista de aplicaciones protegidas aparece en **Aplicaciones permitidas**.  <br/> |
|||
   
## <a name="windows-10-device-protection-settings"></a>Configuración de protección del dispositivo de Windows 10

En la siguiente tabla se describe cómo se asignan las opciones de configuración de dispositivo de Windows 10 a la configuración de Intune.
  
Para buscar la configuración de Intune, mientras ha iniciado sesión con las credenciales de administrador de Microsoft 365 Business, vaya a [Azure portal](https://portal.azure.com), seleccione **más servicios**y escriba Intune en el **filtro**, seleccione dispositivo de **Intune** \> . ** ** \> **perfiles**de configuración. A continuación, seleccione **Directiva de dispositivo para** \> la **configuración**de **propiedades** \> de Windows 10.
  
|**Configuración de directiva de dispositivo de Windows 10**|**Configuración de Intune**|
|:-----|:-----|
|Proteger los equipos PC de virus y otras amenazas con el antivirus Windows Defender  <br/> |Permitir supervisión en tiempo real = activado  <br/> Permitir la protección de la nube = activado  <br/> Solicitar a los usuarios el envío de muestras de ejemplo = enviar muestras seguras automáticamente (envío automático sin PII predeterminado)  <br/> |
|Proteger los equipos PC de amenazas basadas en web en Microsoft Edge  <br/> |La **configuración del explorador** de **SmartScreen** en el servidor perimetral se establece en **obligatorio**.  <br/> |
|Apagar la pantalla del dispositivo cuando esté inactivo durante (minutos)  <br/> |Número máximo de minutos de inactividad hasta que se bloquee la pantalla (minutos)  <br/> |
|Permitir a los usuarios descargar aplicaciones desde la Microsoft Store  <br/> |Directiva de URI personalizada  <br/> |
|Permitir a los usuarios acceder a Cortana  <br/> |**General** \> **Cortana** está configurada para **bloquearse** en Intune cuando se establece en **OFF** en Microsoft 365 Business.  <br/> |
|Permitir a los usuarios recibir sugerencias de Windows y anuncios de Microsoft  <br/> |**Contenido destacado de Windows**, todos los bloqueados si está establecido en **desactivado** en Microsoft 365 Business.  <br/> |
|Mantener actualizados automáticamente los dispositivos con Windows 10  <br/> | Esta configuración está en actualizaciones de servicio de **Microsoft Intune** \> **-anillos de actualización de Windows 10**, elija U **ctualizar Directiva para dispositivos con Windows 10**y, a continuación, **configuración**de **propiedades** \> .  <br/>  Cuando la configuración de Microsoft 365 Business se establece en **activado**, se establecen todas las opciones de configuración siguientes:  <br/> La **rama de servicio** se establece en **CB** (CBB cuando está desactivada en Microsoft 365 Business).  <br/> **Las actualizaciones de productos de Microsoft** están configuradas para **permitir**.  <br/> **Controladores de Windows** se establece en **permitir**.  <br/> El comportamiento de la **actualización automática** se establece en la **instalación automática durante el mantenimiento** con:  <br/> El **Inicio de horas después del horario** se establece en **6 a.m.**  <br/> El fin de las **horas activas** se establece en **10 PM**.  <br/> El período de aplazamiento de la **actualización de calidad (días)** se establece en **0**.  <br/> El período de aplazamiento de la **actualización de características (días)** se establece en **0**.  <br/> El **modo de descarga de optimización de entrega** se establece en **http combinado con el emparejamiento detrás del mismo NAT**.  <br/> |
|||
   

