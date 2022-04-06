---
title: Envío de archivos para su análisis por Parte de Microsoft
description: Obtenga información sobre cómo enviar archivos a Microsoft para el análisis de malware, cómo realizar un seguimiento de los envíos y las detecciones de disputas.
ms.reviewer: ''
keywords: seguridad, ayuda de envío de ejemplo, archivo de malware, archivo de virus, archivo troyano, enviar, enviar a Microsoft, enviar una muestra, virus, troyano, gusano, no detectado, no detecta, correo electrónico microsoft, malware de correo electrónico, creo que se trata de malware, creo que es un virus, donde puedo enviar un virus, es este un virus, MSE, no detecta, sin firma, sin detección, archivo sospechoso,  MMPC, Centro de protección contra malware de Microsoft, investigadores, analista, WDSI, inteligencia de seguridad
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: df2ab2b2019bb76af49f00d2751cdc76848705d1
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64663608"
---
# <a name="submit-files-for-analysis"></a>Enviar archivos para su análisis

Si tiene un archivo que sospecha que puede ser malware o se está detectando incorrectamente, puede enviarlo a nosotros para su análisis. Esta página tiene respuestas a algunas preguntas comunes sobre el envío de un archivo para su análisis.

## <a name="how-do-i-send-a-malware-file-to-microsoft"></a>Cómo enviar un archivo de malware a Microsoft?

Puede enviarnos archivos que cree que pueden ser malware o archivos que se han detectado incorrectamente a través del [portal de envío de ejemplo](https://www.microsoft.com/wdsi/filesubmission).

Recibimos un gran número de muestras de muchos orígenes. Nuestro análisis se prioriza por el número de detecciones de archivos y el tipo de envío. Puede ayudarnos a completar un análisis rápido proporcionando información detallada sobre el producto que estaba usando y lo que estaba haciendo cuando encontró el archivo.

Después de iniciar sesión, podrá realizar un seguimiento de los envíos.

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
