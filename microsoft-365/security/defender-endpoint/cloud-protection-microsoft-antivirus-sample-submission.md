---
title: Protección en la nube y envío de ejemplo en el Antivirus de Microsoft Defender
description: Más información sobre la protección proporcionada en la nube y el Antivirus de Microsoft Defender
keywords: Antivirus de Microsoft Defender, tecnologías de última generación, envío de ejemplos antivirus, av de última generación, aprendizaje automático, antimalware, seguridad, defender, nube, protección entregada en la nube
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.subservice: mde
ms.topic: article
ms.date: 02/24/2022
ms.collection: M365-security-compliance
search.appverid: met150
ms.openlocfilehash: 55cc82f03a193f94909268317b59370ef62ca79f
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67701530"
---
# <a name="cloud-protection-and-sample-submission-at-microsoft-defender-antivirus"></a>Protección en la nube y envío de ejemplo en el Antivirus de Microsoft Defender

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Antivirus de Microsoft Defender usa muchos mecanismos inteligentes para detectar malware. Una de las funcionalidades más eficaces es la capacidad de aplicar el poder de la nube para detectar malware y realizar análisis rápidos. La protección en la nube y el envío automático de muestras funcionan junto con el Antivirus de Microsoft Defender para ayudar a protegerse frente a amenazas nuevas y emergentes. 

Si se detecta un archivo sospechoso o malintencionado, se envía un ejemplo al servicio en la nube para su análisis mientras antivirus de Microsoft Defender bloquea el archivo. En cuanto se realiza una determinación, lo que sucede rápidamente, el antivirus de Microsoft Defender libera o bloquea el archivo. 

En este artículo se proporciona información general sobre la protección en la nube y el envío automático de ejemplos en Antivirus de Microsoft Defender. Para más información sobre la protección en la nube, consulte [Protección en la nube y Antivirus de Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md).

## <a name="how-cloud-protection-and-sample-submission-work-together"></a>Cómo funcionan conjuntamente la protección en la nube y el envío de ejemplos

Para comprender cómo funciona la protección en la nube junto con el envío de ejemplo, puede ser útil comprender cómo Defender para punto de conexión protege frente a amenazas. Microsoft Intelligent Security Graph supervisa los datos de amenazas de una amplia red de sensores. Microsoft capas de modelos de aprendizaje automático basados en la nube que pueden evaluar archivos basados en señales del cliente y la vasta red de sensores y datos en Intelligent Security Graph. Este enfoque ofrece a Defender para punto de conexión la capacidad de bloquear muchas amenazas nunca vistas. 

En la imagen siguiente se muestra el flujo de protección en la nube y el envío de ejemplo con el Antivirus de Microsoft Defender:

:::image type="content" source="images/cloud-protection-flow.png" alt-text="Flujo de protección entregado en la nube" lightbox="images/cloud-protection-flow.png":::

Antivirus de Microsoft Defender y protección en la nube bloquean automáticamente las amenazas más nuevas y nunca vistas a primera vista mediante los métodos siguientes:

1. Modelos de aprendizaje automático ligeros basados en cliente, bloqueando malware nuevo y desconocido.

2. Análisis de comportamiento local, detener ataques basados en archivos y sin archivos.

3. Antivirus de alta precisión, detectando malware común a través de técnicas genéricas y heurísticas.

