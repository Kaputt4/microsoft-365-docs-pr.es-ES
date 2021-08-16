---
title: Revisar eventos y errores con el Visor de eventos
description: Obtenga descripciones y pasos de solución de problemas adicionales (si es necesario) para todos los eventos notificados por el servicio de Microsoft Defender para puntos de conexión.
keywords: troubleshoot, event viewer, log summary, failure code, failed, Microsoft Defender for Endpoint service, can't start, broken, can't start
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 05/21/2018
ms.technology: mde
ms.openlocfilehash: c92d53045c56adf300dc2d67c92f8e7c6b6333e6739a10f476461252321ca3bb
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53857620"
---
# <a name="review-events-and-errors-using-event-viewer"></a>Revisar eventos y errores con el Visor de eventos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- Visor de eventos
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)

Puedes revisar los IDs de eventos en el [Visor de eventos](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) en dispositivos individuales.

Por ejemplo, si los dispositivos no aparecen en la lista Dispositivos, es posible que deba buscar los ID de eventos en los dispositivos. A continuación, puede usar esta tabla para determinar los pasos de solución de problemas adicionales.

**Abra el Visor de eventos y busque el registro de eventos de servicio de Microsoft Defender para puntos de conexión:**

1. Haga **clic en** Inicio en Windows menú, escriba Visor de **eventos** y presione **Entrar**.

2. En la lista de registros, en **Resumen del registro,** desplácese hasta que vea **Microsoft-Windows-SENSE/Operational**. Haga doble clic en el elemento para abrir el registro.

   También puede obtener acceso al registro expandiendo **Registros** de aplicaciones y servicios  >  **microsoft**  >  **Windows**  >  **SENSE** y haga clic en **Operativo**.

   > [!NOTE]
   > SENSE es el nombre interno que se usa para hacer referencia al sensor de comportamiento que potencia Microsoft Defender para Endpoint.

