---
title: Seguimiento y respuesta a amenazas de seguridad emergentes con la vista de campañas en Microsoft Defender para Office 365
description: Tutorial de campañas de amenazas dentro de Microsoft Defender para Office 365 para demostrar cómo se pueden usar para investigar un ataque de correo electrónico coordinado contra su organización.
search.product: ''
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.technology: mdo
search.appverid: met150
ms.openlocfilehash: 79ff9f29b37dca665635a9728567c78d0b945435
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67686282"
---
# <a name="track-and-respond-to-emerging-threats-with-campaigns-in-microsoft-defender-for-office-365"></a>Seguimiento y respuesta a amenazas emergentes con campañas en Microsoft Defender para Office 365

Las campañas se pueden usar para realizar un seguimiento y responder a amenazas emergentes, ya que las campañas permiten investigar un ataque de correo electrónico coordinado contra su organización. A medida que las nuevas amenazas se dirigen a su organización, Microsoft Defender para Office 365 detectará y correlacionará automáticamente los mensajes malintencionados. 

## <a name="what-you-will-need"></a>Lo que necesitará
- Microsoft Defender para Office 365 Plan 2 (incluido en los planes E5).
- Permisos suficientes (rol lector de seguridad).
- De cinco a diez minutos para realizar estos pasos.

## <a name="what-is-a-campaign-in-microsoft-defender-for-office-365"></a>¿Qué es una campaña en Microsoft Defender para Office 365

Una campaña es un ataque de correo electrónico coordinado contra una o varias organizaciones. Email ataques que roban credenciales y datos de la empresa son un sector grande y lucrativo. A medida que las tecnologías para detener los ataques aumentan y se multiplican, los atacantes modifican sus métodos para continuar su éxito.

Microsoft aprovecha grandes cantidades de datos anti-phishing, antispam y antimalware en todo el servicio para ayudar a identificar campañas. Analizamos y clasificamos la información de ataque según varios factores, por ejemplo:

- **Origen de ataque**: las direcciones IP de origen y los dominios de correo electrónico del remitente.
- **Propiedades del mensaje**: contenido, estilo y tono de los mensajes.
- **Destinatarios de mensajes**: cómo se relacionan los destinatarios, por ejemplo, los dominios de destinatario, las funciones de trabajo del destinatario (como administradores y ejecutivos), los tipos de empresa (como grandes, pequeños, públicos y privados) y los sectores.
- **Carga de ataque**: vínculos malintencionados, datos adjuntos u otras cargas en los mensajes.

Una campaña puede ser de corta duración o puede abarcar varios días, semanas o meses con períodos activos e inactivos. Es posible que se inicie una campaña en su organización específica o que su organización forme parte de una campaña más grande en *varias* empresas.

> [!TIP]
> Para obtener más información sobre los datos disponibles en una campaña, lea [Vistas de campaña en Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/campaigns).

## <a name="watch-the-exploring-campaign-views-video"></a>Vea el vídeo *Exploración de vistas de campaña*

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGBL8]

## <a name="investigating-a-suspicious-email-campaign-using-threat-reports"></a>Investigación de una campaña de correo electrónico sospechosa mediante informes de amenazas

En caso de que una campaña se haya dirigido a su organización y le gustaría obtener más información sobre el impacto: 
1. Vaya a la [página](https://security.microsoft.com/campaigns) de la campaña.
1. Seleccione el nombre de la campaña que desea investigar. 
1. Al abrir el control flotante, seleccione **Descargar informe de amenazas**.
1. Abra el informe de amenazas y proporcionará más información sobre la campaña. La información del informe incluye: 
- **Resumen ejecutivo:** Resumen de alto nivel del tipo de campaña y el número de usuarios destinados en su organización. 
- **Análisis:** Gráfico de escala de tiempo de cuándo se inició la campaña, el recuento de mensajes dirigidos a su organización y el destino y los veredictos de los mensajes. 
- **Origen del ataque:** Principales direcciones IP y dominios de envío con un recuento de mensajes que se entregaron a las bandejas de entrada de la organización. Esto le permite investigar quién se dirige a su organización. 
- **Email plantilla y carga útil:** la línea de asunto de los correos electrónicos que formaban parte de la campaña y las direcciones URL (y su frecuencia) presentes como parte de la campaña.
- **Recomendaciones:** Recomendaciones para los pasos siguientes para corregir los mensajes.

## <a name="investigate-inboxed-messages-that-are-part-of-a-email-threat-campaign"></a>Investigación de mensajes bandeja de entrada que forman parte de una campaña de amenazas por correo electrónico

1. Vaya a la [página](https://security.microsoft.com/campaigns) de la campaña.
1. Desplácese por la lista de campañas en la **vista Detalles**, debajo del gráfico.
1. Seleccione el nombre de la campaña que desea investigar. Si la campaña tiene un recuento de clics de más de cero, esto indica que un usuario de su organización ha hecho clic en una dirección URL o ha descargado un archivo del correo electrónico.
1. El control flotante de la campaña muestra más información sobre la campaña, el gráfico muestra una escala de tiempo de la campaña de principio a fin de la campaña y el diagrama de flujo horizontal muestra las fases de la campaña desde su origen, el veredicto y la ubicación actual de los mensajes.
1. Debajo del diagrama de flujo, seleccione la pestaña **Clics de dirección URL** para mostrar información sobre el clic. Aquí puede ver el usuario que ha hecho clic en una dirección URL, si el usuario está etiquetado como usuario de cuenta de prioridad, la propia dirección URL y la hora de clic. 
1. Si desea obtener más información sobre los mensajes bandeja de entrada y en los que se ha hecho clic, seleccione **Explorar mensajes** > **bandeja de entrada**. Se abrirá una nueva pestaña y navegará al Explorador de amenazas. 
1. En la **vista de detalles** del Explorador, puede hacer referencia a **la entrega más reciente** para determinar si un mensaje sigue en la bandeja de entrada o si el sistema ZAP ha movido a la cuarentena. _Para obtener más detalles sobre el mensaje específico, seleccione el mensaje. El control flotante proporciona información adicional. Al seleccionar la **página Abrir entidad de correo electrónico** en la parte superior izquierda del control flotante, se abrirá una nueva pestaña que le proporcionará más información sobre el mensaje._
1.  Si desea realizar una acción y sacar los mensajes de la bandeja de entrada, puede seleccionar el mensaje y, a continuación, seleccionar **Acciones** >  de mensaje **Mover a la carpeta no deseada**. Esto garantizará que el usuario no siga interactuando con el mensaje malintencionado que podría dar lugar a una posible vulneración. 

## <a name="next-steps"></a>Pasos siguientes

Para obtener más información, lea [Vistas de campaña en Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/campaigns).
