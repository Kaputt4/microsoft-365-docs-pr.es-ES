---
title: Cómo se asignan las características de protección Microsoft 365 Empresa Premium a la configuración de Intune
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
ms.date: 02/27/2022
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: aad21b1a-c775-469a-b89c-c5d1d59d27db
description: Obtenga información sobre cómo las características de protección Microsoft 365 Empresa Premium se asignan a la configuración de Intune. La suscripción le proporciona una licencia para modificar la configuración de Intune.
ms.openlocfilehash: 33dfb7b53e048f258c1974ced046deaad41f5ce2
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63313767"
---
# <a name="how-do-protection-features-in-microsoft-365-business-premium-map-to-intune-settings"></a>Cómo se asignan las características de protección Microsoft 365 Empresa Premium a la configuración de Intune

> [!NOTE]
> Microsoft Defender para empresas se está implementando para Microsoft 365 Empresa Premium clientes, a partir del 1 de marzo de 2022. Esta oferta proporciona características de seguridad adicionales para dispositivos. [Obtenga más información sobre Defender para empresas](../../security/defender-business/mdb-overview.md).

## <a name="android-and-ios-application-protection-settings"></a>Configuración de protección de aplicación Android o iOS

En la siguiente tabla, se detalla cómo se asigna a la configuración de Intune la configuración de directiva de aplicaciones de Android o iOS.
  
Para buscar la configuración de Intune, inicie sesión con sus Microsoft 365 Empresa Premium de administrador y vaya a Centros de **administración** y, a continuación, **Intune**.
  
 > [!IMPORTANT]
 > 
 > Una Microsoft 365 Empresa Premium suscripción le da una licencia para modificar toda la configuración de Intune. Consulta [Introducción a Intune para empezar.](/intune/introduction-intune)
  
Seleccione el nombre de directiva que desee, &mdash; por ejemplo, Directiva de aplicación para Android &mdash; y, a continuación, elija **Configuración de directiva**.
  
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
|Restablecer el PIN cuando se produce un error de inicio de sesión muchas veces (esto está deshabilitado si el PIN no es necesario)  <br/> |Número de intentos antes de restablecimiento del PIN  <br/> |
|Requerir a los usuarios que inicien sesión de nuevo después Office que las aplicaciones hayan estado inactivas (esto está deshabilitado si el PIN no es necesario)  <br/> | Volver a revisar los requisitos de acceso después (minutos)  <br/>  Esto también establece:  <br/> **El tiempo de espera** se establece en minutos  <br/>  Este es el mismo número de minutos que estableció en Microsoft 365 Business.  <br/> **El período de gracia sin conexión** se establece en 720 minutos de forma predeterminada  <br/> |
|Denegar el acceso a los archivos de trabajo en dispositivos con jailbreak o rooting  <br/> |Bloquear la ejecución de aplicaciones administradas en dispositivos con Jailbreak o rooting  <br/> |
|Permitir a los usuarios copiar contenido de aplicaciones de Office en aplicaciones personales  <br/> | Restringir cortar, copiar y pegar con otras aplicaciones  <br/>  Si la Microsoft 365 Empresa Premium está establecida en **On**, estas tres opciones también se establecen en **Todas las aplicaciones** en Intune:  <br/> **Permitir a la aplicación transferir datos a otras aplicaciones** <br/> **Permitir a la aplicación recibir datos de otras aplicaciones** <br/> **Restringir cortar, copiar y pegar con otras aplicaciones** <br/>  Si la opción Microsoft 365 Business se establece en **Activar**, a continuación, todas las opciones de Intune se establecen en:  <br/> **Permitir a la aplicación transferir datos a otras aplicaciones** se establece en **Aplicaciones administradas de la directiva** <br/> **Permitir a la aplicación recibir datos de otras aplicaciones** se establece en **Todas las aplicaciones** <br/> **Restringir cortar, copiar y pegar con otras aplicaciones** se establece en **Aplicaciones administradas de la directiva con pegado en** <br/> |
|||
   
## <a name="windows-10-app-protection-settings"></a>Configuración de protección de la aplicación de Windows 10

La siguiente tabla detalla cómo se asigna a la configuración de Intune la configuración de directiva de aplicaciones de Windows 10.
  
