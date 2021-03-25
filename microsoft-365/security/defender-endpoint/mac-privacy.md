---
title: Privacidad para ATP de Microsoft Defender para Mac
description: Controles de privacidad, cómo configurar las opciones de directiva que afectan a la privacidad y la información sobre los datos de diagnóstico recopilados en ATP de Microsoft Defender para Mac.
keywords: microsoft, defender, atp, mac, privacidad, diagnóstico
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 83a56a74ff949b23843417942923d2b4b810b4ee
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185938"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-for-mac"></a>Privacidad de Microsoft Defender para Endpoint para Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


Microsoft se compromete a proporcionarle la información y los controles que necesita para tomar decisiones sobre cómo se recopilan y usan los datos cuando usa Microsoft Defender para Endpoint para Mac.

En este tema se describen los controles de privacidad disponibles en el producto, cómo administrar estos controles con la configuración de directiva y más detalles sobre los eventos de datos que se recopilan.

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-for-mac"></a>Información general sobre los controles de privacidad en Microsoft Defender para Endpoint para Mac

En esta sección se describen los controles de privacidad de los distintos tipos de datos recopilados por Microsoft Defender para Endpoint para Mac.

### <a name="diagnostic-data"></a>Datos de diagnóstico

Los datos de diagnóstico se usan para mantener Microsoft Defender for Endpoint seguro y actualizado, detectar, diagnosticar y corregir problemas y también realizar mejoras en el producto.

Algunos datos de diagnóstico son necesarios, mientras que otros son opcionales. Le damos la posibilidad de elegir si enviarnos datos de diagnóstico necesarios u opcionales mediante los controles de privacidad, como la configuración de directiva para las organizaciones.

Hay dos niveles de datos de diagnóstico para el software cliente de Microsoft Defender para endpoint entre los que puede elegir:

* **Obligatorio:** los datos mínimos necesarios para ayudar a mantener Microsoft Defender para endpoint seguro, actualizado y con el rendimiento esperado en el dispositivo en el que está instalado.

* **Opcional:** datos adicionales que ayudan a Microsoft a realizar mejoras en el producto y proporcionan información mejorada para ayudar a detectar, diagnosticar y corregir problemas.

De forma predeterminada, solo se envían los datos de diagnóstico necesarios a Microsoft.

### <a name="cloud-delivered-protection-data"></a>Datos de protección entregados en la nube

La protección entregada en la nube se usa para proporcionar una mayor y más rápida protección con acceso a los últimos datos de protección en la nube.

Habilitar el servicio de protección entregado en la nube es opcional, pero es muy recomendable porque proporciona protección importante contra malware en los puntos de conexión y en toda la red.

### <a name="sample-data"></a>Datos de ejemplo

Los datos de ejemplo se usan para mejorar las capacidades de protección del producto, enviando muestras sospechosas de Microsoft para que se puedan analizar. Habilitar el envío automático de ejemplo es opcional.

Cuando esta característica está habilitada y es probable que el ejemplo recopilado contenga información personal, se pedirá al usuario su consentimiento.

## <a name="manage-privacy-controls-with-policy-settings"></a>Administre los controles de privacidad con la configuración de directiva

Si es administrador de TI, es posible que desee configurar estos controles en el nivel de empresa. 

Los controles de privacidad de los distintos tipos de datos descritos en la sección anterior se describen detalladamente en Establecer preferencias para [Microsoft Defender para Endpoint para Mac](mac-preferences.md).

Al igual que con cualquier configuración de directiva nueva, debe probarlas cuidadosamente en un entorno limitado y controlado para asegurarse de que la configuración que configure tenga el efecto deseado antes de implementar la configuración de directiva más ampliamente en su organización.

## <a name="diagnostic-data-events"></a>Eventos de datos de diagnóstico

En esta sección se describen los datos de diagnóstico necesarios y los que se consideran datos de diagnóstico opcionales, junto con una descripción de los eventos y campos recopilados.

### <a name="data-fields-that-are-common-for-all-events"></a>Campos de datos comunes para todos los eventos
Hay cierta información acerca de los eventos que es común a todos, independientemente del subtipo de datos o la categoría. 

Los siguientes campos se consideran comunes para todos los eventos:

