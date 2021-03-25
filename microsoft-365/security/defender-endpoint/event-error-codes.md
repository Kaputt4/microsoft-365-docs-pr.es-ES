---
title: Revisar eventos y errores con el Visor de eventos
description: Obtenga descripciones y pasos de solución de problemas adicionales (si es necesario) para todos los eventos notificados por el servicio de Microsoft Defender para puntos de conexión.
keywords: troubleshoot, event viewer, log summary, failure code, failed, Microsoft Defender for Endpoint service, cannot start, broken, can't start
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
ms.openlocfilehash: 98c0f790c228989b261b95f3b87cdc9d18e4fa76
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076619"
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

1. Haga **clic en** Inicio en el menú Windows, escriba Visor de **eventos** y presione **Entrar**.

2. En la lista de registros, en **Resumen del registro,** desplácese hasta que vea **Microsoft-Windows-SENSE/Operational**. Haga doble clic en el elemento para abrir el registro.

   a.  También puede acceder al registro expandiendo Registros de aplicaciones y servicios  >  **Microsoft**  >  **Windows**  >  **SENSE** y haga clic en **Operativo**.

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
<td>Se produce durante el inicio, apagado y durante el inicio del sistema.</td>
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
<td>El dispositivo no se ha incorporado correctamente y no se va a informar al portal.</td>
<td>La incorporación debe ejecutarse antes de iniciar el servicio.<br>
Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración.<br>
Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación de dispositivos Windows 10</a>.</td>
</tr>
<tr>
<td>7 </td>
<td>Microsoft Defender para el servicio de extremo no pudo leer los parámetros de incorporación. Error: <code>variable</code> .</td>
<td>Variable = descripción detallada del error. El dispositivo no se ha incorporado correctamente y no se va a informar al portal.</td>
<td>Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración.<br>
Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación de dispositivos Windows 10</a>.</td>
</tr>
<tr>
<td>8 </td>
<td>Microsoft Defender para el servicio de extremo no pudo limpiar su configuración. Código de error: <code>variable</code> .</td>
<td><b>Durante la incorporación:</b> El servicio no pudo limpiar su configuración durante la incorporación. El proceso de incorporación continúa. <br><br> <b>Durante el offboarding:</b> El servicio no pudo limpiar su configuración durante el offboarding. El proceso de offboarding ha finalizado, pero el servicio sigue ejecutándose.
 </td>