Para buscar la configuración de Intune, inicie sesión con las Microsoft 365 Empresa Premium de administrador y vaya a [Azure Portal](https://portal.azure.com). Selecciona **Más servicios y** escribe Intune en el **filtro**. Selecciona **Directiva de aplicación de Intune App Protection**\>.
  
 > [!IMPORTANT]
 >
 >Una Microsoft 365 Empresa Premium suscripción le da una licencia para modificar solo la configuración de Intune que se asigna a la configuración disponible en Microsoft 365 Empresa Premium. 
  
Para explorar la configuración disponible, seleccione el nombre de directiva que desee y, a continuación, elija **General, Asignaciones****, Aplicaciones** permitidas **, Aplicaciones** exentas **, Configuración** requerida o Configuración avanzada en el panel de navegación izquierdo. 
  
|**Configuración de directiva de aplicación de Windows 10**|**Configuración de Intune**|
|:-----|:-----|
|Cifrar los archivos de trabajo  <br/> |**Configuración avanzada** \> **Protección de datos**: **Revocar las claves de cifrado en la inscripción** y **Revocar acceso al dispositivo de datos protegidos inscrito a MDM** se establecen en **Activar**.  <br/> |
|Impedir que los usuarios copien datos de la empresa en archivos personales.  <br/> |**Configuración necesaria** \> **Modo de protección de la información de Windows**. **On** in Microsoft 365 Empresa Premium maps to: **Hide Overrides**, **Off** in Microsoft 365 Empresa Premium maps to: **Off**.  <br/> |
|Control de acceso a documentos de Office  <br/> | Si se establece en **On en Microsoft 365 Empresa Premium**, a continuación,  <br/> **Configuración avanzada** \> **Acceso**, **Usar Windows Hello para empresas como método para iniciar sesión en Windows** se establece en **Activar**, con la siguiente configuración adicional:  <br/> **Establecer el número mínimo de caracteres necesarios para el PIN** se establece en **4**.  <br/> **Configurar el uso de mayúsculas en el PIN de Windows Hello para empresas** se establece en **No se permite el uso de mayúsculas para el PIN**.  <br/> **Configurar el uso de minúsculas en el PIN de Windows Hello para empresas** se establece en **No se permite el uso de minúsculas para el PIN**.  <br/> **Configurar el uso de caracteres especiales en el PIN de Windows Hello para empresas** se establece en **No se permite el uso de caracteres especiales para el PIN**.  <br/> **Especifique el período de tiempo (en días)** que se puede usar un PIN antes de que el sistema requiera que el usuario cambie se establece en **0**.  <br/> **Especificar el número de PIN anteriores que pueden estar asociados a una cuenta de usuario que no se puede volver a utilizar** se establece en **0**.  <br/> **Número de errores de autenticación permitidos antes de que el dispositivo se borre** se establece en el mismo que en Microsoft 365 Business (5 de forma predeterminada).  <br/> **Cantidad máxima de tiempo (en minutos) permitido después de que el dispositivo esté inactivo que hará que el dispositivo se bloquee con la contraseña o el PIN** se establece en el mismo que en Microsoft 365 Business.  <br/> |
|Habilitar la recuperación de datos protegidos  <br/> |**Configuración avanzada** \> **Protección de datos**: **Mostrar el icono de protección de datos de empresa** y **Usar Azure RMS para el trabajo en curso** se establecen en **Activar**.  <br/> |
|Proteger las ubicaciones de la empresa y de la nube adicionales  <br/> |**Configuración avanzada** \> **Dominios protegidos** y **Recursos en nube** muestran los sitios de SharePoint y los dominios.  <br/> |
|Los archivos que usan estas aplicaciones están protegidos  <br/> |La lista de aplicaciones protegidas aparece en **Aplicaciones permitidas**.  <br/> |
|||
   
## <a name="windows-10-device-protection-settings"></a>Configuración de protección del dispositivo de Windows 10

En la tabla siguiente se detalla cómo se asignan las Windows 10 configuración del dispositivo a la configuración de Intune.
  
Para buscar la configuración de Intune, inicie sesión con sus credenciales de administrador de Microsoft 365 Empresa Premium y vaya a  [Azure Portal](https://portal.azure.com), seleccione Más servicios y escriba Intune en El **filtro, seleccione** Perfiles de configuración de dispositivo **de** **Intune** \> \>. A **continuación, selecciona Directiva de dispositivo Windows 10** \> **Propiedades Configuración**\>.
  
|**Windows 10 de directiva de dispositivo**|**Configuración de Intune**|
|:-----|:-----|
|Proteger los equipos PC de virus y otras amenazas con el antivirus Windows Defender  <br/> |Permitir supervisión en tiempo real = ON  <br/> Permitir protección en la nube = ON  <br/> Solicitar a los usuarios el envío de muestras = enviar Caja fuerte automáticamente (envío automático predeterminado no PII)  <br/> |
|Proteger los equipos PC de amenazas basadas en web en Microsoft Edge  <br/> |**SmartScreen en** **la configuración del Explorador perimetral** está **establecido en Obligatorio**.  <br/> |
|Desactivar la pantalla del dispositivo cuando esté inactivo durante (minutos)  <br/> |Minutos máximos de inactividad hasta que se bloquea la pantalla (minutos)  <br/> |
|Permitir a los usuarios descargar aplicaciones desde la Microsoft Store  <br/> |Directiva uri personalizada  <br/> |
|Permitir a los usuarios acceder a Cortana  <br/> |**General** \> **Cortana** se establece en **bloquear** en Intune cuando se establece en **desactivado** en Microsoft 365 Empresa Premium.  <br/> |
|Permitir a los usuarios recibir sugerencias de Windows y anuncios de Microsoft  <br/> |**Windows destacado**, todo bloqueado si se establece en **desactivado** en Microsoft 365 Empresa Premium.  <br/> |
|Mantener actualizados automáticamente los dispositivos con Windows 10  <br/> | Esta configuración se encuentra en **Microsoft Intune** \> **de servicio: Windows 10** anillos de actualización, elija Directiva de actualización para dispositivos Windows 10 **y, a** continuación, **Propiedades** \> **Configuración**.  <br/>  Cuando la Microsoft 365 Empresa Premium está establecida en **On**, se establecen todas las opciones siguientes:  <br/> **La rama** de servicio se establece en **CB** (CBB cuando está desactivada en Microsoft 365 Empresa Premium).  <br/> **Las actualizaciones de productos de Microsoft** se establecen en **Permitir**.  <br/> **Windows controladores está** establecido en **Permitir**.  <br/> **El comportamiento de actualización** automática se establece en **Instalación automática en tiempo de mantenimiento** con:  <br/> **El inicio después de las** horas se establece en **6 a. m**.  <br/> **El fin de las** horas activas se establece en **10 p. m**.  <br/> **El período de aplazamiento de actualización de calidad (días)** se establece en **0**.  <br/> **El período de aplazamiento de actualización de características (días)** se establece en **0**.  <br/> **El modo de descarga de optimización de** distribución se establece en **HTTP combinado con emparejamiento detrás del mismo NAT**.  <br/> |
|||

## <a name="see-also"></a>Consulte también

[Principales 10 formas de proteger Microsoft 365 para planes empresariales](../security-and-compliance/secure-your-business-data.md)