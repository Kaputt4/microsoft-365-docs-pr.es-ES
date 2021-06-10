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
ms.openlocfilehash: a8b7268e89470a85a34015967b69abb1818fe64f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933846"
---
# <a name="review-events-and-errors-using-event-viewer"></a>Revisar eventos y errores con el Visor de eventos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- Visor de eventos
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

Puedes revisar los IDs de eventos en el [Visor de eventos](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) en dispositivos individuales.

Por ejemplo, si los dispositivos no aparecen en la lista Dispositivos, es posible que deba buscar los ID de eventos en los dispositivos. A continuación, puede usar esta tabla para determinar los pasos de solución de problemas adicionales.

**Abra el Visor de eventos y busque el registro de eventos de servicio de Microsoft Defender para puntos de conexión:**

1. Haga **clic en** Inicio en Windows menú, escriba Visor de **eventos** y presione **Entrar**.

2. En la lista de registros, en **Resumen del registro,** desplácese hasta que vea **Microsoft-Windows-SENSE/Operational**. Haga doble clic en el elemento para abrir el registro.

   a.  También puede obtener acceso al registro expandiendo **Registros** de aplicaciones y servicios  >  **microsoft**  >  **Windows**  >  **SENSE** y haga clic en **Operativo**.

   > [!NOTE]
   > SENSE es el nombre interno que se usa para hacer referencia al sensor de comportamiento que potencia Microsoft Defender para Endpoint.

3. Los eventos registrados por el servicio aparecerán en el registro. Vea la tabla siguiente para obtener una lista de eventos registrados por el servicio.

<table>
<tbody style="vertical-align:top;">
<tr>
<th>Identificador de evento</th>
<th>Mensaje</th>
<th>Descripción</th>
<th>Acción</th>
</tr>
<tr>
<td>1</td>
<td>Se inició el servicio de Microsoft Defender para puntos de conexión <code>variable</code> (versión).</td>
<td>Se produce durante el inicio, apagado y durante la incorporación del sistema.</td>
<td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
<td>2</td>
<td>Cierre del servicio de Microsoft Defender para puntos de conexión.</td>
<td>Se produce cuando el dispositivo se apaga o se apaga.</td>
<td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
<td>3</td>
<td>Microsoft Defender para el servicio de extremo no se pudo iniciar. Código de error: <code>variable</code> .</td>
<td>El servicio no se ha empezado.</td>
<td>Revise otros mensajes para determinar posibles causas y pasos de solución de problemas.</td>
</tr>
<tr>
<td>4 </td>
<td>Microsoft Defender para el servicio de extremo se puso en contacto con el servidor en <code>variable</code> .</td>
<td>Variable = dirección URL de los servidores de procesamiento de Defender for Endpoint.<br>
Esta dirección URL coincidirá con la que se ve en el Firewall o la actividad de red.</td>
<td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
<td>5 </td>
<td>Microsoft Defender para el servicio de extremo no se pudo conectar al servidor en <code>variable</code> .</td>
<td>Variable = dirección URL de los servidores de procesamiento de Defender for Endpoint.<br>
El servicio no pudo ponerse en contacto con los servidores de procesamiento externos en esa dirección URL.</td>
<td>Compruebe la conexión a la dirección URL. Consulte <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</td>
</tr>
<tr>
<td>6 </td>
<td>El servicio de Microsoft Defender para puntos de conexión no está incorporado y no se encontraron parámetros de incorporación.</td>
<td>El dispositivo no se incorporó correctamente y no se va a informar al portal.</td>
<td>La incorporación debe ejecutarse antes de iniciar el servicio.<br>
Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración.<br>
Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación Windows 10 dispositivos</a>.</td>
</tr>
<tr>
<td>7 </td>
<td>Microsoft Defender para el servicio de extremo no pudo leer los parámetros de incorporación. Error: <code>variable</code> .</td>
<td>Variable = descripción detallada del error. El dispositivo no se incorporó correctamente y no se va a informar al portal.</td>
<td>Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración.<br>
Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación Windows 10 dispositivos</a>.</td>
</tr>
<tr>
<td>8 </td>
<td>Microsoft Defender para el servicio de extremo no pudo limpiar su configuración. Código de error: <code>variable</code> .</td>
<td><b>Durante la incorporación:</b> El servicio no pudo limpiar su configuración durante la incorporación. El proceso de incorporación continúa. <br><br> <b>Durante el offboarding:</b> El servicio no pudo limpiar su configuración durante el offboarding. El proceso de offboarding ha finalizado, pero el servicio sigue ejecutándose.
 </td>
