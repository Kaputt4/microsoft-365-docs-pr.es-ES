---
title: 'Protección proporcionada en la nube Antivirus de Microsoft Defender: envío de muestra'
description: Obtenga información sobre la protección y la protección entregadas en la nube Antivirus de Microsoft Defender
keywords: Antivirus de Microsoft Defender, tecnologías de última generación, envío de ejemplo antivirus, av de próxima generación, aprendizaje automático, antimalware, seguridad, defender, nube, protección entregada en la nube
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: jweston-1
ms.author: v-jweston
ms.reviewer: shwjha
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 07/22/2021
ms.openlocfilehash: 2d30777754f05b46336e28c237b2264cef6ac802
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2021
ms.locfileid: "53622285"
---
# <a name="cloud-delivered-protection-antivirus-sample-submission"></a>Envío de ejemplo de antivirus de protección entregado en la nube

Microsoft Defender para Endpoint Antivirus (Defender para endpoint antivirus) usa muchos mecanismos inteligentes para detectar malware. Una de las capacidades más eficaces es la capacidad de aplicar la potencia de la nube para detectar malware. Defender for Endpoint antivirus Cloud Protection funciona con el antivirus defender para endpoints en el punto de conexión para tomar decisiones y proteger los puntos de conexión de amenazas nuevas y emergentes.

## <a name="microsoft-defender-for-endpoint-antivirus-cloud-protection-overview"></a>Introducción a la protección en la nube de Microsoft Defender para Endpoint Antivirus

La protección en la nube está habilitada de forma predeterminada en Defender para Endpoint Antivirus. Se recomienda que los clientes no deshabiliten la protección en la nube en Defender para Endpoint Antivirus.  Cuando la protección en la nube está habilitada, tiene la opción de configurar la información que defender para el antivirus de extremo proporcionará a la nube (incluido el envío de ejemplo). La protección en la nube habilitada es útil cuando no se puede tomar una determinación de elevada confianza en función de otras características.
La configuración del envío de ejemplo genera preguntas sobre cómo funciona; por ejemplo, cómo se almacenan y usan los datos. Las tres opciones de envío de ejemplo de protección en la nube que más preguntas plantean son:

- "Enviar muestras seguras automáticamente", (el comportamiento predeterminado)
- "Enviar todos los ejemplos automáticamente",  
- "No enviar muestras".  

Para obtener información sobre las opciones de configuración mediante Intune, Configuration Manager, GPO o PowerShell, vea Activar la protección entregada en la [nube en Antivirus de Microsoft Defender](/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus).  

## <a name="customer-data-cloud-protection-and-sample-submission"></a>Datos del cliente, protección en la nube y envío de ejemplo