4. La protección avanzada basada en la nube se proporciona para los casos en los que antivirus de Microsoft Defender que se ejecuta en el punto de conexión necesita más inteligencia para comprobar la intención de un archivo sospechoso.

   1. En caso de que antivirus de Microsoft Defender no pueda tomar una determinación clara, los metadatos de los archivos se envían al servicio de protección en la nube. A menudo, en milisegundos, el servicio de protección en la nube puede determinar en función de los metadatos si el archivo es malintencionado o no una amenaza.  

      - La consulta en la nube de metadatos de archivo puede ser el resultado del comportamiento, la marca de la web u otras características en las que no se determina un veredicto claro.
      - Se envía una pequeña carga de metadatos, con el objetivo de alcanzar un veredicto de malware o no una amenaza. Los metadatos no incluyen información de identificación personal (PII). La información, como los nombres de archivo, se aplica un hash.
      - Puede ser sincrónico o asincrónico. En el caso de sincrónico, el archivo no se abrirá hasta que la nube represente un veredicto. En el caso de la asincrónica, el archivo se abrirá mientras la protección en la nube realiza su análisis.
      - Los metadatos pueden incluir atributos pe, atributos de archivo estáticos, atributos dinámicos y contextuales, etc. (consulte [Ejemplos de metadatos enviados al servicio de protección en la nube](#examples-of-metadata-sent-to-the-cloud-protection-service)).

   2. Después de examinar los metadatos, si la protección en la nube del Antivirus de Microsoft Defender no puede alcanzar un veredicto concluyente, puede solicitar una muestra del archivo para una inspección adicional. Esta solicitud respeta la configuración de configuración para el envío de ejemplo:

      1. **Enviar muestras seguras automáticamente** (valor predeterminado)
         - Las muestras seguras son ejemplos que se consideran que no suelen contener datos de PII, como .bat, .scr, .dll, .exe.
         - Si es probable que el archivo contenga PII, el usuario recibirá una solicitud para permitir el envío de ejemplo de archivo.
         - Esta opción es la predeterminada en Windows, macOS y Linux.

      2. **Siempre preguntar**
         - Si está configurado, siempre se le pedirá al usuario su consentimiento antes del envío de archivos.
         - Esta configuración no está disponible en la protección en la nube de macOS.

      3. **Enviar todos los ejemplos automáticamente**
         - Si se configura, todos los ejemplos se enviarán automáticamente.
         - Si desea que el envío de ejemplo incluya macros incrustadas en documentos de Word, debe elegir "Enviar todos los ejemplos automáticamente".
         - Esta configuración no está disponible en la protección en la nube de macOS.

      4. **No enviar**
         - Impide "bloquear a primera vista" en función del análisis de ejemplo de archivo
         - "No enviar" es el equivalente a la configuración "Deshabilitado" en la directiva de macOS
         - Los metadatos se envían para las detecciones incluso cuando el envío de ejemplo está deshabilitado

   3. Después de enviar metadatos o archivos a la protección en la nube, puede usar **ejemplos**, **detonaciones** o modelos de aprendizaje automático de **análisis de macrodatos** para llegar a un veredicto. La desactivación de la protección entregada en la nube limitará el análisis solo a lo que el cliente puede proporcionar a través de modelos de aprendizaje automático locales y funciones similares.

> [!IMPORTANT]
> [Bloquear a primera vista (BAFS)](configure-block-at-first-sight-microsoft-defender-antivirus.md) proporciona detonación y análisis para determinar si un archivo o proceso es seguro. BAFS puede retrasar momentáneamente la apertura de un archivo hasta que se alcance un veredicto. Si deshabilita el envío de ejemplo, BAFS también está deshabilitado y el análisis de archivos solo se limita a metadatos. Se recomienda mantener habilitados el envío de muestras y BAFS. Para obtener más información, consulte [¿Qué es "bloquear a primera vista"?](configure-block-at-first-sight-microsoft-defender-antivirus.md#what-is-block-at-first-sight)

## <a name="cloud-protection-levels"></a>Niveles de protección en la nube

La protección en la nube está habilitada de forma predeterminada en el Antivirus de Microsoft Defender. Se recomienda mantener habilitada la protección en la nube, aunque puede configurar el nivel de protección para su organización. Consulte [Especificación del nivel de protección entregado en la nube para antivirus de Microsoft Defender](specify-cloud-protection-level-microsoft-defender-antivirus.md).

## <a name="sample-submission-settings"></a>Configuración de envío de ejemplo

Además de configurar el nivel de protección en la nube, puede configurar los valores de envío de ejemplo. Puede elegir entre varias opciones:

- **Enviar muestras seguras automáticamente**  (el comportamiento predeterminado)
- **Enviar todos los ejemplos automáticamente**  
- **No enviar ejemplos**  

Para obtener información sobre las opciones de configuración mediante Intune, Configuration Manager, GPO o PowerShell, consulte [Activar la protección en la nube en el Antivirus de Microsoft Defender](enable-cloud-protection-microsoft-defender-antivirus.md).

## <a name="examples-of-metadata-sent-to-the-cloud-protection-service"></a>Ejemplos de metadatos enviados al servicio de protección en la nube

:::image type="content" source="images/cloud-protection-metadata-sample.png" alt-text="Ejemplos de metadatos enviados a la protección en la nube en el portal del Antivirus de Microsoft Defender" lightbox="images/cloud-protection-metadata-sample.png":::

En la tabla siguiente se enumeran ejemplos de metadatos enviados para su análisis por protección en la nube:

| Tipo | Atributo |
|:---|:---|
| Atributos de máquina | `OS version` <br/> `Processor` <br/> `Security settings` |
| Atributos dinámicos y contextuales | **Proceso e instalación** <br/> `ProcessName` <br/> `ParentProcess` <br/> `TriggeringSignature` <br/> `TriggeringFile` <br/> `Download IP and url` <br/> `HashedFullPath` <br/> `Vpath` <br/> `RealPath` <br/> `Parent/child relationships` <br/><br/>**Comportamiento** <br/> `Connection IPs` <br/> `System changes` <br/> `API calls` <br/> `Process injection` <br/><br/>**Locale** <br/> `Locale setting` <br/> `Geographical location` |
| Atributos de archivo estáticos | **Hashes parciales y completos** <br/> `ClusterHash` <br/> `Crc16` <br/> `Ctph` <br/> `ExtendedKcrcs` <br/> `ImpHash` <br/> `Kcrc3n` <br/> `Lshash` <br/> `LsHashs` <br/> `PartialCrc1` <br/> `PartialCrc2` <br/> `PartialCrc3` <br/> `Sha1` <br/> `Sha256` <br/><br/>**Propiedades de archivo** <br/>`FileName` <br/> `FileSize` <br/><br/> **Información del firmante** <br/> `AuthentiCodeHash` <br/> `Issuer` <br/> `IssuerHash` <br/> `Publisher` <br/> `Signer` <br/> `SignerHash` |

## <a name="samples-are-treated-as-customer-data"></a>Los ejemplos se tratan como datos de clientes

Por si se pregunta qué ocurre con los envíos de ejemplo, Defender para punto de conexión trata todos los ejemplos de archivo como datos de cliente. Microsoft respeta las opciones geográficas y de retención de datos que ha seleccionado su organización al incorporarse a Defender para punto de conexión. 

Además, Defender for Endpoint ha recibido varias certificaciones de cumplimiento, lo que demuestra la adhesión continua a un sofisticado conjunto de controles de cumplimiento:

- ISO 27001
- ISO 27018
- SOC I, II, III
- Pci

Para obtener más información, consulte los siguientes recursos:

- [Ofertas de cumplimiento de Azure](/azure/storage/common/storage-compliance-offerings) 
- [Portal de confianza del servicio](https://servicetrust.microsoft.com)
- [Microsoft Defender para punto de conexión almacenamiento de datos y privacidad](data-storage-privacy.md#data-storage-location)

## <a name="other-file-sample-submission-scenarios"></a>Otros escenarios de envío de ejemplo de archivo

Hay dos escenarios más en los que Defender para punto de conexión podría solicitar un ejemplo de archivo que no esté relacionado con la protección en la nube en el Antivirus de Microsoft Defender. Estos escenarios se describen en la tabla siguiente:

| Escenario | Descripción |
|:---|:---|
|Colección manual de ejemplos de archivos en el portal de Microsoft 365 Defender | Al incorporar dispositivos a Defender para punto de conexión, puede configurar los valores para la [detección y respuesta de puntos de conexión (EDR).](overview-endpoint-detection-response.md) Por ejemplo, hay una configuración para habilitar colecciones de ejemplo desde el dispositivo, que se puede confundir fácilmente con la configuración de envío de ejemplo descrita en este artículo. <br/><br/>La configuración de EDR controla la recopilación de ejemplos de archivos de los dispositivos cuando se solicita a través del portal de Microsoft 365 Defender y está sujeta a los roles y permisos ya establecidos. Esta configuración puede permitir o bloquear la recopilación de archivos desde el punto de conexión para características como el análisis profundo en el portal de Microsoft 365 Defender. Si esta configuración no está configurada, el valor predeterminado es habilitar la recopilación de ejemplo. <br/><br/>Obtenga información sobre la configuración de Defender para punto de conexión, consulte [Incorporación de herramientas y métodos para Windows 10 dispositivos en Defender para punto de conexión](configure-endpoints.md). |
| Análisis automatizado de contenido de investigación y respuesta | Cuando las [investigaciones automatizadas](automated-investigations.md) se ejecutan en dispositivos (cuando se configuran para ejecutarse automáticamente en respuesta a una alerta o se ejecutan manualmente), los archivos que se identifican como sospechosos se pueden recopilar de los puntos de conexión para una inspección adicional. Si es necesario, la característica de análisis de contenido de archivos para las investigaciones automatizadas se puede deshabilitar en el portal de Microsoft 365 Defender. <br/><br/> Los nombres de extensión de archivo también se pueden modificar para agregar o quitar extensiones para otros tipos de archivo que se enviarán automáticamente durante una investigación automatizada. <br/><br/> Para más información, consulte [Administración de cargas de archivos de automatización](manage-automation-file-uploads.md). |

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características iOS](ios-configure-features.md)

## <a name="see-also"></a>Vea también

[Información sobre los servicios de protección de última generación](next-generation-protection.md)

[Configure la corrección para las detecciones del Antivirus de Microsoft Defender.](configure-remediation-microsoft-defender-antivirus.md)