<td><b>Incorporación:</b> No se requiere ninguna acción. <br><br> <b>Offboarding:</b> Reinicie el sistema.<br>
Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación Windows 10 dispositivos</a>.</td>
</tr>
<tr>
<td>9 </td>
<td>Microsoft Defender para el servicio de extremo no pudo cambiar su tipo de inicio. Código de error: <code>variable</code> .</td>
<td><b>Durante la incorporación:</b> El dispositivo no se incorporó correctamente y no se va a informar al portal. <br><br><b>Durante el offboarding:</b> No se pudo cambiar el tipo de inicio del servicio. El proceso de offboarding continúa. </td>
<td>Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración.<br>
Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación Windows 10 dispositivos</a>.</td>
</tr>
<tr>
<td>10</td>
<td>Microsoft Defender para el servicio de extremo no pudo conservar la información de incorporación. Código de error: <code>variable</code> .</td>
<td>El dispositivo no se incorporó correctamente y no se va a informar al portal.</td>
<td>Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración.<br>
Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación Windows 10 dispositivos</a>.</td>
</tr>
<tr>
<td>11</td>
<td>Se completó la incorporación o la incorporación de Defender para el servicio de extremo.</td>
<td>El dispositivo se incorporó correctamente.</td>
<td>Notificación de funcionamiento normal; no se requiere ninguna acción.<br>
El dispositivo puede tardar varias horas en aparecer en el portal.</td>
</tr>
<tr>
<td>12 </td>
<td>Microsoft Defender para endpoint no pudo aplicar la configuración predeterminada.</td>
<td>El servicio no pudo aplicar la configuración predeterminada.</td>
<td>Este error debe resolverse después de un breve período de tiempo.</td>
</tr>
<tr>
<td>13</td>
<td>Microsoft Defender para el identificador de dispositivo de extremo calculado: <code>variable</code> .</td>
<td>Proceso operativo normal.</td>
<td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
<td>15</td>
<td>Microsoft Defender para endpoint no puede iniciar el canal de comandos con dirección URL: <code>variable</code> .</td>
<td>Variable = dirección URL de los servidores de procesamiento de Defender for Endpoint.<br>
El servicio no pudo ponerse en contacto con los servidores de procesamiento externos en esa dirección URL.</td>
<td>Compruebe la conexión a la dirección URL. Consulte <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</td>
</tr>
<tr>
<td>17 </td>
<td>Microsoft Defender para el servicio de extremo no pudo cambiar la ubicación del servicio Telemetría y experiencias del usuario conectado. Código de error: <code>variable</code> .</td>
<td>Se produjo un error con el servicio Windows telemetría.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Asegúrese de que el servicio de datos de diagnóstico está habilitado.</a><br>
Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración.<br>
Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación Windows 10 dispositivos</a>.</td>
</tr>
<tr>
<td>18 </td>
<td>OOBE (Windows bienvenida) se ha completado.</td>
<td>El servicio solo se iniciará después de que Windows actualizaciones haya terminado de instalarse.</td>
<td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
<td>19</td>
<td>OOBE (Windows bienvenida) aún no se ha completado.</td>
<td>El servicio solo se iniciará después de que Windows actualizaciones haya terminado de instalarse.</td>
<td>Notificación de funcionamiento normal; no se requiere ninguna acción.<br>
Si este error persiste después de reiniciar el sistema, asegúrese de que todas Windows actualizaciones se han instalado por completo.</td>
</tr>
<tr>
<td>20</td>
<td>No se puede esperar a que se complete la OOBE (Windows welcome). Código de error: <code>variable</code> .</td>
<td>Error interno.</td>
<td>Si este error persiste después de reiniciar el sistema, asegúrese de que todas Windows actualizaciones se han instalado por completo.</td>
</tr>
<tr>
<td>25</td>
<td>Microsoft Defender para el servicio de extremo no pudo restablecer el estado de mantenimiento en el Registro. Código de error: <code>variable</code> .</td>
<td>El dispositivo no se incorporó correctamente.
Se presentará en el portal, pero es posible que el servicio no aparezca como registrado en SCCM o en el Registro.</td>
<td>Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración.<br>
Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación Windows 10 dispositivos</a>.</td>
</tr>
<tr>
<td>26</td>
<td>Microsoft Defender para el servicio de extremo no pudo establecer el estado de incorporación en el Registro. Código de error: <code>variable</code> .</td>
<td>El dispositivo no se incorporó correctamente.<br>
Se presentará en el portal, pero es posible que el servicio no aparezca como registrado en SCCM o en el Registro.</td>
<td>Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración.<br>
Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación Windows 10 dispositivos</a>.</td>
</tr>
<tr>
<td>27</td>
<td>El servicio de Microsoft Defender para puntos de conexión no pudo habilitar el modo consciente de SENSE en Antivirus de Microsoft Defender. Error en el proceso de incorporación. Código de error: <code>variable</code> .</td>
<td>Normalmente, Antivirus de Microsoft Defender un estado pasivo especial si otro producto antimalware en tiempo real se ejecuta correctamente en el dispositivo y el dispositivo informa a Defender para endpoint.</td>
<td>Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración.<br>
Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación Windows 10 dispositivos</a>.<br>
Asegúrese de que la protección antimalware en tiempo real se está ejecutando correctamente.</td>
</tr>
<tr>
<td>28</td>
<td>Error en el registro del servicio de telemetría y experiencias de usuario conectado de Microsoft Defender para puntos de conexión. Código de error: <code>variable</code> .</td>
<td>Se produjo un error con el servicio Windows telemetría.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Asegúrese de que el servicio de datos de diagnóstico está habilitado.</a><br>
Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración.<br>
Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación Windows 10 dispositivos</a>.</td>
</tr>
<tr>
<td>29</td>
<td>No se pudieron leer los parámetros de offboarding. Tipo de error: %1, Código de error: %2, Descripción: %3 </td>
<td>Este evento se produce cuando el sistema&#39;leer los parámetros de offboarding.</td>
<td>Asegúrate de que el dispositivo tiene acceso a Internet y, a continuación, vuelve a ejecutar todo el proceso de offboarding. Asegúrese de que el paquete de offboarding no ha expirado.</td>
</tr>
<tr>
<td>30</td>
<td>Microsoft Defender para el servicio de extremo no pudo deshabilitar el modo consciente de SENSE en Antivirus de Microsoft Defender. Código de error: <code>variable</code> .</td>
<td>Normalmente, Antivirus de Microsoft Defender un estado pasivo especial si otro producto antimalware en tiempo real se ejecuta correctamente en el dispositivo y el dispositivo informa a Defender para endpoint.</td>
<td>Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración.<br>
Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación Windows 10 dispositivos</a><br>
Asegúrese de que la protección antimalware en tiempo real se está ejecutando correctamente.</td>
</tr>
<tr>
<td>31</td>
<td>Error en la anulación de la registro de Microsoft Defender para experiencias de usuario conectadas a puntos de conexión y servicio de telemetría. Código de error: <code>variable</code> .</td>
<td>Se produjo un error con el Windows de telemetría durante la incorporación. El proceso de offboarding continúa.</td>
<td><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Compruebe si hay errores con el servicio Windows telemetría</a>.</td>
</tr>
<tr>
<td>32</td>
<td>Microsoft Defender para el servicio de extremo no pudo solicitar que se detuviera después del proceso de desaborde. Código de error: %1</td>
<td>Se produjo un error durante el offboarding.</td>
<td>Reinicie el dispositivo.</td>
</tr>
<tr>
<td>33</td>
<td>Microsoft Defender para el servicio de extremo no pudo conservar EL GUID DE SENSE. Código de error: <code>variable</code> .</td>
<td>Se usa un identificador único para representar cada dispositivo que está informando al portal.<br>
Si el identificador no persiste, es posible que el mismo dispositivo aparezca dos veces en el portal.</td>
<td>Compruebe los permisos del Registro en el dispositivo para asegurarse de que el servicio puede actualizar el Registro.</td>
</tr>
<tr>
<td>34</td>
<td>Microsoft Defender para el servicio de extremo no pudo agregarse a sí mismo como dependencia del servicio de telemetría y experiencias del usuario conectado, lo que provocó un error en el proceso de incorporación. Código de error: <code>variable</code> .</td>
<td>Se produjo un error con el servicio Windows telemetría.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Asegúrese de que el servicio de datos de diagnóstico está habilitado.</a><br>
Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración.<br>
Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación Windows 10 dispositivos</a>.</td>
</tr>
<tr>
<td>35</td>
<td>Microsoft Defender para el servicio de extremo no pudo quitarse a sí mismo como dependencia del servicio telemetría y experiencias del usuario conectado. Código de error: <code>variable</code> .</td>
<td>Se produjo un error con el Windows de telemetría durante el offboarding. El proceso de offboarding continúa.
</td>
<td>Compruebe si hay errores con el Windows de datos de diagnóstico.</td>
</tr>
<tr>
<td>36</td>
<td>El registro del servicio de telemetría y experiencias de usuario conectado de Microsoft Defender para endpoints se ha correcto. Código de finalización: <code>variable</code> .</td>
<td>El registro de Defender para endpoint con el servicio de telemetría y experiencias del usuario conectado se completó correctamente.</td>
<td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
<td>37</td>
<td>El módulo De punto de conexión A de Microsoft Defender está a punto de superar su cuota. Módulo: %1, Cuota: {%2} {%3}, Porcentaje de utilización de la cuota: %4.</td>
<td>El dispositivo casi ha usado su cuota asignada de la ventana actual de 24 horas. Está a punto de limitarse.</td>
<td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
<td>38</td>
<td>La conexión de red se identifica como baja. Microsoft Defender para endpoint se pondrá en contacto con el servidor cada %1 minuto. Conexión medida: %2, Internet disponible: %3, red gratuita disponible: %4.</td>
<td>El dispositivo usa una red de pago y medición y se pondrá en contacto con el servidor con menos frecuencia.</td>
<td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
<td>39</td>
<td>La conexión de red se identifica como normal. Microsoft Defender para endpoint se pondrá en contacto con el servidor cada %1 minuto. Conexión medida: %2, Internet disponible: %3, red gratuita disponible: %4.</td>
<td>El dispositivo no usa una conexión de pago o de medición y se pondrá en contacto con el servidor como de costumbre.</td>
<td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
<td>40</td>
<td>El estado de la batería se identifica como bajo. Microsoft Defender para endpoint se pondrá en contacto con el servidor cada %1 minuto. Estado de la batería: %2.</td>
<td>El dispositivo tiene un nivel de batería bajo y se pondrá en contacto con el servidor con menos frecuencia.</td>
<td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
<td>41</td>
<td>El estado de la batería se identifica como normal. Microsoft Defender para endpoint se pondrá en contacto con el servidor cada %1 minuto. Estado de la batería: %2.</td>
<td>El dispositivo no tiene bajo nivel de batería y se pondrá en contacto con el servidor como de costumbre.</td>
<td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
<td>42</td>
<td>El componente de Microsoft Defender para extremo no pudo realizar la acción. Componente: %1, Acción: %2, Tipo de excepción: %3, Mensaje de excepción: %4</td>
<td>Error interno. No se pudo iniciar el servicio.</td>
<td>Si este error persiste, póngase en contacto con el soporte técnico.</td>
</tr>
<tr>
<td>43</td>
<td>El componente de Microsoft Defender para extremo no pudo realizar la acción. Componente: %1, Acción: %2, Tipo de excepción: %3, Error de excepción: %4, Mensaje de excepción: %5</td>
<td>Error interno. No se pudo iniciar el servicio.</td>
<td>Si este error persiste, póngase en contacto con el soporte técnico.</td>
</tr>
<tr>
<td>44</td>
<td>Offboarding of Defender for Endpoint service completed.</td>
<td>El servicio se ha desactivado.</td>
<td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
<td>45</td>
<td>Error al registrar e iniciar la sesión de seguimiento de eventos [%1]. Código de error: %2</td>
<td>Se produjo un error al iniciar el servicio al crear la sesión etw. Esto provocó un error de inicio del servicio.</td>
<td>Si este error persiste, póngase en contacto con el soporte técnico.</td>
</tr>
<tr>
<td>46</td>
<td>No se pudo registrar e iniciar la sesión de seguimiento de eventos [%1] debido a la falta de recursos. Código de error: %2. Esto es más probable porque hay demasiadas sesiones de seguimiento de eventos activos. El servicio reintentará en 1 minuto.</td>
<td>Se produjo un error al iniciar el servicio al crear una sesión de ETW debido a la falta de recursos. El servicio se inició y se está ejecutando, pero no informa de ningún evento de sensor hasta que se inicia la sesión etw.</td>
<td>Notificación de funcionamiento normal; no se requiere ninguna acción. El servicio intentará iniciar la sesión cada minuto.</td>
</tr>
<tr>
<td>47</td>
<td>Se registró correctamente e inició la sesión de seguimiento de eventos, recuperada después de intentos fallidos anteriores.</td>
<td>Este evento sigue al evento anterior después de iniciar correctamente la sesión etw.</td>
<td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
<td>48</td>
<td>No se pudo agregar un proveedor [%1] a la sesión de seguimiento de eventos [%2]. Código de error: %3. Esto significa que los eventos de este proveedor no se notifican.</td>
<td>No se pudo agregar un proveedor a la sesión de ETW. Como resultado, no se notifican los eventos del proveedor.</td>
<td>Compruebe el código de error. Si el error persiste, póngase en contacto con el soporte técnico.</td>
</tr>
</tr>
<tr>
   <td>49</td>
   <td>Comando de configuración de nube no válido recibido e ignorado. Versión: %1, estado: %2, código de error: %3, mensaje: %4</td>
   <td>Se ha recibido un archivo de configuración no válido del servicio en la nube que se ha omitido.</td>
   <td>Si este error persiste, póngase en contacto con el soporte técnico.</td>
