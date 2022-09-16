---
title: Envío de archivos para su análisis por Parte de Microsoft
description: Obtenga información sobre cómo enviar archivos a Microsoft para el análisis de malware, cómo realizar un seguimiento de los envíos y las detecciones de disputas.
ms.reviewer: ''
keywords: seguridad, ayuda de envío de ejemplo, archivo de malware, archivo de virus, archivo troyano, enviar, enviar a Microsoft, enviar una muestra, virus, troyano, gusano, no detectado, no detecta, correo electrónico microsoft, malware de correo electrónico, creo que se trata de malware, creo que es un virus, donde puedo enviar un virus, es este un virus, MSE, no detecta, sin firma, sin detección, archivo sospechoso,  MMPC, Centro de protección contra malware de Microsoft, investigadores, analista, WDSI, inteligencia de seguridad
ms.service: microsoft-365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.localizationpriority: medium
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 778fd439c7c886be558eaf058ae941267bf0d52c
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2022
ms.locfileid: "67736020"
---
# <a name="submit-files-for-analysis"></a>Enviar archivos para su análisis

Si tiene un archivo que sospecha que puede ser malware o se está detectando incorrectamente, puede enviarlo a nosotros para su análisis. Esta página tiene respuestas a algunas preguntas comunes sobre el envío de un archivo para su análisis.

## <a name="how-do-i-submit-a-file-to-microsoft-for-analysis"></a>Cómo enviar un archivo a Microsoft para su análisis?

### <a name="send-a-malware-file"></a>Envío de un archivo de malware

Puede enviar archivos que cree que podrían ser malware o archivos que se han detectado incorrectamente a través del [portal de envío de ejemplo](https://www.microsoft.com/wdsi/filesubmission).

Puede completar un análisis rápido proporcionando información detallada sobre el producto que estaba usando y lo que estaba haciendo cuando encontró el archivo.

Después de iniciar sesión, podrá realizar un seguimiento de los envíos.

> [!NOTE]
>
> Puede usar la característica de envío WDSI incluso si no tiene Microsoft Defender para punto de conexión Plan 2 o Microsoft Defender para Office Plan 2.

### <a name="submit-a-suspected-email-attachment"></a>Envío de datos adjuntos de correo electrónico sospechosos

Use el [portal de Microsoft 365 Defender](https://security.microsoft.com/) para enviar datos adjuntos de correo electrónico sospechosos a Microsoft para su revisión. Para obtener más información, consulte [Envío de datos adjuntos de correo electrónico sospechosos a Microsoft](../office-365-security/admin-submission.md).

### <a name="submit-a-file-or-file-hash"></a>Envío de un archivo o hash de archivo

Use la característica de envíos unificados en Microsoft Defender para punto de conexión para enviar archivos y hash de archivos a Microsoft para su revisión. Para obtener más información, consulte [Envío de archivos en Microsoft Defender para punto de conexión](../defender-endpoint/admin-submissions-mde.md).

## <a name="can-i-send-a-sample-by-email"></a>¿Puedo enviar un ejemplo por correo electrónico?

No, solo aceptamos envíos a través de nuestro [portal de envío de ejemplo](https://www.microsoft.com/wdsi/filesubmission).

## <a name="can-i-submit-a-sample-without-signing-in"></a>¿Puedo enviar un ejemplo sin iniciar sesión?

No. Si es un cliente empresarial, debe iniciar sesión para que podamos priorizar el envío de forma adecuada. Si actualmente está experimentando un brote de virus o un incidente relacionado con la seguridad, debe ponerse en contacto con el profesional de soporte técnico de Microsoft designado o ir a [Soporte técnico de Microsoft](https://support.microsoft.com/) para obtener ayuda inmediata.

## <a name="what-is-the-software-assurance-id-said"></a>¿Qué es el identificador de Software Assurance (SAID)?

El [identificador de Software Assurance (SAID)](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx) es para que los clientes empresariales realicen un seguimiento de los derechos de soporte técnico. El portal de envío acepta y conserva la información de SAID y permite a los clientes con SAID válidos realizar envíos de mayor prioridad.

### <a name="how-do-i-dispute-the-detection-of-my-program"></a>Cómo disputa la detección de mi programa?

[Envíe el archivo](https://www.microsoft.com/wdsi/filesubmission) en cuestión como desarrollador de software. Espere hasta que su envío tenga una determinación final.

Si no está satisfecho con nuestra determinación del envío, use el formulario de contacto para desarrolladores que se proporciona con los resultados del envío para llegar a Microsoft. Usaremos la información que proporcione para investigar más si es necesario.

Animamos a todos los proveedores y desarrolladores de software a leer sobre [cómo Microsoft identifica el malware y el software no deseado](criteria.md).

## <a name="how-do-i-track-or-view-past-sample-submissions"></a>Cómo realizar un seguimiento o ver los envíos de ejemplo anteriores?

Puede realizar un seguimiento de los envíos a través de la [página del historial de envíos](https://www.microsoft.com/wdsi/submissionhistory).

## <a name="what-does-the-submission-status-mean"></a>¿Qué significa el estado del envío?

Se muestra que cada envío está en uno de los siguientes tipos de estado:

* Enviado: se ha recibido el archivo.

* En curso: un analista ha empezado a comprobar el archivo.

* Cerrada: un analista ha dado una determinación final.

Puede ver el estado de los archivos que nos envíe en la página del [historial de envíos](https://www.microsoft.com/wdsi/submissionhistory).

## <a name="how-does-microsoft-prioritize-submissions"></a>¿Cómo prioriza Microsoft los envíos?

El procesamiento de envíos toma un recurso de analista dedicado. Dado que recibimos regularmente un gran número de envíos, los gestionamos en función de una prioridad. Los siguientes factores afectan a la forma en que priorizamos los envíos:

* Se priorizan los archivos frecuentes con el potencial de afectar a un gran número de equipos.

* A los clientes autenticados, especialmente a los clientes [empresariales con identificadores de Software Assurance (SAID) válidos](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx), se les da prioridad.

* Los envíos marcados como de alta prioridad por los titulares de SAID reciben atención inmediata.

Nuestros sistemas examinan inmediatamente su envío para proporcionarle la determinación más reciente incluso antes de que un analista empiece a controlar su caso. Tenga en cuenta que es posible que un analista ya haya procesado el mismo archivo. Para comprobar si hay actualizaciones de la determinación, seleccione Volver a examinar en la página de detalles del envío.
