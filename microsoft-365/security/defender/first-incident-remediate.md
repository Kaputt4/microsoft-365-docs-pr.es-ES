---
title: Paso 2. Corrección del primer incidente
description: Cómo empezar a corregir el primer incidente en Microsoft 365 Defender.
keywords: incidentes, alertas, investigación, correlación, ataque, máquinas, dispositivos, usuarios, identidades, identidad, buzón de correo electrónico, 365, microsoft, m365, respuesta a incidentes, ciberataque
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365solution-firstincident
- highpri
- tier1
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 9352f54e54966850484caf2b3a116710c41b248a
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68060876"
---
# <a name="step-2-remediate-your-first-incident"></a>Paso 2. Corrección del primer incidente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**
- Microsoft 365 Defender

Microsoft 365 Defender no solo proporciona capacidades de detección y análisis, sino que también proporciona contención y erradicación de malware. La contención incluye pasos para reducir el impacto del ataque, mientras que la erradicación garantiza que todos los seguimientos de la actividad del atacante se quiten de la red. Microsoft 365 Defender ofrece varias acciones de corrección que se pueden configurar para [corregir automáticamente](m365d-autoir.md) en función del sistema operativo de los dispositivos afectados y del tipo de ataque.

Microsoft 365 Defender ofrece varias acciones de corrección que los analistas pueden iniciar manualmente. Las acciones se dividen en dos categorías: Acciones en dispositivos y acciones en archivos. Algunas acciones se pueden usar para detener inmediatamente la amenaza, mientras que otras acciones ayudan en un análisis forense adicional.

## <a name="actions-on-devices"></a>Acciones en dispositivos

- **Aislar el dispositivo** : esta actividad bloquea inmediatamente todo el tráfico de red (internet e interno) para minimizar la propagación de malware y permitir que los analistas continúen el análisis sin que un actor malintencionado pueda continuar con un ataque. La única conexión permitida es a la nube del servicio Microsoft Defender for Identity, por lo que Microsoft Defender for Identity puede seguir supervisando el dispositivo. 
- **Restringir la ejecución** de aplicaciones: para restringir la ejecución de una aplicación, se aplica una directiva de integridad de código que solo permite ejecutar archivos si están firmados por un certificado emitido por Microsoft. Este método de restricción puede ayudar a evitar que un atacante controle dispositivos en peligro y realice otras actividades malintencionadas.
- **Ejecutar examen antivirus**: un examen Microsoft Defender Antivirus puede ejecutarse junto con otras soluciones antivirus, independientemente de si Antivirus de Defender es la solución antivirus activa o no. Si otro producto de proveedor de antivirus es la solución de endpoint protection principal, puede ejecutar Antivirus de Defender en modo pasivo.
- **Iniciar investigación automatizada** : puede iniciar una nueva investigación automatizada de uso general en el dispositivo. Mientras se ejecuta una investigación, cualquier otra alerta generada desde el dispositivo se agregará a una investigación automatizada en curso hasta que se complete esa investigación. Además, si se ve la misma amenaza en otros dispositivos, esos dispositivos se agregan a la investigación.
- **Iniciar respuesta en directo** : la respuesta en directo es una funcionalidad que proporciona acceso instantáneo a un dispositivo mediante una conexión de shell remoto. Esto le ofrece la capacidad de realizar un trabajo de investigación en profundidad y tomar medidas de respuesta inmediatas para contener rápidamente amenazas identificadas en tiempo real. La respuesta en directo está diseñada para mejorar las investigaciones, ya que le permite recopilar datos forenses, ejecutar scripts, enviar entidades sospechosas para su análisis, corregir amenazas y buscar amenazas emergentes de forma proactiva.
- **Recopilar paquete de investigación** : como parte del proceso de investigación o respuesta, puede recopilar un paquete de investigación de un dispositivo. Al recopilar el paquete de investigación, puede identificar el estado actual del dispositivo y comprender aún más las herramientas y técnicas usadas por el atacante. 
- **Consulte a un experto en amenazas** (disponible en Acciones en dispositivos y archivos): puede consultar a un experto en amenazas de Microsoft para obtener más información sobre dispositivos potencialmente comprometidos o dispositivos que ya están en peligro. Los expertos en amenazas de Microsoft pueden participar directamente desde dentro de Microsoft 365 Defender para obtener una respuesta oportuna y precisa. 