</tr>
<tr>
   <td>50</td>
   <td>Nueva configuración de nube aplicada correctamente. Versión: %1.</td>
   <td>Se aplicó correctamente una nueva configuración desde el servicio en la nube.</td>
   <td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
   <td>51</td>
   <td>No se pudo aplicar la nueva configuración de nube, versión: %1. Se aplicó correctamente la última configuración correcta conocida, versión %2.</td>
   <td>Se ha recibido un archivo de configuración mal del servicio en la nube. La última configuración correcta conocida se aplicó correctamente.</td>
   <td>Si este error persiste, póngase en contacto con el soporte técnico.</td>
</tr>
<tr>
   <td>52</td>
   <td>No se pudo aplicar la nueva configuración de nube, versión: %1. Tampoco se pudo aplicar la última configuración correcta conocida, versión %2. Se aplicó correctamente la configuración predeterminada.</td>
   <td>Se ha recibido un archivo de configuración mal del servicio en la nube. No se pudo aplicar la última configuración buena conocida y se aplicó la configuración predeterminada.</td>
   <td>El servicio intentará descargar un nuevo archivo de configuración en 5 minutos. Si no ve el evento #50: póngase en contacto con el soporte técnico.</td>
</tr>
<tr>
   <td>53</td>
   <td>Configuración de nube cargada desde el almacenamiento persistente, versión: %1.</td>
   <td>La configuración se cargó desde el almacenamiento persistente al iniciar el servicio.</td>
   <td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
   <td>55</td>
   <td>No se pudo crear el registrador automático de ETW seguro. Código de error: %1</td>
   <td>No se pudo crear el registrador ETW seguro.</td>
   <td>Reinicie el dispositivo. Si este error persiste, póngase en contacto con el soporte técnico.</td>
