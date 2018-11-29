---
title: Cómo se asignan las características de protección de Microsoft 365 Business a la configuración de Intune
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 8/13/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: aad21b1a-c775-469a-b89c-c5d1d59d27db
description: Obtenga información sobre cómo se asignan características de protección de Microsoft 365 Business Intune configuración. La suscripción proporciona con una licencia para modificar la configuración de Intune.
ms.openlocfilehash: 5ee5a457fe3f265dd37f6806ca8c11fe096718b6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871429"
---
# <a name="how-do-protection-features-in-microsoft-365-business-map-to-intune-settings"></a>Cómo se asignan las características de protección de Microsoft 365 Business a la configuración de Intune

## <a name="android-and-ios-application-protection-settings"></a>Configuración de protección de aplicación Android o iOS

En la siguiente tabla, se detalla cómo se asigna a la configuración de Intune la configuración de directiva de aplicaciones de Android o iOS.
  
Para encontrar la configuración Intune, mientras que inicia sesión con sus credenciales de administrador empresarial de Microsoft 365, vaya a **centros de administración**y, a continuación, en **Intune**.
  
 **Importante:** Una suscripción de Microsoft 365 Business proporciona con una licencia para modificar todas las opciones de Intune. Vea [Introducción a Intune para empezar a.](https://docs.microsoft.com/intune/introduction-intune)
  
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
  
Para buscar el Intune configuración, mientras que inicia sesión con sus credenciales de administrador empresarial de Microsoft 365, vaya al [portal de Azure](https://portal.azure.com), a continuación, seleccione **más servicios**y el tipo en Intune en el **filtro**, seleccione **Protección de aplicación Intune** \> ** Directiva de aplicación**.
  
 **Importante**: La suscripción de Microsoft 365 Empresa le proporciona una licencia para modificar solo la configuración de Intune que se asigna a la configuración disponible en Microsoft 365 Empresa. 
  
Haga clic en el nombre de la directiva que desea seleccionar y, a continuación, elija **General, asignaciones**, **Aplicaciones permitidas**, **Excluir aplicaciones**, **Configuración obligatoria** o **Configuración avanzada** en la barra de navegación izquierda para explorar la configuración disponible. 
  
|**Configuración de directiva de aplicación de Windows 10**|**Configuración de Intune**|
|:-----|:-----|
|Cifrar los archivos de trabajo  <br/> |**Configuración avanzada** \> **Protección de datos**: **Revocar las claves de cifrado en la inscripción** y **Revocar acceso al dispositivo de datos protegidos inscrito a MDM** se establecen en **Activar**.  <br/> |
|Impedir que los usuarios copien los datos de la compañía a los archivos personales.  <br/> |**Configuración necesaria** \> **Modo de protección de la información de Windows**. **Activado** en Microsoft 365 Business se asigna a: **Ocultar reemplazo**, **Desactivar** en Microsoft 365 Business se asigna a: **Desactivar**.  <br/> |
|Control de acceso a documentos de Office  <br/> | Si se establece en **Activar** en Microsoft 365 Business, a continuación,  <br/> **Configuración avanzada** \> **Acceso**, **Usar Windows Hello para empresas como método para iniciar sesión en Windows** se establece en **Activar**, con la siguiente configuración adicional:  <br/> **Establecer el número mínimo de caracteres necesarios para el PIN** se establece en **4**.  <br/> **Configurar el uso de mayúsculas en el PIN de Windows Hello para empresas** se establece en **No se permite el uso de mayúsculas para el PIN**.  <br/> **Configurar el uso de minúsculas en el PIN de Windows Hello para empresas** se establece en **No se permite el uso de minúsculas para el PIN**.  <br/> **Configurar el uso de caracteres especiales en el PIN de Windows Hello para empresas** se establece en **No se permite el uso de caracteres especiales para el PIN**.  <br/> **Especificar el período de tiempo (en días) que puede se puede usar el PIN antes de que el sistema necesite que el usuario lo cambie** se establece en **0**.  <br/> **Especificar el número de PIN anteriores que pueden estar asociados a una cuenta de usuario que no se puede volver a utilizar** se establece en **0**.  <br/> **Número de errores de autenticación permitidos antes de que el dispositivo se borre** se establece en el mismo que en Microsoft 365 Business (5 de forma predeterminada).  <br/> **Cantidad máxima de tiempo (en minutos) permitido después de que el dispositivo esté inactivo que hará que el dispositivo se bloquee con la contraseña o el PIN** se establece en el mismo que en Microsoft 365 Business.  <br/> |
|Habilitar la recuperación de datos protegidos  <br/> |**Configuración avanzada** \> **Protección de datos**: **Mostrar el icono de protección de datos de empresa** y **Usar Azure RMS para el trabajo en curso** se establecen en **Activar**.  <br/> |
|Proteger las ubicaciones de la empresa y de la nube adicionales  <br/> |**Configuración avanzada** \> **Dominios protegidos** y **Recursos en nube** muestran los sitios de SharePoint y los dominios.  <br/> |
|Los archivos que usan estas aplicaciones están protegidos  <br/> |La lista de aplicaciones protegidas aparece en **Aplicaciones permitidas**.  <br/> |
|||
   
## <a name="windows-10-device-protection-settings"></a>Configuración de protección del dispositivo de Windows 10

La siguiente tabla detalla cómo se asigna a la configuración de Intune los valores de configuración del dispositivo de Windows 10.
  
Para buscar el Intune configuración, mientras que inicia sesión con sus credenciales de administrador empresarial de Microsoft 365, vaya al [portal de Azure](https://portal.azure.com), a continuación, seleccione **más servicios**y el tipo en Intune en el **filtro**, seleccionan **Intune** \> **dispositivo configuración de** \> **perfiles**. A continuación, seleccione **Directiva de dispositivo para Windows 10** \> **Propiedades** \> **configuración**.
  
|**Configuración de la directiva del dispositivo de Windows 10**|**Configuración de Intune**|
|:-----|:-----|
|Ayudar a proteger los equipos PC de los virus y otras amenazas con Antivirus de Windows Defender  <br/> |Permitir la supervisión en tiempo real = Activado  <br/> Permitir la protección de la nube = Activado  <br/> Solicitar a los usuarios el envío de ejemplos = Enviar ejemplos seguros automáticamente (envío automático de DCP predeterminada)  <br/> |
|Ayudar a proteger los equipos PC de amenazas basadas en web en Microsoft Edge  <br/> |**SmartScreen** en **Configuración del Explorador de Edge** se establece en **Requerir**.  <br/> |
|Desactivar la pantalla del dispositivo cuando haya estado inactivo durante (minutos)  <br/> |Número máximo de minutos de inactividad hasta que se bloquea la pantalla (minutos)  <br/> |
|Permitir a los usuarios descargar aplicaciones desde la Microsoft Store  <br/> |Directiva URI personalizada  <br/> |
|Permitir a los usuarios acceder a Cortana  <br/> |**General** \> **Cortana** se establece en **Bloquear** en Intune cuando se establece en **Desactivar** en Microsoft 365 Business.  <br/> |
|Permitir a los usuarios recibir sugerencias de Windows y anuncios de Microsoft  <br/> |**Noticias destacadas de Windows**, todo se bloquea si se establece en **Desactivar** en Microsoft 365 Business.  <br/> |
|Mantener actualizados automáticamente los dispositivos con Windows 10  <br/> | Esta configuración está en **Microsoft Intune** \> **Actualizaciones de servicio - Anillos de actualización de Windows 10**, elija **Actualizar la directiva para los dispositivos Windows 10** y, a continuación, **Propiedades** \> **Configuración**.  <br/>  Cuando la configuración de Microsoft 365 Business está establecida en **Activar**, la configuración siguiente está establecida:  <br/> **La rama de servicio** se establece en **CB** (CBB cuando este está desactivado en Microsoft 365 Business).  <br/> **Actualizaciones de productos de Microsoft** se establece en **Permitir**.  <br/> **Controladores de Windows** se establece en **Permitir**.  <br/> **Comportamiento de la actualización automática** se establece en **Instalar automáticamente en el momento de mantenimiento** con:  <br/> **El inicio fuera del horario laboral** se establece en **6 a.m.**.  <br/> **El final de las horas activas** se establece en **10 p.m.**.  <br/> **El período de aplazamiento de la actualización de calidad (días)** se establece en **0**.  <br/> **El período de aplazamiento de la actualización de características (días)** se establece en **0**.  <br/> **El modo de descarga de optimización de entrega** se establece en **HTTP combinado con el emparejamiento que se encuentra en la misma NAT**.  <br/> |
|||
   

