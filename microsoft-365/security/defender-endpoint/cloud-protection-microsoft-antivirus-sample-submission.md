---
title: Protección en la nube y envío de ejemplo en Antivirus de Microsoft Defender
description: Obtenga información sobre la protección y la protección entregadas en la nube Antivirus de Microsoft Defender
keywords: Antivirus de Microsoft Defender, tecnologías de última generación, envío de ejemplo antivirus, av de próxima generación, aprendizaje automático, antimalware, seguridad, defender, nube, protección entregada en la nube
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 10/18/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: 1c7ef9883aacf9af0ee5474795c19adf1694fd9c
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2021
ms.locfileid: "60701734"
---
# <a name="cloud-protection-and-sample-submission-in-microsoft-defender-antivirus"></a>Protección en la nube y envío de ejemplo en Antivirus de Microsoft Defender

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)
- [Antivirus de Microsoft Defender](microsoft-defender-antivirus-windows.md)

Antivirus de Microsoft Defender muchos mecanismos inteligentes para detectar malware. Una de las capacidades más eficaces es la capacidad de aplicar la potencia de la nube para detectar malware y realizar análisis rápidos. La protección en la nube y el envío automático de muestras funcionan Antivirus de Microsoft Defender para ayudar a proteger contra amenazas nuevas y emergentes. 

Si se detecta un archivo sospechoso o malintencionado, se envía un ejemplo al servicio en la nube para su análisis mientras Antivirus de Microsoft Defender bloquea el archivo. Tan pronto como se realiza una determinación, que se produce rápidamente, el archivo se libera o se bloquea mediante Antivirus de Microsoft Defender. 

En este artículo se proporciona información general sobre la protección en la nube y el envío automático de muestras en Antivirus de Microsoft Defender. Para obtener más información sobre la protección en la nube, consulte [Cloud protection and Antivirus de Microsoft Defender](cloud-protection-microsoft-defender-antivirus.md).

## <a name="how-cloud-protection-and-sample-submission-work-together"></a>Cómo funcionan conjuntamente la protección en la nube y el envío de muestras

Para comprender cómo funciona la protección en la nube junto con el envío de ejemplo, puede resultar útil comprender cómo Defender for Endpoint protege contra amenazas. Microsoft Intelligent Security Graph los datos de amenazas de una amplia red de sensores. Microsoft capas de modelos de aprendizaje automático basados en la nube que pueden evaluar archivos basados en las señales del cliente y la amplia red de sensores y datos en la seguridad inteligente Graph. Este enfoque proporciona a Defender for Endpoint la capacidad de bloquear muchas amenazas nunca vistas. 

En la siguiente imagen se muestra el flujo de protección en la nube y el envío de ejemplo con Antivirus de Microsoft Defender:

:::image type="content" source="images/cloud-protection-flow.png" alt-text="Flujo de protección entregado en la nube":::

Antivirus de Microsoft Defender y la protección en la nube bloquean automáticamente la mayoría de las amenazas nuevas nunca vistas a primera vista mediante los métodos siguientes:

1. Modelos de aprendizaje automático ligeros basados en cliente, que bloquean malware nuevo y desconocido.

2. Análisis de comportamiento local, detención de ataques basados en archivos y sin archivos.

3. Antivirus de alta precisión, que detecta malware común a través de técnicas heurísticas y genéricas.