</tr>
<tr>
   <td>56</td>
   <td>No se pudo quitar el registrador automático de ETW seguro. Código de error: %1</td>
   <td>No se pudo quitar la sesión de ETW segura en el offboarding.</td>
   <td>Póngase en contacto con el soporte técnico.</td>
</tr>
<tr>
   <td>57</td>
   <td>Captura de una instantánea de la máquina para solucionar problemas.</td>
   <td>Se está recopilando un paquete de investigación, también conocido como paquete forense.</td>
   <td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
   <td>59</td>
   <td>Comando inicio: %1</td>
   <td>Iniciar la ejecución del comando de respuesta.</td>
   <td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
   <td>60</td>
   <td>Error al ejecutar el comando %1, error: %2.</td>
   <td>Error al ejecutar el comando response.</td>
   <td>Si este error persiste, póngase en contacto con el soporte técnico.</td>
</tr>
<tr>
   <td>61</td>
   <td>Los parámetros de comando de la colección de datos no son válidos: SasUri: %1, compressionLevel: %2.</td>
   <td>No se pudo leer ni analizar los argumentos del comando de colección de datos (argumentos no válidos).</td>
   <td>Si este error persiste, póngase en contacto con el soporte técnico.</td>
</tr>
<tr>
   <td>62</td>
   <td>No se pudo iniciar el servicio de telemetría y experiencias de usuario conectado. Código de error: %1</td>
   <td>No se pudo iniciar el servicio de telemetría y experiencias de usuario conectados (diagtrack). La telemetría que no sea de Microsoft Defender para puntos de conexión no se enviará desde este equipo.</td>
   <td>Busque más sugerencias de solución de problemas en el registro de eventos: Microsoft-Windows-UniversalTelemetryClient/Operational.</td>
