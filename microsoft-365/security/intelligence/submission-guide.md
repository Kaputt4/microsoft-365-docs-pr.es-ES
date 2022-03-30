---
title: Enviar archivos para su análisis por Microsoft
description: Obtenga información sobre cómo enviar archivos a Microsoft para análisis de malware, cómo realizar un seguimiento de los envíos y detecciones de disputas.
ms.reviewer: ''
keywords: security, sample submission help, malware file, virus file, trojan file, submit, send to Microsoft, submit a sample, virus, trojan, worm, undetected, doesn't detect, email microsoft, email malware, I think this is malware, I think it's a virus, where can I send a virus, is this a virus, MSE, doesn't detect, no signature, no detection, suspect file,  MMPC, Centro de protección contra malware de Microsoft, investigadores, analistas, WDSI, inteligencia de seguridad
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
ms.openlocfilehash: 78f1e00555d36880f24f05d213f42725f4ac0133
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2022
ms.locfileid: "63680320"
---
# <a name="submit-files-for-analysis"></a>Enviar archivos para su análisis

Si tiene un archivo que sospecha que puede ser malware o que se está detectando incorrectamente, puede enviarlo para su análisis. Esta página tiene respuestas a algunas preguntas comunes sobre cómo enviar un archivo para su análisis.

## <a name="how-do-i-send-a-malware-file-to-microsoft"></a>¿Cómo envío un archivo de malware a Microsoft?

Puede enviarnos archivos que cree que pueden ser malware o archivos que se han detectado incorrectamente a través del [portal de envío de ejemplo](https://www.microsoft.com/en-us/wdsi/filesubmission).

Recibimos un gran número de muestras de muchos orígenes. Nuestro análisis se prioriza por el número de detecciones de archivos y el tipo de envío. Puede ayudarnos a completar un análisis rápido proporcionando información detallada sobre el producto que estaba usando y lo que estaba haciendo cuando encontró el archivo.

Después de iniciar sesión, podrá realizar un seguimiento de los envíos.

## <a name="can-i-send-a-sample-by-email"></a>¿Puedo enviar un ejemplo por correo electrónico?

No, solo aceptamos envíos a través de nuestro [portal de envío de ejemplo](https://www.microsoft.com/en-us/wdsi/filesubmission).

## <a name="can-i-submit-a-sample-without-signing-in"></a>¿Puedo enviar un ejemplo sin iniciar sesión?

No. Si es un cliente de empresa, debe iniciar sesión para que podamos priorizar el envío correctamente. Si actualmente está experimentando un brote de virus o un incidente relacionado con la seguridad, debe ponerse en contacto con el profesional de soporte técnico de Microsoft designado o ir al Soporte técnico de [Microsoft](https://support.microsoft.com/) para obtener asistencia inmediata.

## <a name="what-is-the-software-assurance-id-said"></a>¿Qué es el identificador de Software Assurance (SAID)?

El [id. de Software Assurance (SAID)](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx) es para que los clientes empresariales realicen un seguimiento de los derechos de soporte técnico. El portal de envío acepta y conserva la información de SAID y permite a los clientes con SAID válidos realizar envíos de mayor prioridad.

### <a name="how-do-i-dispute-the-detection-of-my-program"></a>¿Cómo puedo impugnar la detección de mi programa?

[Envíe el archivo en](https://www.microsoft.com/en-us/wdsi/filesubmission) cuestión como desarrollador de software. Espere hasta que el envío tenga una determinación final.

Si no está satisfecho con nuestra determinación del envío, use el formulario de contacto para desarrolladores proporcionado con los resultados del envío para llegar a Microsoft. Usaremos la información que proporciones para investigar más si es necesario.

Animamos a todos los proveedores de software y desarrolladores a leer acerca de cómo [Microsoft identifica el malware y el software no deseado](criteria.md).

## <a name="how-do-i-track-or-view-past-sample-submissions"></a>¿Cómo puedo realizar un seguimiento o ver los envíos de ejemplo anteriores?

Puede realizar un seguimiento de los envíos a través de la página [historial de envíos](https://www.microsoft.com/en-us/wdsi/submissionhistory).

## <a name="what-does-the-submission-status-mean"></a>¿Qué significa el estado de envío?

Cada envío se muestra en uno de los siguientes tipos de estado:

* Enviado: se ha recibido el archivo

* En curso: un analista ha comenzado a comprobar el archivo

* Cerrado: un analista ha dado una determinación final

Puede ver el estado de los archivos que nos envíe en la página historial [de envíos](https://www.microsoft.com/en-us/wdsi/submissionhistory).

## <a name="how-does-microsoft-prioritize-submissions"></a>Cómo prioriza Microsoft los envíos

El procesamiento de envíos toma un recurso de analista dedicado. Dado que recibimos regularmente un gran número de envíos, los administramos en función de una prioridad. Los siguientes factores afectan a la forma en que priorizamos los envíos:

* Se priorizan los archivos que pueden afectar a un gran número de equipos.

* Los clientes autenticados, especialmente los clientes empresariales con identificadores de [Software Assurance (SAID) válidos](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx), tienen prioridad.

* Los envíos marcados como de alta prioridad por los titulares de SAID reciben atención inmediata.

Nuestros sistemas examinan inmediatamente el envío para darle la última determinación incluso antes de que un analista comience a administrar su caso. Tenga en cuenta que es posible que un analista ya haya procesado el mismo archivo. Para comprobar si hay actualizaciones en la determinación, seleccione volver a examinar en la página de detalles del envío.