<td><b>Incorporación:</b> No se requiere ninguna acción. <br><br> <b>Offboarding:</b> Reinicie el sistema.<br>
Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación de dispositivos Windows 10</a>.</td>
</tr>
<tr>
<td>9 </td>
<td>Microsoft Defender para el servicio de extremo no pudo cambiar su tipo de inicio. Código de error: <code>variable</code> .</td>
<td><b>Durante la incorporación:</b> El dispositivo no se ha incorporado correctamente y no se va a informar al portal. <br><br><b>Durante el offboarding:</b> No se pudo cambiar el tipo de inicio del servicio. El proceso de offboarding continúa. </td>
<td>Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración.<br>
Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación de dispositivos Windows 10</a>.</td>
</tr>
<tr>
<td>10  </td>
<td>Microsoft Defender para el servicio de extremo no pudo conservar la información de incorporación. Código de error: <code>variable</code> .</td>
<td>El dispositivo no se ha incorporado correctamente y no se va a informar al portal.</td>
<td>Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración.<br>
Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación de dispositivos Windows 10</a>.</td>
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
<td>15 </td>
<td>Microsoft Defender para endpoint no puede iniciar el canal de comandos con dirección URL: <code>variable</code> .</td>
<td>Variable = dirección URL de los servidores de procesamiento de Defender for Endpoint.<br>
El servicio no pudo ponerse en contacto con los servidores de procesamiento externos en esa dirección URL.</td>
<td>Compruebe la conexión a la dirección URL. Consulte <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</td>
</tr>
<tr>
<td>17 </td>
<td>Microsoft Defender para el servicio de extremo no pudo cambiar la ubicación del servicio Telemetría y experiencias del usuario conectado. Código de error: <code>variable</code> .</td>
<td>Se produjo un error con el servicio de telemetría de Windows.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Asegúrese de que el servicio de datos de diagnóstico está habilitado.</a><br>
Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración.<br>
Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación de dispositivos Windows 10</a>.</td>
</tr>
<tr>
<td>18 </td>
<td>OOBE (Windows Welcome) se ha completado.</td>
<td>El servicio solo se iniciará después de que las actualizaciones de Windows terminen de instalarse.</td>
<td>Notificación de funcionamiento normal; no se requiere ninguna acción.</td>
</tr>
<tr>
<td>19</td>
<td>OOBE (Windows Welcome) aún no se ha completado.</td>
<td>El servicio solo se iniciará después de que las actualizaciones de Windows terminen de instalarse.</td>
<td>Notificación de funcionamiento normal; no se requiere ninguna acción.<br>
Si este error persiste después de reiniciar el sistema, asegúrate de que todas las actualizaciones de Windows se han instalado por completo.</td>
</tr>
<tr>
<td>20</td>
<td>No se puede esperar a que se complete OOBE (Windows Welcome). Código de error: <code>variable</code> .</td>
<td>Error interno.</td>
<td>Si este error persiste después de reiniciar el sistema, asegúrate de que todas las actualizaciones de Windows se han instalado por completo.</td>
</tr>
<tr>
<td>25</td>
<td>Microsoft Defender para el servicio de extremo no pudo restablecer el estado de mantenimiento en el Registro. Código de error: <code>variable</code> .</td>
<td>El dispositivo no se incorporó correctamente.
Se presentará en el portal, pero es posible que el servicio no aparezca como registrado en SCCM o en el Registro.</td>
<td>Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración.<br>
Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación de dispositivos Windows 10</a>.</td>
</tr>
<tr>
<td>26</td>
<td>Microsoft Defender para el servicio de extremo no pudo establecer el estado de incorporación en el Registro. Código de error: <code>variable</code> .</td>
<td>El dispositivo no se incorporó correctamente.<br>
Se presentará en el portal, pero es posible que el servicio no aparezca como registrado en SCCM o en el Registro.</td>
<td>Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración.<br>
Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación de dispositivos Windows 10</a>.</td>
</tr>
<tr>
<td>27</td>
<td>El servicio de Microsoft Defender para puntos de conexión no pudo habilitar el modo consciente de SENSE en El Antivirus de Microsoft Defender. Error en el proceso de incorporación. Código de error: <code>variable</code> .</td>
<td>Normalmente, Antivirus de Microsoft Defender entrará en un estado pasivo especial si otro producto antimalware en tiempo real se ejecuta correctamente en el dispositivo y el dispositivo informa a Defender para endpoint.</td>
<td>Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración.<br>
Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación de dispositivos Windows 10</a>.<br>
Asegúrese de que la protección antimalware en tiempo real se está ejecutando correctamente.</td>
</tr>
<tr>
<td>28</td>
<td>Error en el registro del servicio de telemetría y experiencias de usuario conectado de Microsoft Defender para puntos de conexión. Código de error: <code>variable</code> .</td>
<td>Se produjo un error con el servicio de telemetría de Windows.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Asegúrese de que el servicio de datos de diagnóstico está habilitado.</a><br>
Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración.<br>
Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación de dispositivos Windows 10</a>.</td>
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
<td>Normalmente, Antivirus de Microsoft Defender entrará en un estado pasivo especial si otro producto antimalware en tiempo real se ejecuta correctamente en el dispositivo y el dispositivo informa a Defender para endpoint.</td>
<td>Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración.<br>
Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación de dispositivos Windows 10</a><br>
Asegúrese de que la protección antimalware en tiempo real se está ejecutando correctamente.</td>
</tr>
<tr>
<td>31</td>
<td>Error en la anulación de la registro de Microsoft Defender para experiencias de usuario conectadas a puntos de conexión y servicio de telemetría. Código de error: <code>variable</code> .</td>
<td>Se produjo un error con el servicio de telemetría de Windows durante la incorporación. El proceso de offboarding continúa.</td>
<td><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Compruebe si hay errores con el servicio de telemetría de Windows</a>.</td>
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
<td>Se produjo un error con el servicio de telemetría de Windows.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Asegúrese de que el servicio de datos de diagnóstico está habilitado.</a><br>
Compruebe que la configuración de incorporación y los scripts se implementaron correctamente. Intente volver a implementar los paquetes de configuración.<br>
Consulta <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Incorporación de dispositivos Windows 10</a>.</td>
</tr>
<tr>
<td>35</td>
<td>Microsoft Defender para el servicio de extremo no pudo quitarse a sí mismo como dependencia del servicio telemetría y experiencias del usuario conectado. Código de error: <code>variable</code> .</td>
<td>Se produjo un error con el servicio de telemetría de Windows durante el offboarding. El proceso de offboarding continúa.
</td>
<td>Compruebe si hay errores con el servicio de datos de diagnóstico de Windows.</td>
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
<td>El dispositivo no usa una conexión de pago/medición y se pondrá en contacto con el servidor como de costumbre.</td>
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
<td>El componente WDATP de Microsoft Defender para extremo no pudo realizar la acción. Componente: %1, Acción: %2, Tipo de excepción: %3, Mensaje de excepción: %4</td>
<td>Error interno. No se pudo iniciar el servicio.</td>
<td>Si este error persiste, póngase en contacto con el soporte técnico.</td>
</tr>
<tr>
<td>43</td>
<td>El componente WDATP de Microsoft Defender para extremo no pudo realizar la acción. Componente: %1, Acción: %2, Tipo de excepción: %3, Error de excepción: %4, Mensaje de excepción: %5</td>
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
<td>Se produjo un error al iniciar el servicio al crear una sesión de ETW debido a la falta de recursos. El servicio se inició y se está ejecutando, pero no informará de ningún evento de sensor hasta que se inicia la sesión de ETW.</td>
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
</tbody>
</table>

>¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a>Temas relacionados
- [Incorporación de dispositivos Windows 10](configure-endpoints.md)
- [Configurar el proxy de dispositivo y la configuración de conectividad a Internet](configure-proxy-internet.md)
- [Solucionar problemas de Microsoft Defender para el extremo](troubleshoot-onboarding.md)