</tr>
<tr>
   <td>63</td>
   <td>Actualizar el tipo de inicio del servicio externo. Nombre: %1, tipo de inicio real: %2, tipo de inicio esperado: %3, código de salida: %4</td>
   <td>Tipo de inicio actualizado del servicio externo.</td>
   <td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
   <td>64</td>
   <td>Inicio del servicio externo detenido. Nombre: %1, código de salida: %2</td>
   <td>Iniciar un servicio externo.</td>
   <td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
   <td>65</td>
   <td>No se pudo cargar el controlador de minifiltro de componentes de eventos de seguridad de Microsoft. Código de error: %1</td>
   <td>No se pudo cargar MsSecFlt.sys minifiltro del sistema de archivos.</td>
   <td>Reinicie el dispositivo. Si este error persiste, póngase en contacto con el soporte técnico.</td>
</tr>
<tr>
   <td>66</td>
   <td>Actualización de directivas: Modo de latencia - %1</td>
   <td>Se actualizó C# de frecuencia de conexión C de C&C.</td>
   <td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
   <td>68</td>
   <td>El tipo de inicio del servicio es inesperado. Nombre del servicio: %1, tipo de inicio real: %2, tipo de inicio esperado: %3</td>
   <td>Tipo de inicio de servicio externo inesperado.</td>
   <td>Corregir el tipo de inicio del servicio externo.</td>