| Field                   | Descripción |
| ----------------------- | ----------- |
| plataforma                | La clasificación general de la plataforma en la que se ejecuta la aplicación. Permite a Microsoft identificar en qué plataformas se puede producir un problema para que se pueda priorizar correctamente. |
| machine_guid            | Identificador único asociado al dispositivo. Permite a Microsoft identificar si los problemas afectan a un conjunto selecto de instalaciones y cuántos usuarios se verán afectados. |
| sense_guid              | Identificador único asociado al dispositivo. Permite a Microsoft identificar si los problemas afectan a un conjunto selecto de instalaciones y cuántos usuarios se verán afectados. |
| org_id                  | Identificador único asociado a la empresa a la que pertenece el dispositivo. Permite a Microsoft identificar si los problemas afectan a un conjunto selecto de empresas y cuántas empresas se verán afectadas. |
| nombre de host                | Nombre de dispositivo local (sin sufijo DNS). Permite a Microsoft identificar si los problemas afectan a un conjunto selecto de instalaciones y cuántos usuarios se verán afectados. |
| product_guid            | Identificador único del producto. Permite a Microsoft diferenciar los problemas que afectan a diferentes sabores del producto. |
| app_version             | Versión de la aplicación Microsoft Defender para Endpoint para Mac. Permite a Microsoft identificar qué versiones del producto muestran un problema para que se pueda priorizar correctamente.|
| sig_version             | Versión de la base de datos de inteligencia de seguridad. Permite a Microsoft identificar qué versiones de la inteligencia de seguridad muestran un problema para que se pueda priorizar correctamente. |
| supported_compressions  | Lista de algoritmos de compresión admitidos por la aplicación, por ejemplo `['gzip']` . Permite a Microsoft comprender qué tipos de compresión se pueden usar cuando se comunica con la aplicación. |
| release_ring            | Anillo al que está asociado el dispositivo (por ejemplo, Insider Fast, Insider Slow, Production). Permite a Microsoft identificar en qué anillo de lanzamiento puede producirse un problema para que se pueda priorizar correctamente. |


### <a name="required-diagnostic-data"></a>Datos de diagnósticos necesarios

**Los datos de diagnóstico** necesarios son los datos mínimos necesarios para ayudar a mantener Microsoft Defender para endpoint seguro, actualizado y con el rendimiento esperado en el dispositivo en el que está instalado.

Los datos de diagnóstico necesarios ayudan a identificar problemas con Microsoft Defender para endpoint que pueden estar relacionados con una configuración de dispositivo o software. Por ejemplo, puede ayudar a determinar si una característica de Microsoft Defender para endpoint se bloquea con más frecuencia en una versión determinada del sistema operativo, con características recién introducidas o cuando determinadas características de Microsoft Defender para endpoint están deshabilitadas. Los datos de diagnóstico necesarios ayudan a Microsoft a detectar, diagnosticar y solucionar estos problemas con mayor rapidez para reducir el impacto para los usuarios u organizaciones.

#### <a name="software-setup-and-inventory-data-events"></a>Eventos de datos de inventario y configuración de software

**Instalación y desinstalación de Microsoft Defender para endpoint**

Se recopilan los campos siguientes: 

| Field            | Descripción |
| ---------------- | ----------- |
| correlation_id   | Identificador único asociado a la instalación. |
| version          | Versión del paquete. |
| severity         | Gravedad del mensaje (por ejemplo, Informativo). |
| código             | Código que describe la operación. |
| text             | Información adicional asociada a la instalación del producto. |

**Configuración de Microsoft Defender para punto de conexión**

Se recopilan los campos siguientes: 

| Field                                               | Descripción |
| --------------------------------------------------- | ----------- |
| antivirus_engine.enable_real_time_protection        | Si la protección en tiempo real está habilitada en el dispositivo o no. |
| antivirus_engine.passive_mode                       | Si el modo pasivo está habilitado en el dispositivo o no. |
| cloud_service.enabled                               | Si la protección entregada en la nube está habilitada en el dispositivo o no. |
| cloud_service.timeout                               | Tiempo de espera cuando la aplicación se comunica con la nube de Microsoft Defender para endpoint. |
| cloud_service.heartbeat_interval                    | Intervalo entre latidos consecutivos enviados por el producto a la nube. |
| cloud_service.service_uri                           | URI usado para comunicarse con la nube. |
| cloud_service.diagnostic_level                      | Nivel de diagnóstico del dispositivo (obligatorio, opcional). |
| cloud_service.automatic_sample_submission           | Si el envío de muestra automático está activado o no. |
| edr.early_preview                                   | Si el dispositivo debe ejecutar características de vista previa de EDR. |
| edr.group_id                                        | Identificador de grupo usado por el componente de detección y respuesta. |
| edr.tags                                            | Etiquetas definidas por el usuario. |
| características. \[ nombre de característica opcional\]                  | Lista de características de vista previa, junto con si están habilitadas o no. |