Al incorporarse a Defender for Endpoint, Defender for Endpoint trata todos los ejemplos de archivos como datos de cliente, respetando las opciones de retención geográfica y de datos que el cliente seleccionó. Las opciones de retención geográfica y de datos se describen aquí: [Microsoft Defender para el almacenamiento de datos de extremo y la privacidad.](/security/defender-endpoint/data-storage-privacy#data-storage-location)
El producto ha recibido varias certificaciones de cumplimiento, lo que demuestra el cumplimiento continuo de un sofisticado conjunto de controles de cumplimiento:

- ISO 27001
- ISO 27018
- SOC I, II, III
- y PCI

[Las ofertas de cumplimiento de Azure](/azure/compliance/#compliance-offerings) proporcionan más información sobre estas certificaciones. Todos los artefactos de certificación de Microsoft Defender para endpoint se pueden encontrar en el [Portal](https://servicetrust.microsoft.com/) de confianza de servicio de Microsoft en cada uno de los informes de certificación de Azure asociados.

## <a name="cloud-protection-mechanisms"></a>Mecanismos de protección en la nube

Microsoft Intelligent Security Graph los datos de amenazas de una amplia red de sensores. Se capa de modelos de aprendizaje automático basados en la nube que pueden realizar una evaluación en función de las señales del cliente y la amplia red de sensores y datos en el servicio de seguridad inteligente Graph. Este modelo ofrece a Defender for Endpoint la capacidad de bloquear muchas amenazas nunca antes vistas.

Defender for Endpoint antivirus and cloud protection bloquea automáticamente la mayoría de las amenazas nuevas y nunca vistas a primera vista mediante los siguientes métodos:

1. Modelos de aprendizaje automático ligeros basados en cliente, que bloquean malware nuevo y desconocido.

2. Análisis de comportamiento local, detención de ataques basados en archivos y sin archivos.

3. Antivirus de alta precisión, que detecta malware común a través de técnicas heurísticas y genéricas.

4. La protección avanzada basada en la nube se proporciona para los casos en los que el antivirus de Defender for Endpoint que se ejecuta en el punto de conexión necesita más inteligencia para comprobar la intención de un archivo sospechoso.

   1. En caso de que el antivirus de Microsoft Defender para endpoint no pueda tomar una determinación clara, los metadatos de archivo se envían al servicio de protección en la nube. Normalmente, el servicio de protección en la nube puede determinar si el archivo es seguro o malintencionado, en milisegundos.  
      - La consulta en la nube de metadatos de archivo puede ser el resultado del comportamiento, la marca de la web u otras características en las que no se determina un veredicto claro.
      - Se envía una pequeña carga de metadatos, con el objetivo de alcanzar un veredicto de malware contra limpio
      - Los metadatos pueden incluir atributos PE, atributos de archivo estáticos, atributos dinámicos y contextuales, y más (figura 1).
      - No incluye información de identificación personal (PII). La información, como los nombres de archivo, se aplica hash
      - Puede ser sincrónico o asincrónico. Para sincrónico, el archivo no se abrirá hasta que la nube represente un veredicto. Para los asincrónicos, el archivo se abrirá mientras la nube realiza su análisis.

   2. Después de examinar los metadatos, si la protección en la nube de Defender for Endpoint antivirus no puede llegar a un veredicto concluyente, puede solicitar una muestra del archivo para su posterior inspección. Esta solicitud respeta la configuración de configuración para el envío de ejemplo:

      1. **Enviar muestras seguras automáticamente** (valor predeterminado)
         - Caja fuerte ejemplos son ejemplos que se consideran que no contienen normalmente datos de PII como: .bat, .scr, .dll, .exe.
         - Si es probable que el archivo contenga PII, el usuario recibirá una solicitud para permitir el envío de ejemplo de archivo.
         - Este es el valor predeterminado en Windows, macOS y Linux.

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

   3. Después de enviar metadatos y/o archivos a la nube de Defender for Endpoint, puede usar **ejemplos,** **detonaciones** o modelos de aprendizaje automático de análisis de big **data** para llegar a un veredicto. Este modelo se muestra en la figura 3. Desactivar la protección entregada en la nube limitará el análisis solo a lo que el cliente puede proporcionar a través de modelos de aprendizaje automático locales y funciones similares.

_Figura 1: Ejemplos de metadatos enviados a Microsoft Defender Cloud Protection_

:::image type="content" source="images/cloud-protection-metadata-sample.png" alt-text="Figura 1. Ejemplos de metadatos enviados a Microsoft Defender Cloud Protection":::

_Figura 2. Flujo de protección entregado en la nube_

:::image type="content" source="images/cloud-protection-flow.png" alt-text="Figura 2. Flujo de protección entregado en la nube":::

_Figura 3. Protección entregada en la nube y aprendizaje automático en capas_

:::image type="content" source="images/cloud-protection-detection-layered-machine-learning.png" lightbox="images/cloud-protection-detection-layered-machine-learning.png" alt-text="Figura 3. Protección entregada en la nube y aprendizaje automático en capas":::

> [!Note]
>
> Es posible que también haya escuchado la frase "Bloquear a primera vista (BAFS)". BAFS hace referencia al análisis más amplio que la nube puede proporcionar, incluidos aspectos como la detonación para proporcionar un veredicto más preciso. Esto también puede incluir retrasar la apertura de un archivo que está siendo interrogado por la protección de la nube hasta que se llegue a un veredicto. Si deshabilita "Envío de ejemplo", BAFS está deshabilitado y no puede realizar el análisis más extenso y se limita a analizar solo metadatos de archivo.

## <a name="cloud-delivered-protection-levels"></a>Niveles de protección entregados en la nube

La detección de malware requiere lograr un equilibrio entre proporcionar la protección más sólida posible, al tiempo que se minimiza el número de falsos positivos. Diferentes entornos pueden tener tolerancia a la protección frente al riesgo de falso positivo. Los niveles de protección entregados en la nube permiten al cliente definir el nivel de tolerancia adecuado para el entorno específico. Al habilitar la protección entregada en la nube, el nivel de protección se configura automáticamente para proporcionar una detección segura sin aumentar el riesgo de detectar archivos legítimos. Si desea configurar un nivel de protección diferente, consulte [Specify the cloud-delivered protection level for Antivirus de Microsoft Defender](/security/threat-protection/microsoft-defender-antivirus/specify-cloud-protection-level-microsoft-defender-antivirus).  

> [!Note]
>
> Cambiar el nivel de protección puede dar como resultado un mayor nivel de falsos positivos y debe evaluarse cuidadosamente antes de cambiar.

## <a name="other-file-sample-submission-scenarios"></a>Otros escenarios de envío de ejemplo de archivo

Hay dos escenarios más en los que Defender for Endpoint puede solicitar un ejemplo de archivo que no está relacionado con la configuración de protección en la nube descrita anteriormente.  

### <a name="manual-file-sample-collection-by-security-admin-from-defender-for-endpoint-management-portal"></a>Colección manual de ejemplos de archivos por parte del administrador de seguridad de Defender for Endpoint Management Portal

Al incorporar dispositivos a Microsoft Defender para endpoint EDR hay una configuración para habilitar colecciones de muestras desde el dispositivo, que puede confundirse con la configuración descrita anteriormente. Esta configuración controla la colección de muestras de archivos de dispositivos cuando se solicita a través del portal administrativo defender para endpoint; está sujeto a los roles y permisos ya establecidos. Esta configuración puede permitir o bloquear la colección de archivos desde el punto de conexión para características como el análisis profundo en el portal de Defender for Endpoint. Si esta configuración no está configurada, el valor predeterminado es habilitar la colección de muestras.

[Defender adicional para la configuración de extremo Configuración](/configure-endpoints#additional-defender-for-endpoint-configuration-settings)

### <a name="automated-investigation-and-response-content-analysis"></a>Análisis automatizado de contenido de investigación y respuesta

Cuando las investigaciones automatizadas se ejecutan en dispositivos (cuando se configura para ejecutarse automáticamente en respuesta a una alerta o ejecutarse manualmente), los archivos identificados como sospechosos se pueden recopilar desde los puntos de conexión para una inspección posterior. La característica de análisis de contenido de archivos para investigaciones automatizadas se puede deshabilitar en el portal de Defender for Endpoint. Los nombres de extensión de archivo también se pueden modificar para agregar o quitar extensiones para otros tipos de archivo que se envían automáticamente durante una investigación automatizada.

[Administrar cargas de archivos de automatización](/manage-automation-file-uploads)