</tr>
<tr>
   <td>69</td>
   <td>El servicio se detiene. Nombre del servicio: %1</td>
   <td>Se detiene el servicio externo.</td>
   <td>Inicie el servicio externo.</td>
</tr>
<tr>
   <td>70</td>
   <td>Actualización de directivas: permitir la colección de muestras - %1</td>
   <td>Se actualizó la directiva de colección de ejemplo.</td>
   <td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
   <td>71</td>
   <td>Se ha ejecutado correctamente el comando: %1</td>
   <td>El comando se ejecutó correctamente.</td>
   <td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
   <td>72</td>
   <td>Se intentó enviar el primer informe de perfil completo del equipo. Código de resultado: %1</td>
   <td>Solo informativo.</td>
   <td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
   <td>73</td>
   <td>Sense starting for platform: %1</td>
   <td>Solo informativo.</td>
   <td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
   <td>74</td>
   <td>La etiqueta de dispositivo en el Registro supera el límite de longitud. Nombre de etiqueta: %2. Límite de longitud: %1.</td>
   <td>La etiqueta de dispositivo supera el límite de longitud.</td>
   <td>Usa una etiqueta de dispositivo más corta.</td>
</tr>
<tr>
   <td>81</td>
   <td>No se pudo crear el registrador automático de ETW de Microsoft Defender para endpoint. Código de error: %1</td>
   <td>No se pudo crear la sesión etw.</td>
   <td>Reinicie el dispositivo. Si este error persiste, póngase en contacto con el soporte técnico.</td>