## <a name="actions-on-files"></a>Acciones en archivos

- **Detener y poner en cuarentena el archivo** : esta acción incluye la detención de procesos en ejecución, la cuarentena de archivos y la eliminación de datos persistentes, como las claves del Registro. Esta acción surte efecto en dispositivos con Windows 11 o Windows 10, versión 1703 o posterior, donde se observó el archivo en los últimos 30 días. 
- **Agregar indicadores para bloquear o permitir archivos** : evite la propagación de un ataque en su organización mediante la prohibición de archivos potencialmente malintencionados o sospechas de malware. Esta operación impedirá que el archivo se lea, escriba o ejecute en dispositivos de su organización.
- **Descargar o recopilar archivos** : esta acción permite a los analistas descargar un archivo en un archivo de archivo .zip protegido con contraseña para su posterior análisis por parte de la organización.
- **Análisis profundo** : esta acción ejecuta un archivo en un entorno de nube seguro y totalmente instrumentado. Los resultados de análisis profundos muestran las actividades del archivo, los comportamientos observados y los artefactos asociados, como archivos eliminados, modificaciones del Registro y comunicación con direcciones IP. 

Continuando con el ejemplo de [Detectar, evaluar y analizar incidentes](first-incident-analyze.md#analyze-your-first-incident), un analista puede corregir este incidente con estas acciones:

1. Restablecer inmediatamente la contraseña de la cuenta de usuario
2. Aislar el dispositivo en Microsoft 365 Defender hasta que se complete el análisis profundo
3. Asegúrese de que el archivo malintencionado se puso en cuarentena desde SharePoint
4. Comprobación de qué puntos de conexión se vieron afectados por malware
5. Recompilación de sistemas
6. Buscar alertas de Microsoft Defender for Cloud Apps similares para otros usuarios
7. Creación de un indicador personalizado en Microsoft Defender para punto de conexión para bloquear una dirección IP de Tor
8. Cree una acción de gobernanza en Microsoft Defender for Cloud Apps para este tipo de alerta, como las que se muestran en la siguiente imagen:

   :::image type="content" source="../../media/first-incident-remediate/first-incident-mcas-governance.png" alt-text="Acciones de gobernanza en el portal de Microsoft Defender for Cloud Apps" lightbox="../../media/first-incident-remediate/first-incident-mcas-governance.png":::

La mayoría de las acciones de corrección se pueden aplicar y realizar un seguimiento en Microsoft 365 Defender.

## <a name="using-playbooks"></a>Uso de cuadernos de estrategias

Además, la corrección automatizada se puede crear mediante cuadernos de estrategias. Actualmente, Microsoft tiene [plantillas de cuaderno de estrategias en GitHub](https://github.com/microsoft/Microsoft-Cloud-App-Security/tree/master/Playbooks) que proporcionan cuadernos de estrategias para los siguientes escenarios:

- Eliminación del uso compartido de archivos confidenciales después de solicitar la validación del usuario
- Evaluación automática de alertas de país poco frecuentes
- Solicitud de acción del administrador antes de deshabilitar una cuenta
- Deshabilitar reglas de bandeja de entrada malintencionadas

Los cuadernos de estrategias usan Power Automate para crear flujos de automatización de procesos robóticos personalizados para automatizar ciertas actividades una vez que se han desencadenado criterios específicos. Las organizaciones pueden crear cuadernos de estrategias a partir de plantillas existentes o desde cero. 

Por ejemplo:
 
:::image type="content" source="../../media/first-incident-remediate/first-incident-power-automate.png" alt-text="Flujo de automatización de procesos robóticos personalizados de Power Automate" lightbox="../../media/first-incident-remediate/first-incident-power-automate.png"::: 
 
Los cuadernos de estrategias también se pueden crear durante la [revisión posterior a los incidentes](first-incident-post.md) para crear acciones de corrección a partir de incidentes resueltos. 

## <a name="next-step"></a>Paso siguiente

Obtenga información sobre cómo [realizar una revisión posterior al incidente de un incidente](first-incident-post.md).

## <a name="see-also"></a>Vea también

- [Información general sobre incidentes](incidents-overview.md)
- [Investigar incidentes](investigate-incidents.md)
- [Administrar incidentes](manage-incidents.md)