3. Los eventos registrados por el servicio aparecerán en el registro. Vea la tabla siguiente para obtener una lista de eventos registrados por el servicio.

   <br>

   ****

   |Identificador de evento|Mensaje|Description|Action|
   |---|---|---|---|
   |1|Se inició el servicio de Microsoft Defender para puntos de conexión `variable` (versión).|Se produce durante el inicio, apagado y durante la incorporación del sistema.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |2|Cierre del servicio de Microsoft Defender para puntos de conexión.|Se produce cuando el dispositivo se apaga o se apaga.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |3|Microsoft Defender para el servicio de extremo no se pudo iniciar. Código de error: `variable` .|El servicio no se ha empezado.|Revise otros mensajes para determinar posibles causas y pasos de solución de problemas.|
   |4 |Microsoft Defender para el servicio de extremo se puso en contacto con el servidor en `variable` .|Variable = dirección URL de los servidores de procesamiento de Defender for Endpoint. <p> Esta dirección URL coincidirá con la que se ve en el Firewall o la actividad de red.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |5 |Microsoft Defender para el servicio de extremo no se pudo conectar al servidor en `variable` .|Variable = dirección URL de los servidores de procesamiento de Defender for Endpoint. <p> El servicio no pudo ponerse en contacto con los servidores de procesamiento externos en esa dirección URL.|Compruebe la conexión a la dirección URL. Consulte [Configure proxy and Internet connectivity](configure-proxy-internet.md).|
   |6 |El servicio de Microsoft Defender para puntos de conexión no está incorporado y no se encontraron parámetros de incorporación.|El dispositivo no se incorporó correctamente y no se va a informar al portal.|La incorporación debe ejecutarse antes de iniciar el servicio. <p> Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración. <p> Consulta [Incorporación Windows 10 dispositivos](configure-endpoints.md).|
   |7 |Microsoft Defender para el servicio de extremo no pudo leer los parámetros de incorporación. Error: `variable` .|Variable = descripción detallada del error. El dispositivo no se incorporó correctamente y no se va a informar al portal.|Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración. <p> Consulta [Incorporación Windows 10 dispositivos](configure-endpoints.md).|
   |8 |Microsoft Defender para el servicio de extremo no pudo limpiar su configuración. Código de error: `variable` .|**Durante la incorporación:** El servicio no pudo limpiar su configuración durante la incorporación. El proceso de incorporación continúa. <p> **Durante el offboarding:** El servicio no pudo limpiar su configuración durante el offboarding. El proceso de offboarding ha finalizado, pero el servicio sigue ejecutándose.|**Incorporación:** No se requiere ninguna acción. <p> **Offboarding:** Reinicie el sistema. <p> Consulta [Incorporación Windows 10 dispositivos](configure-endpoints.md).|
   |9 |Microsoft Defender para el servicio de extremo no pudo cambiar su tipo de inicio. Código de error: `variable` .|**Durante la incorporación:** El dispositivo no se incorporó correctamente y no se va a informar al portal. <p>**Durante el offboarding:** No se pudo cambiar el tipo de inicio del servicio. El proceso de offboarding continúa. |Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración. <p> Consulta [Incorporación Windows 10 dispositivos](configure-endpoints.md).|
   |10 |Microsoft Defender para el servicio de extremo no pudo conservar la información de incorporación. Código de error: `variable` .|El dispositivo no se incorporó correctamente y no se va a informar al portal.|Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración. <p> Consulta [Incorporación Windows 10 dispositivos](configure-endpoints.md).|
   |11|Se completó la incorporación o la incorporación de Defender para el servicio de extremo.|El dispositivo se incorporó correctamente.|Notificación de funcionamiento normal; no se requiere ninguna acción. <p> El dispositivo puede tardar varias horas en aparecer en el portal.|
   |12 |Microsoft Defender para endpoint no pudo aplicar la configuración predeterminada.|El servicio no pudo aplicar la configuración predeterminada.|Este error debe resolverse después de un breve período de tiempo.|
   |13|Microsoft Defender para el identificador de dispositivo de extremo calculado: `variable` .|Proceso operativo normal.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |15|Microsoft Defender para endpoint no puede iniciar el canal de comandos con dirección URL: `variable` .|Variable = dirección URL de los servidores de procesamiento de Defender for Endpoint. <p> El servicio no pudo ponerse en contacto con los servidores de procesamiento externos en esa dirección URL.|Compruebe la conexión a la dirección URL. Consulte [Configure proxy and Internet connectivity](configure-proxy-internet.md).|
   |17 |Microsoft Defender para el servicio de extremo no pudo cambiar la ubicación del servicio Telemetría y experiencias del usuario conectado. Código de error: `variable` .|Se produjo un error con el servicio Windows telemetría.|[Asegúrese de que el servicio de datos de](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)diagnóstico está habilitado ">asegúrese de que el servicio de datos de diagnóstico está habilitado. <p> Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración. <p> Consulta [Incorporación Windows 10 dispositivos](configure-endpoints.md).|
   |18 |OOBE (Windows bienvenida) se ha completado.|El servicio solo se iniciará después de que Windows actualizaciones haya terminado de instalarse.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |19|OOBE (Windows bienvenida) aún no se ha completado.|El servicio solo se iniciará después de que Windows actualizaciones haya terminado de instalarse.|Notificación de funcionamiento normal; no se requiere ninguna acción. <p> Si este error persiste después de reiniciar el sistema, asegúrese de que todas Windows actualizaciones se han instalado por completo.|
   |20|No se puede esperar a que se complete la OOBE (Windows welcome). Código de error: `variable` .|Error interno.|Si este error persiste después de reiniciar el sistema, asegúrese de que todas Windows actualizaciones se han instalado por completo.|
   |25|Microsoft Defender para el servicio de extremo no pudo restablecer el estado de mantenimiento en el Registro. Código de error: `variable` .|El dispositivo no se incorporó correctamente. Se presentará en el portal, pero es posible que el servicio no aparezca como registrado en SCCM o en el Registro.|Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración. <p> Consulta [Incorporación Windows 10 dispositivos](configure-endpoints.md).|
   |26|Microsoft Defender para el servicio de extremo no pudo establecer el estado de incorporación en el Registro. Código de error: `variable` .|El dispositivo no se incorporó correctamente. <p> Se presentará en el portal, pero es posible que el servicio no aparezca como registrado en SCCM o en el Registro.|Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración. <p> Consulta [Incorporación Windows 10 dispositivos](configure-endpoints.md).|
   |27|El servicio de Microsoft Defender para puntos de conexión no pudo habilitar el modo consciente de SENSE en Antivirus de Microsoft Defender. Error en el proceso de incorporación. Código de error: `variable` .|Normalmente, Antivirus de Microsoft Defender un estado pasivo especial si otro producto antimalware en tiempo real se ejecuta correctamente en el dispositivo y el dispositivo informa a Defender para endpoint.|Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración. <p> Consulta [Incorporación Windows 10 dispositivos](configure-endpoints.md). <p> Asegúrese de que la protección antimalware en tiempo real se está ejecutando correctamente.|
   |28|Error en el registro del servicio de telemetría y experiencias de usuario conectado de Microsoft Defender para puntos de conexión. Código de error: `variable` .|Se produjo un error con el servicio Windows telemetría.|[Asegúrese de que el servicio de datos de diagnóstico está habilitado.](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy) <p> Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración. <p> Consulta [Incorporación Windows 10 dispositivos](configure-endpoints.md).|
   |29|No se pudieron leer los parámetros de offboarding. Tipo de error: %1, Código de error: %2, Descripción: %3|Este evento se produce cuando el sistema&#39;leer los parámetros de offboarding.|Asegúrate de que el dispositivo tiene acceso a Internet y, a continuación, vuelve a ejecutar todo el proceso de offboarding. Asegúrese de que el paquete de offboarding no ha expirado.|
   |30|Microsoft Defender para el servicio de extremo no pudo deshabilitar el modo consciente de SENSE en Antivirus de Microsoft Defender. Código de error: `variable` .|Normalmente, Antivirus de Microsoft Defender un estado pasivo especial si otro producto antimalware en tiempo real se ejecuta correctamente en el dispositivo y el dispositivo informa a Defender para endpoint.|Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración. <p> Consulta [Incorporación Windows 10 dispositivos](configure-endpoints.md). <p> Asegúrese de que la protección antimalware en tiempo real se está ejecutando correctamente.|
   |31|Error en la anulación de la registro de Microsoft Defender para experiencias de usuario conectadas a puntos de conexión y servicio de telemetría. Código de error: `variable` .|Se produjo un error con el Windows de telemetría durante la incorporación. El proceso de offboarding continúa.|[Compruebe si hay errores con el servicio Windows telemetría](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled).|
   |32|Microsoft Defender para el servicio de extremo no pudo solicitar que se detuviera después del proceso de desaborde. Código de error: %1|Se produjo un error durante el offboarding.|Reinicie el dispositivo.|
   |33|Microsoft Defender para el servicio de extremo no pudo conservar EL GUID DE SENSE. Código de error: `variable` .|Se usa un identificador único para representar cada dispositivo que está informando al portal. <p> Si el identificador no persiste, es posible que el mismo dispositivo aparezca dos veces en el portal.|Compruebe los permisos del Registro en el dispositivo para asegurarse de que el servicio puede actualizar el Registro.|
   |34|Microsoft Defender para el servicio de extremo no pudo agregarse a sí mismo como dependencia del servicio de telemetría y experiencias del usuario conectado, lo que provocó un error en el proceso de incorporación. Código de error: `variable` .|Se produjo un error con el servicio Windows telemetría.|[Asegúrese de que el servicio de datos de diagnóstico está habilitado.](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy) <p> Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración. <p> Consulta [Incorporación Windows 10 dispositivos](configure-endpoints.md).|
   |35|Microsoft Defender para el servicio de extremo no pudo quitarse a sí mismo como dependencia del servicio telemetría y experiencias del usuario conectado. Código de error: `variable` .|Se produjo un error con el Windows de telemetría durante el offboarding. El proceso de offboarding continúa.|Compruebe si hay errores con el Windows de datos de diagnóstico.|
   |36|El registro del servicio de telemetría y experiencias de usuario conectado de Microsoft Defender para endpoints se ha correcto. Código de finalización: `variable` .|El registro de Defender para endpoint con el servicio de telemetría y experiencias del usuario conectado se completó correctamente.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |37|El módulo De punto de conexión A de Microsoft Defender está a punto de superar su cuota. Módulo: %1, Cuota: {%2} {%3}, Porcentaje de utilización de la cuota: %4.|El dispositivo casi ha usado su cuota asignada de la ventana actual de 24 horas. Está a punto de limitarse.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |38|La conexión de red se identifica como baja. Microsoft Defender para endpoint se pondrá en contacto con el servidor cada %1 minuto. Conexión medida: %2, Internet disponible: %3, red gratuita disponible: %4.|El dispositivo usa una red de pago y medición y se pondrá en contacto con el servidor con menos frecuencia.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |39|La conexión de red se identifica como normal. Microsoft Defender para endpoint se pondrá en contacto con el servidor cada %1 minuto. Conexión medida: %2, Internet disponible: %3, red gratuita disponible: %4.|El dispositivo no usa una conexión de pago o de medición y se pondrá en contacto con el servidor como de costumbre.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |40|El estado de la batería se identifica como bajo. Microsoft Defender para endpoint se pondrá en contacto con el servidor cada %1 minuto. Estado de la batería: %2.|El dispositivo tiene un nivel de batería bajo y se pondrá en contacto con el servidor con menos frecuencia.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |41|El estado de la batería se identifica como normal. Microsoft Defender para endpoint se pondrá en contacto con el servidor cada %1 minuto. Estado de la batería: %2.|El dispositivo no tiene bajo nivel de batería y se pondrá en contacto con el servidor como de costumbre.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |42|El componente de Microsoft Defender para extremo no pudo realizar la acción. Componente: %1, Acción: %2, Tipo de excepción: %3, Mensaje de excepción: %4|Error interno. No se pudo iniciar el servicio.|Si este error persiste, póngase en contacto con el soporte técnico.|
   |43|El componente de Microsoft Defender para extremo no pudo realizar la acción. Componente: %1, Acción: %2, Tipo de excepción: %3, Error de excepción: %4, Mensaje de excepción: %5|Error interno. No se pudo iniciar el servicio.|Si este error persiste, póngase en contacto con el soporte técnico.|
   |44|Offboarding of Defender for Endpoint service completed.|El servicio se ha desactivado.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |45|Error al registrar e iniciar la sesión de seguimiento de eventos [%1]. Código de error: %2|Se produjo un error al iniciar el servicio al crear la sesión etw. Esto provocó un error de inicio del servicio.|Si este error persiste, póngase en contacto con el soporte técnico.|
   |46|No se pudo registrar e iniciar la sesión de seguimiento de eventos [%1] debido a la falta de recursos. Código de error: %2. Esto es más probable porque hay demasiadas sesiones de seguimiento de eventos activos. El servicio reintentará en 1 minuto.|Se produjo un error al iniciar el servicio al crear una sesión de ETW debido a la falta de recursos. El servicio se inició y se está ejecutando, pero no informa de ningún evento de sensor hasta que se inicia la sesión etw.|Notificación de funcionamiento normal; no se requiere ninguna acción. El servicio intentará iniciar la sesión cada minuto.|
   |47|Se registró correctamente e inició la sesión de seguimiento de eventos, recuperada después de intentos fallidos anteriores.|Este evento sigue al evento anterior después de iniciar correctamente la sesión etw.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |48|No se pudo agregar un proveedor [%1] a la sesión de seguimiento de eventos [%2]. Código de error: %3. Esto significa que los eventos de este proveedor no se notifican.|No se pudo agregar un proveedor a la sesión de ETW. Como resultado, no se notifican los eventos del proveedor.|Compruebe el código de error. Si el error persiste, póngase en contacto con el soporte técnico.|
   |49|Comando de configuración de nube no válido recibido e ignorado. Versión: %1, estado: %2, código de error: %3, mensaje: %4|Se ha recibido un archivo de configuración no válido del servicio en la nube que se ha omitido.|Si este error persiste, póngase en contacto con el soporte técnico.|
   |50|Nueva configuración de nube aplicada correctamente. Versión: %1.|Se aplicó correctamente una nueva configuración desde el servicio en la nube.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |51|No se pudo aplicar la nueva configuración de nube, versión: %1. Se aplicó correctamente la última configuración correcta conocida, versión %2.|Se ha recibido un archivo de configuración mal del servicio en la nube. La última configuración correcta conocida se aplicó correctamente.|Si este error persiste, póngase en contacto con el soporte técnico.|
   |52|No se pudo aplicar la nueva configuración de nube, versión: %1. Tampoco se pudo aplicar la última configuración correcta conocida, versión %2. Se aplicó correctamente la configuración predeterminada.|Se ha recibido un archivo de configuración mal del servicio en la nube. No se pudo aplicar la última configuración buena conocida y se aplicó la configuración predeterminada.|El servicio intentará descargar un nuevo archivo de configuración en 5 minutos. Si no ve el evento #50: póngase en contacto con el soporte técnico.|
   |53|Configuración de nube cargada desde el almacenamiento persistente, versión: %1.|La configuración se cargó desde el almacenamiento persistente al iniciar el servicio.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |55|No se pudo crear el registrador automático de ETW seguro. Código de error: %1|No se pudo crear el registrador ETW seguro.|Reinicie el dispositivo. Si este error persiste, póngase en contacto con el soporte técnico.|
   |56|No se pudo quitar el registrador automático de ETW seguro. Código de error: %1|No se pudo quitar la sesión de ETW segura en el offboarding.|Póngase en contacto con el soporte técnico.|
   |57|Captura de una instantánea de la máquina para solucionar problemas.|Se está recopilando un paquete de investigación, también conocido como paquete forense.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |59|Comando inicio: %1|Iniciar la ejecución del comando de respuesta.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |60|Error al ejecutar el comando %1, error: %2.|Error al ejecutar el comando response.|Si este error persiste, póngase en contacto con el soporte técnico.|
   |61|Los parámetros de comando de la colección de datos no son válidos: SasUri: %1, compressionLevel: %2.|No se pudo leer ni analizar los argumentos del comando de colección de datos (argumentos no válidos).|Si este error persiste, póngase en contacto con el soporte técnico.|
   |62|No se pudo iniciar el servicio de telemetría y experiencias de usuario conectado. Código de error: %1|No se pudo iniciar el servicio de telemetría y experiencias de usuario conectados (diagtrack). La telemetría que no sea de Microsoft Defender para puntos de conexión no se enviará desde este equipo.|Busque más sugerencias de solución de problemas en el registro de eventos: Microsoft-Windows-UniversalTelemetryClient/Operational.|
   |63|Actualizar el tipo de inicio del servicio externo. Nombre: %1, tipo de inicio real: %2, tipo de inicio esperado: %3, código de salida: %4|Tipo de inicio actualizado del servicio externo.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |64|Inicio del servicio externo detenido. Nombre: %1, código de salida: %2|Iniciar un servicio externo.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |65|No se pudo cargar el controlador de minifiltro de componentes de eventos de seguridad de Microsoft. Código de error: %1|No se pudo cargar MsSecFlt.sys minifiltro del sistema de archivos.|Reinicie el dispositivo. Si este error persiste, póngase en contacto con el soporte técnico.|
   |66|Actualización de directivas: Modo de latencia - %1|Se actualizó C# de frecuencia de conexión C de C&C.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |68|El tipo de inicio del servicio es inesperado. Nombre del servicio: %1, tipo de inicio real: %2, tipo de inicio esperado: %3|Tipo de inicio de servicio externo inesperado.|Corregir el tipo de inicio del servicio externo.|
   |69|El servicio se detiene. Nombre del servicio: %1|Se detiene el servicio externo.|Inicie el servicio externo.|
   |70|Actualización de directivas: permitir la colección de muestras - %1|Se actualizó la directiva de colección de ejemplo.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |71|Se ha ejecutado correctamente el comando: %1|El comando se ejecutó correctamente.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |72|Se intentó enviar el primer informe de perfil completo del equipo. Código de resultado: %1|Solo informativo.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |73|Sense starting for platform: %1|Solo informativo.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |74|La etiqueta de dispositivo en el Registro supera el límite de longitud. Nombre de etiqueta: %2. Límite de longitud: %1.|La etiqueta de dispositivo supera el límite de longitud.|Usa una etiqueta de dispositivo más corta.|
   |81|No se pudo crear el registrador automático de ETW de Microsoft Defender para endpoint. Código de error: %1|No se pudo crear la sesión etw.|Reinicie el dispositivo. Si este error persiste, póngase en contacto con el soporte técnico.|
   |82|No se pudo quitar el registrador automático de ETW de Microsoft Defender para extremo. Código de error: %1|No se pudo eliminar la sesión etw.|Póngase en contacto con el soporte técnico.|
   |84|Establece Antivirus de Windows Defender modo de ejecución. Forzar el modo pasivo: %1, código de resultado: %2.|Establece el modo de ejecución del defensor (activo o pasivo).|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |85|No se pudo desencadenar el ejecutable de Microsoft Defender para endpoint. Código de error: %1|Error al ejecutar el archivo ejecutable SenseIR.|Reinicie el dispositivo. Si este error persiste, póngase en contacto con el soporte técnico.|
   |86|Al iniciar de nuevo se detuvo el servicio externo que debería estar en servicio. Nombre: %1, código de salida: %2|Iniciar el servicio externo de nuevo.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |87|No se puede iniciar el servicio externo. Nombre: %1|No se pudo iniciar el servicio externo.|Póngase en contacto con el soporte técnico.|
   |88|Actualizar el tipo de inicio del servicio externo de nuevo. Nombre: %1, tipo de inicio real: %2, tipo de inicio esperado: %3, código de salida: %4|Se actualizó el tipo de inicio del servicio externo.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |89|No se puede actualizar el tipo de inicio del servicio externo. Nombre: %1, tipo de inicio real: %2, tipo de inicio esperado: %3|No se puede actualizar el tipo de inicio del servicio externo.|Póngase en contacto con el soporte técnico.|
   |90|No se pudo configurar System Guard Runtime Monitor para conectarse al servicio en la nube en la región geográfica %1. Código de error: %2|System Guard Runtime Monitor no enviará datos de atestación al servicio en la nube.|Compruebe los permisos en la ruta de registro: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm". Si no se detecta ningún problema, póngase en contacto con el soporte técnico.|
   |91|No se pudo quitar la información de región geográfica del Monitor de tiempo de ejecución de System Guard. Código de error: %1|System Guard Runtime Monitor no enviará datos de atestación al servicio en la nube.|Compruebe los permisos en la ruta de registro: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm". Si no se detecta ningún problema, póngase en contacto con el soporte técnico.|
   |92|Detener el envío de la cuota de datos cibernéticos del sensor porque se supera la cuota de datos. Se reanudará el envío una vez que pase el período de cuota. Máscara de estado: %1|Supere el límite de limitación.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |93|Reanudación del envío de datos cibernéticos del sensor. Máscara de estado: %1|Reanudar el envío de datos cibernéticos.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |94|Se ha iniciado el ejecutable de Microsoft Defender para endpoint|Se ha iniciado el archivo ejecutable senseCE.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |95|El ejecutable de Microsoft Defender para endpoint ha finalizado|El archivo ejecutable senseCE ha finalizado.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |96|Microsoft Defender para Endpoint Init ha llamado. Código de resultado: %2|El ejecutable senseCE ha llamado inicialización de MCE.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |97|Hay problemas de conectividad a la nube para el escenario DLP|Hay problemas de conectividad de red que afectan al flujo de clasificación dlp.|Compruebe la conectividad de red.|
   |98|Se ha restaurado la conectividad a la nube para el escenario DLP|La conectividad a la red se restauró y el flujo de clasificación dlp puede continuar.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |99|Sense ha encontrado el siguiente error al comunicarse con el servidor: (%1). Resultado: (%2)|Se ha producido un error de comunicación.|Compruebe los siguientes eventos en el registro de eventos para obtener más detalles.|
   |100|El ejecutable de Microsoft Defender para extremo no se pudo iniciar. Código de error: %1|El archivo ejecutable senseCE no se ha podido iniciar.|Reinicie el dispositivo. Si este error persiste, póngase en contacto con el soporte técnico.|
   |102|Se ha iniciado el ejecutable de Microsoft Defender para detección y respuesta de red de extremo|Se ha iniciado el archivo ejecutable SenseNdr.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |103|El ejecutable de Microsoft Defender para detección y respuesta de la red de extremo ha finalizado|El archivo ejecutable SenseNdr ha finalizado.|Notificación de funcionamiento normal; no se requiere ninguna acción.|
   |

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a>Temas relacionados

- [Incorporar dispositivos Windows 10 mediante la directiva de grupo](configure-endpoints.md)
- [Configurar las opciones de proxy de dispositivo y de conectividad a Internet](configure-proxy-internet.md)
- [Solucionar problemas de Microsoft Defender para punto de conexión](troubleshoot-onboarding.md)