</tr>
<tr>
   <td>82</td>
   <td>No se pudo quitar el registrador automático de ETW de Microsoft Defender para extremo. Código de error: %1</td>
   <td>No se pudo eliminar la sesión etw.</td>
   <td>Póngase en contacto con el soporte técnico.</td>
</tr>
<tr>
   <td>84</td>
   <td>Establece Antivirus de Windows Defender modo de ejecución. Forzar el modo pasivo: %1, código de resultado: %2.</td>
   <td>Establece el modo de ejecución del defensor (activo o pasivo).</td>
   <td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
   <td>85</td>
   <td>No se pudo desencadenar el ejecutable de Microsoft Defender para endpoint. Código de error: %1</td>
   <td>Error al ejecutar el archivo ejecutable SenseIR.</td>
   <td>Reinicie el dispositivo. Si este error persiste, póngase en contacto con el soporte técnico.</td>
</tr>
<tr>
   <td>86</td>
   <td>Al iniciar de nuevo se detuvo el servicio externo que debería estar en servicio. Nombre: %1, código de salida: %2</td>
   <td>Iniciar el servicio externo de nuevo.</td>
   <td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
   <td>87</td>
   <td>No se puede iniciar el servicio externo. Nombre: %1</td>
   <td>No se pudo iniciar el servicio externo.</td>
   <td>Póngase en contacto con el soporte técnico.</td>
</tr>
<tr>
   <td>88</td>
   <td>Actualizar el tipo de inicio del servicio externo de nuevo. Nombre: %1, tipo de inicio real: %2, tipo de inicio esperado: %3, código de salida: %4</td>
   <td>Se actualizó el tipo de inicio del servicio externo.</td>
   <td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
   <td>89</td>
   <td>No se puede actualizar el tipo de inicio del servicio externo. Nombre: %1, tipo de inicio real: %2, tipo de inicio esperado: %3</td>
   <td>No se puede actualizar el tipo de inicio del servicio externo.</td>
   <td>Póngase en contacto con el soporte técnico.</td>