#### <a name="product-and-service-usage-data-events"></a>Eventos de datos de uso de productos y servicios

**Informe de actualización de inteligencia de seguridad**

Se recopilan los campos siguientes: 

| Field            | Descripción |
| ---------------- | ----------- |
| from_version     | Versión original de inteligencia de seguridad. |
| to_version       | Nueva versión de inteligencia de seguridad. |
| status           | Estado de la actualización que indica el éxito o error. |
| using_proxy      | Si la actualización se ha realizado a través de un proxy. |
| error            | Código de error si se produjo un error en la actualización. |
| motivo           | Mensaje de error si se ha actualizado el archivo. |

#### <a name="product-and-service-performance-data-events"></a>Eventos de datos de rendimiento de productos y servicios

**Estadísticas de extensión de kernel**

Se recopilan los campos siguientes: 

| Field            | Descripción |
| ---------------- | ----------- |
| version          | Versión de Microsoft Defender para Endpoint para Mac. |
| instance_id      | Identificador único generado en el inicio de extensión de kernel. |
| trace_level      | Nivel de seguimiento de la extensión del kernel. |
| subsistema        | Subsistema subyacente usado para la protección en tiempo real. |
| ipc.connects     | Número de solicitudes de conexión recibidas por la extensión del kernel. |
| ipc.rejects      | Número de solicitudes de conexión rechazadas por la extensión del kernel. |
| ipc.connected    | Si hay alguna conexión activa a la extensión del kernel. |

#### <a name="support-data"></a>Datos de soporte técnico

**Registros de diagnóstico**

Los registros de diagnóstico solo se recopilan con el consentimiento del usuario como parte de la característica de envío de comentarios. Los siguientes archivos se recopilan como parte de los registros de soporte técnico:

- Todos los archivos *en /Library/Logs/Microsoft/mdatp/*
- Subconjunto de archivos en */Library/Application Support/Microsoft/Defender/* creados y usados por Microsoft Defender para Endpoint para Mac
- Subconjunto de archivos en */Library/Managed Preferences* que usa Microsoft Defender para Endpoint para Mac
- /Library/Logs/Microsoft/autoupdate.log
- $HOME/Library/Preferences/com.microsoft.autoupdate2.plist

### <a name="optional-diagnostic-data"></a>Datos de diagnóstico opcionales

**Los datos de diagnóstico** opcionales son datos adicionales que ayudan a Microsoft a realizar mejoras en el producto y proporcionan información mejorada para ayudar a detectar, diagnosticar y solucionar problemas.

Si elige enviarnos sus datos de diagnóstico opcionales, también se incluyen los datos de diagnósticos requeridos.

Algunos ejemplos de datos de diagnóstico opcionales incluyen datos que Microsoft recopila sobre la configuración del producto (por ejemplo, el número de exclusiones establecidas en el dispositivo) y el rendimiento del producto (medidas agregadas sobre el rendimiento de los componentes del producto).

#### <a name="software-setup-and-inventory-data-events"></a>Eventos de datos de inventario y configuración de software

**Configuración de Microsoft Defender para punto de conexión**

Se recopilan los campos siguientes: 

| Field                                              | Descripción |
| -------------------------------------------------- | ----------- |
| connection_retry_timeout                           | Tiempo de espera de reintento de conexión cuando se comunica con la nube. |
| file_hash_cache_maximum                            | Tamaño de la memoria caché del producto. |
| crash_upload_daily_limit                           | Límite de registros de bloqueo cargados diariamente. |
| antivirus_engine.exclusions[].is_directory         | Si la exclusión del examen es un directorio o no. |
| antivirus_engine.exclusions[].path                 | Ruta de acceso que se excluyó del examen. |
| antivirus_engine.exclusions[].extension            | Extensión excluida del examen. |
| antivirus_engine.exclusions[].name                 | Nombre del archivo excluido del examen. |
| antivirus_engine.scan_cache_maximum                | Tamaño de la memoria caché del producto. |
| antivirus_engine.maximum_scan_threads              | Número máximo de subprocesos usados para el examen. |
| antivirus_engine.threat_restoration_exclusion_time | Tiempo de espera antes de que se pueda detectar de nuevo un archivo restaurado desde la cuarentena. |
| filesystem_scanner.full_scan_directory             | Directorio de examen completo. |
| filesystem_scanner.quick_scan_directories          | Lista de directorios usados en el examen rápido. |
| edr.latency_mode                                   | Modo de latencia usado por el componente de detección y respuesta. |
| edr.proxy_address                                  | Dirección de proxy usada por el componente de detección y respuesta. |