4. La protección avanzada basada en la nube se proporciona para los casos en los que Antivirus de Microsoft Defender ejecución en el punto de conexión necesita más inteligencia para comprobar la intención de un archivo sospechoso.

   1. En caso de Antivirus de Microsoft Defender una determinación clara, los metadatos de archivo se envían al servicio de protección en la nube. A menudo, en milisegundos, el servicio de protección en la nube puede determinar en función de los metadatos si el archivo es malintencionado o no es una amenaza.  

      - La consulta en la nube de metadatos de archivo puede ser el resultado del comportamiento, la marca de la web u otras características en las que no se determina un veredicto claro.
      - Se envía una pequeña carga de metadatos, con el objetivo de alcanzar un veredicto de malware o no una amenaza. Los metadatos no incluyen información de identificación personal (PII). La información, como los nombres de archivo, se aplica hash.
      - Puede ser sincrónico o asincrónico. Para sincrónico, el archivo no se abrirá hasta que la nube represente un veredicto. Para los asincrónicos, el archivo se abrirá mientras la protección en la nube realiza su análisis.
      - Los metadatos pueden incluir atributos PE, atributos de archivo estáticos, atributos dinámicos y contextuales, y mucho más (vea Ejemplos de metadatos enviados [al servicio de protección en la nube).](#examples-of-metadata-sent-to-the-cloud-protection-service)

   2. Después de examinar los metadatos, si Antivirus de Microsoft Defender protección en la nube no puede alcanzar un veredicto concluyente, puede solicitar una muestra del archivo para una inspección posterior. Esta solicitud respeta la configuración de configuración para el envío de ejemplo:

      1. **Enviar muestras seguras automáticamente** (valor predeterminado)
         - Caja fuerte ejemplos son ejemplos que se consideran que no contienen normalmente datos de PII como: .bat, .scr, .dll, .exe.
         - Si es probable que el archivo contenga PII, el usuario recibirá una solicitud para permitir el envío de ejemplo de archivo.
         - Esta opción es la predeterminada en Windows, macOS y Linux.

      2. **Preguntar siempre**
         - Si está configurado, siempre se pedirá al usuario su consentimiento antes del envío de archivos.
         - Esta configuración no está disponible en la protección en la nube de macOS

      3. **Enviar todas las muestras automáticamente**
         - Si se configura, todos los ejemplos se enviarán automáticamente
         - Si desea que el envío de ejemplo incluya macros incrustadas en documentos de Word, debe elegir "Enviar todos los ejemplos automáticamente"
         - Esta configuración no está disponible en la protección en la nube de macOS

      4. **No enviar**
         - Impide "bloquear a primera vista" en función del análisis de ejemplo de archivo
         - "No enviar" equivale a la configuración "Deshabilitado" en la directiva de macOS
         - Los metadatos se envían para detecciones incluso cuando el envío de ejemplo está deshabilitado

   3. Después de enviar metadatos o archivos a la protección en la nube, puede usar **ejemplos,** **detonaciones** o modelos de aprendizaje automático de análisis de big **data** para llegar a un veredicto. Desactivar la protección entregada en la nube limitará el análisis a solo lo que el cliente puede proporcionar a través de modelos de aprendizaje automático locales y funciones similares.

> [!IMPORTANT]
> [El bloqueo a primera vista (BAFS)](configure-block-at-first-sight-microsoft-defender-antivirus.md) proporciona detonación y análisis para determinar si un archivo o proceso es seguro. BAFS puede retrasar la apertura de un archivo momentáneamente hasta que se llegue a un veredicto. Si deshabilita el envío de ejemplo, BAFS también se deshabilita y el análisis de archivos solo se limita a metadatos. Se recomienda mantener habilitado el envío de ejemplo y BAFS. Para obtener más información, vea [¿Qué es "bloquear a primera vista"?](configure-block-at-first-sight-microsoft-defender-antivirus.md#what-is-block-at-first-sight)

## <a name="cloud-protection-levels"></a>Niveles de protección en la nube

La protección en la nube está habilitada de forma predeterminada en Antivirus de Microsoft Defender. Le recomendamos que mantenga habilitada la protección en la nube, aunque puede configurar el nivel de protección de su organización. Vea [Especificar el nivel de protección entregado en la nube para Antivirus de Microsoft Defender](specify-cloud-protection-level-microsoft-defender-antivirus.md).

## <a name="sample-submission-settings"></a>Configuración de envío de ejemplo

Además de configurar el nivel de protección en la nube, puede configurar las opciones de envío de ejemplo. Puede elegir entre varias opciones:

- **Enviar muestras seguras automáticamente**  (comportamiento predeterminado)
- **Enviar todas las muestras automáticamente**  
- **No enviar muestras**  

Para obtener información acerca de las opciones de configuración con Intune, Configuration Manager, GPO o PowerShell, vea [Turn on cloud protection in Antivirus de Microsoft Defender](enable-cloud-protection-microsoft-defender-antivirus.md).

## <a name="examples-of-metadata-sent-to-the-cloud-protection-service"></a>Ejemplos de metadatos enviados al servicio de protección en la nube

:::image type="content" source="images/cloud-protection-metadata-sample.png" alt-text="imagen que muestra ejemplos de metadatos enviados a la protección en la nube en Antivirus de Microsoft Defender":::

En la tabla siguiente se enumeran ejemplos de metadatos enviados para su análisis por la protección en la nube:

| Tipo | Atributo |
|:---|:---|
| Atributos de máquina | `OS version` <br/> `Processor` <br/> `Security settings` |
| Atributos dinámicos y contextuales | **Proceso e instalación** <br/> `ProcessName` <br/> `ParentProcess` <br/> `TriggeringSignature` <br/> `TriggeringFile` <br/> `Download IP and url` <br/> `HashedFullPath` <br/> `Vpath` <br/> `RealPath` <br/> `Parent/child relationships` <br/><br/>**Comportamiento** <br/> `Connection IPs` <br/> `System changes` <br/> `API calls` <br/> `Process injection` <br/><br/>**Locale** <br/> `Locale setting` <br/> `Geographical location` |
| Atributos de archivo estático | **Hashes parciales y completos** <br/> `ClusterHash` <br/> `Crc16` <br/> `Ctph` <br/> `ExtendedKcrcs` <br/> `ImpHash` <br/> `Kcrc3n` <br/> `Lshash` <br/> `LsHashs` <br/> `PartialCrc1` <br/> `PartialCrc2` <br/> `PartialCrc3` <br/> `Sha1` <br/> `Sha256` <br/><br/>**Propiedades de archivo** <br/>`FileName` <br/> `FileSize` <br/><br/> **Información del firmante** <br/> `AuthentiCodeHash` <br/> `Issuer` <br/> `IssuerHash` <br/> `Publisher` <br/> `Signer` <br/> `SignerHash` |

## <a name="samples-are-treated-as-customer-data"></a>Las muestras se tratan como datos de cliente

Por si se pregunta qué sucede con los envíos de ejemplo, Defender for Endpoint trata todas las muestras de archivos como datos de cliente. Microsoft respeta las opciones geográficas y de retención de datos que su organización seleccionó al incorporarse a Defender for Endpoint. 

Además, Defender for Endpoint ha recibido varias certificaciones de cumplimiento, lo que demuestra el cumplimiento continuo de un sofisticado conjunto de controles de cumplimiento:

- ISO 27001
- ISO 27018
- SOC I, II, III
- y PCI

Para obtener más información, consulte los recursos siguientes:

- [Ofertas de cumplimiento de Azure](/azure/storage/common/storage-compliance-offerings) 
- [Portal de confianza del servicio](https://servicetrust.microsoft.com)
- [Privacidad y almacenamiento de datos de Microsoft Defender para endpoint](data-storage-privacy.md#data-storage-location)

## <a name="other-file-sample-submission-scenarios"></a>Otros escenarios de envío de ejemplo de archivo

Hay dos escenarios más en los que Defender for Endpoint puede solicitar un ejemplo de archivo que no esté relacionado con la protección de la nube en Antivirus de Microsoft Defender. Estos escenarios se describen en la tabla siguiente:

| Escenario | Descripción |
|:---|:---|
|Colección de ejemplos de archivos manual en el portal Microsoft 365 Defender archivo | Al incorporar dispositivos a Defender for Endpoint, puede configurar las opciones [para detección y respuesta de puntos de conexión (EDR).](overview-endpoint-detection-response.md) Por ejemplo, hay una configuración para habilitar colecciones de muestras desde el dispositivo, que puede confundirse fácilmente con la configuración de envío de ejemplo descrita en este artículo. <br/><br/>La EDR controla la colección de muestras de archivos de dispositivos cuando se solicita a través del portal de Microsoft 365 Defender y está sujeta a los roles y permisos ya establecidos. Esta configuración puede permitir o bloquear la recopilación de archivos desde el punto de conexión para características como el análisis profundo en el portal Microsoft 365 Defender web. Si esta configuración no está configurada, el valor predeterminado es habilitar la colección de muestras. <br/><br/>Obtenga información sobre las opciones de configuración de Defender for Endpoint, vea: Herramientas y métodos de incorporación [para Windows 10 dispositivos en Defender para endpoint](configure-endpoints.md) |
| Análisis automatizado de contenido de investigación y respuesta | Cuando se ejecutan investigaciones automatizadas en dispositivos (cuando se configura para ejecutarse automáticamente en respuesta a una alerta o ejecutarse manualmente), los archivos identificados como [sospechosos](automated-investigations.md) se pueden recopilar desde los puntos de conexión para una inspección posterior. Si es necesario, la característica de análisis de contenido de archivos para investigaciones automatizadas se puede deshabilitar en el portal Microsoft 365 Defender datos. <br/><br/> Los nombres de extensión de archivo también se pueden modificar para agregar o quitar extensiones para otros tipos de archivo que se envían automáticamente durante una investigación automatizada. <br/><br/> Para obtener más información, vea [Manage automation file uploads](manage-automation-file-uploads.md). |

## <a name="see-also"></a>Vea también

[Información sobre los servicios de protección de última generación](next-generation-protection.md)