</tr>
<tr>
   <td>90</td>
   <td>No se pudo configurar System Guard Runtime Monitor para conectarse al servicio en la nube en la región geográfica %1. Código de error: %2</td>
   <td>System Guard Runtime Monitor no enviará datos de atestación al servicio en la nube.</td>
   <td>Compruebe los permisos en la ruta de registro: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm". Si no se detecta ningún problema, póngase en contacto con el soporte técnico.</td>
</tr>
<tr>
   <td>91</td>
   <td>No se pudo quitar la información de región geográfica del Monitor de tiempo de ejecución de System Guard. Código de error: %1</td>
   <td>System Guard Runtime Monitor no enviará datos de atestación al servicio en la nube.</td>
   <td>Compruebe los permisos en la ruta de registro: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm". Si no se detecta ningún problema, póngase en contacto con el soporte técnico.</td>
</tr>
<tr>
   <td>92</td>
   <td>Detener el envío de la cuota de datos cibernéticos del sensor porque se supera la cuota de datos. Se reanudará el envío una vez que pase el período de cuota. Máscara de estado: %1</td>
   <td>Supere el límite de limitación.</td>
   <td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
   <td>93</td>
   <td>Reanudación del envío de datos cibernéticos del sensor. Máscara de estado: %1</td>
   <td>Reanudar el envío de datos cibernéticos.</td>
   <td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
   <td>94</td>
   <td>Se ha iniciado el ejecutable de Microsoft Defender para endpoint</td>
   <td>Se ha iniciado el archivo ejecutable senseCE.</td>
   <td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
   <td>95</td>
   <td>El ejecutable de Microsoft Defender para endpoint ha finalizado</td>
   <td>El archivo ejecutable senseCE ha finalizado.</td>
   <td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
   <td>96</td>
   <td>Microsoft Defender para Endpoint Init ha llamado. Código de resultado: %2</td>
   <td>El ejecutable senseCE ha llamado inicialización de MCE.</td>
   <td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
   <td>97</td>
   <td>Hay problemas de conectividad a la nube para el escenario DLP</td>
   <td>Hay problemas de conectividad de red que afectan al flujo de clasificación dlp.</td>
   <td>Compruebe la conectividad de red.</td>
</tr>
<tr>
   <td>98</td>
   <td>Se ha restaurado la conectividad a la nube para el escenario DLP</td>
   <td>La conectividad a la red se restauró y el flujo de clasificación dlp puede continuar.</td>
   <td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
   <td>99</td>
   <td>Sense ha encontrado el siguiente error al comunicarse con el servidor: (%1). Resultado: (%2)</td>
   <td>Se ha producido un error de comunicación.</td>
   <td>Compruebe los siguientes eventos en el registro de eventos para obtener más detalles.</td>
</tr>
<tr>
   <td>100</td>
   <td>El ejecutable de Microsoft Defender para extremo no se pudo iniciar. Código de error: %1</td>
   <td>El archivo ejecutable senseCE no se ha podido iniciar.</td>
   <td>Reinicie el dispositivo. Si este error persiste, póngase en contacto con el soporte técnico.</td>
</tr>
<tr>
   <td>102</td>
   <td>Se ha iniciado el ejecutable de Microsoft Defender para detección y respuesta de red de extremo</td>
   <td>Se ha iniciado el archivo ejecutable SenseNdr.</td>
   <td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
   <td>103</td>
   <td>El ejecutable de Microsoft Defender para detección y respuesta de la red de extremo ha finalizado</td>
   <td>El archivo ejecutable SenseNdr ha finalizado.</td>
   <td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
</tbody>
</table>

>¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a>Temas relacionados
- [Incorporar dispositivos Windows 10 mediante la directiva de grupo](configure-endpoints.md)
- [Configurar las opciones de proxy de dispositivo y de conectividad a Internet](configure-proxy-internet.md)
- [Solucionar problemas de Microsoft Defender para punto de conexión](troubleshoot-onboarding.md)