**Configuración de Actualización automática de Microsoft**

Se recopilan los campos siguientes: 

| Field                       | Descripción |
| --------------------------- | ----------- |
| how_to_check                | Determina cómo se comprueban las actualizaciones de productos (por ejemplo, automáticas o manuales). |
| channel_name                | Actualizar canal asociado al dispositivo. |
| manifest_server             | Servidor usado para descargar actualizaciones. |
| update_cache                | Ubicación de la memoria caché usada para almacenar actualizaciones. |

### <a name="product-and-service-usage"></a>Uso de productos y servicios

#### <a name="diagnostic-log-upload-started-report"></a>Informe de carga iniciada del registro de diagnóstico

Se recopilan los campos siguientes: 

| Field            | Descripción |
| ---------------- | ----------- |
| sha256           | Identificador SHA256 del registro de soporte técnico. |
| size             | Tamaño del registro de soporte técnico. |
| original_path    | Ruta de acceso al registro de soporte técnico (siempre en */Library/Application Support/Microsoft/Defender/wdavdiag/*). |
| format           | Formato del registro de soporte técnico. |

#### <a name="diagnostic-log-upload-completed-report"></a>Informe completado de carga de registro de diagnóstico

Se recopilan los campos siguientes: 

| Field            | Descripción |
| ---------------- | ----------- |
| request_id       | Identificador de correlación para la solicitud de carga del registro de soporte técnico. |
| sha256           | Identificador SHA256 del registro de soporte técnico. |
| blob_sas_uri     | URI usado por la aplicación para cargar el registro de soporte técnico. |

#### <a name="product-and-service-performance-data-events"></a>Eventos de datos de rendimiento de productos y servicios

**Cierre inesperado de la aplicación (bloqueo)**

Cierres de aplicación inesperados y el estado de la aplicación cuando esto ocurre.

**Estadísticas de extensión de kernel**

Se recopilan los campos siguientes: 

| Field                          | Descripción |
| ------------------------------ | ----------- |
| pkt_ack_timeout                | Las siguientes propiedades son valores numéricos agregados, que representan el recuento de eventos que se han producido desde el inicio de la extensión del kernel. |
| pkt_ack_conn_timeout             | |
| ipc.ack_pkts                     | |
| ipc.nack_pkts                    | |
| ipc.send.ack_no_conn             | |
| ipc.send.nack_no_conn            | |
| ipc.send.ack_no_qsq              | |
| ipc.send.nack_no_qsq             | |
| ipc.ack.no_space                 | |
| ipc.ack.timeout                  | |
| ipc.ack.ackd_fast                | |
| ipc.ack.ackd                     | |
| ipc.recv.bad_pkt_len             | |
| ipc.recv.bad_reply_len           | |
| ipc.recv.no_waiter               | |
| ipc.recv.copy_failed             | |
| ipc.kauth.vnode.mask             | |
| ipc.kauth.vnode.read             | |
| ipc.kauth.vnode.write            | |
| ipc.kauth.vnode.exec             | |
| ipc.kauth.vnode.del              | |
| ipc.kauth.vnode.read_attr        | |
| ipc.kauth.vnode.write_attr       | |
| ipc.kauth.vnode.read_ex_attr     | |
| ipc.kauth.vnode.write_ex_attr    | |
| ipc.kauth.vnode.read_sec         | |
| ipc.kauth.vnode.write_sec        | |
| ipc.kauth.vnode.take_own         | |
| ipc.kauth.vnode.link             | |
| ipc.kauth.vnode.create           | |
| ipc.kauth.vnode.move             | |
| ipc.kauth.vnode.mount            | |
| ipc.kauth.vnode.denied           | |
| ipc.kauth.vnode.ackd_before_deadline | |
| ipc.kauth.vnode.missed_deadline  | |
| ipc.kauth.file_op.mask           | |
| ipc.kauth_file_op.open           | |
| ipc.kauth.file_op.close          | |
| ipc.kauth.file_op.close_modified | |
| ipc.kauth.file_op.move           | |
| ipc.kauth.file_op.link           | |
| ipc.kauth.file_op.exec           | |
| ipc.kauth.file_op.remove         | |
| ipc.kauth.file_op.unmount        | |
| ipc.kauth.file_op.fork           | |
| ipc.kauth.file_op.create         | |

## <a name="resources"></a>Recursos

- [Privacidad de Microsoft](https://privacy.microsoft.com/)
