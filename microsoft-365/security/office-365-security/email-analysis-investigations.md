---
title: análisis de Email en investigaciones para Microsoft Defender para Office 365
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- m365-security
- m365initiative-defender-office365
keywords: respuesta a incidentes automatizada, investigación, corrección, protección contra amenazas
description: Vea cómo funcionan los análisis de correo electrónico en las investigaciones en Microsoft Defender para Office 365.
ms.custom:
- air
- seo-marvel-mar2020
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 1d7c4f0f01f1aff00e36e5930fa9566e1f6a7993
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68048646"
---
# <a name="email-analysis-in-investigations-for-microsoft-defender-for-office-365"></a>análisis de Email en investigaciones para Microsoft Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Durante la investigación automatizada de alertas, Microsoft Defender para Office 365 analiza el correo electrónico original en busca de amenazas e identifica otros correos electrónicos relacionados con el correo electrónico original y potencialmente parte de un ataque. Este análisis es importante porque los ataques de correo electrónico rara vez constan de un solo correo electrónico.

El análisis de correo electrónico de la investigación automatizada identifica los clústeres de correo electrónico mediante atributos del correo electrónico original para consultar los correos electrónicos enviados y recibidos por su organización. Esto es similar a que un analista de operaciones de seguridad buscaría los correos electrónicos relacionados en explorer o advanced hunting. Se usan varias consultas para identificar los correos electrónicos coincidentes porque los atacantes suelen transformar los parámetros de correo electrónico para evitar la detección de seguridad. El análisis de agrupación en clústeres realiza estas comprobaciones para determinar cómo controlar los correos electrónicos implicados en la investigación:

- El análisis de correo electrónico crea consultas (clústeres) de correos electrónicos mediante atributos del correo electrónico original: valores de remitente (dirección IP, dominio de envío) y contenido (asunto, identificador de clúster) para encontrar correos electrónicos relacionados.
- Si el análisis de las direcciones URL y los archivos del correo electrónico original identifica que algunos son malintencionados (es decir, malware o phish), también creará consultas o clústeres de correos electrónicos que contienen la dirección URL o el archivo malintencionados.
- Email análisis de agrupación en clústeres cuenta las amenazas asociadas a los correos electrónicos coincidentes en el clúster para determinar si los correos electrónicos son malintencionados, sospechosos o no tienen amenazas claras. Si el clúster de correos electrónicos que coinciden con la consulta tiene una cantidad suficiente de spam, phish normal, phish de alta confianza o amenazas de malware, el clúster de correo electrónico obtiene ese tipo de amenaza aplicado.
- El análisis de agrupación en clústeres de correo electrónico también comprueba la ubicación de entrega más reciente del correo electrónico original y los correos electrónicos en los clústeres de correo electrónico para ayudar a identificar si es posible que los correos electrónicos todavía necesiten eliminación o ya se hayan corregido o impedido. Este análisis es importante porque los atacantes transforman contenido malintencionado más directivas de seguridad y protección pueden variar entre buzones. Esta funcionalidad conduce a situaciones en las que el contenido malintencionado puede permanecer en los buzones de correo, aunque uno o más correos electrónicos malintencionados se hayan detectado y quitado mediante la purga automática de cero horas (ZAP).
- Email clústeres que se consideran malintencionados debido al malware, la fish de alta confianza, los archivos malintencionados o las amenazas de direcciones URL malintencionadas obtendrán una acción pendiente para eliminar temporalmente los correos electrónicos cuando todavía haya en el buzón de correo en la nube (bandeja de entrada o carpeta de correo no deseado). Si los mensajes de correo electrónico malintencionados o los clústeres de correo electrónico solo son "No en el buzón" (bloqueado, en cuarentena, con errores, eliminado temporalmente, etc.) o "Local/Externo" sin ninguno en el buzón de correo en la nube, no se configurará ninguna acción pendiente para quitarlos.
- Si se determina que alguno de los clústeres de correo electrónico es malintencionado, la amenaza identificada por el clúster se aplicará de nuevo al correo electrónico original implicado en la investigación. Este comportamiento es similar al de un analista de operaciones de seguridad que usa los resultados de búsqueda de correo electrónico para determinar el veredicto de un correo electrónico original en función de los correos electrónicos coincidentes. Este resultado garantiza que, independientemente de si se detectan o no las direcciones URL, los archivos o los indicadores de correo electrónico de origen de un correo electrónico original, el sistema puede identificar correos electrónicos malintencionados que pueden eludir la detección mediante la personalización, la transformación, la evasión u otras técnicas de atacante.
- En la investigación de riesgo del usuario, se crean clústeres de correo electrónico adicionales para identificar posibles problemas de correo electrónico creados por el buzón. Este proceso incluye un clúster de correo electrónico limpio (buenos correos electrónicos del usuario, posible filtración de datos y posibles correos electrónicos de comando/control), clústeres de correo electrónico sospechosos (correos electrónicos que contienen correo no deseado o phish normal) y clústeres de correo electrónico malintencionados (correos electrónicos que contienen malware o phish de alta confianza). Estos clústeres de correo electrónico proporcionan datos de analistas de operaciones de seguridad para determinar qué otros problemas pueden necesitar solucionarse desde un peligro y visibilidad sobre qué correos electrónicos pueden haber desencadenado las alertas originales (por ejemplo, phish/spam que desencadenó restricciones de envío de usuarios).

Email análisis de agrupación en clústeres a través de consultas de entidades malintencionadas y de similitud garantiza que los problemas de correo electrónico se identifiquen y limpien por completo, incluso si solo se identifica un correo electrónico de un ataque. Puede usar vínculos desde las vistas del panel lateral de detalles del clúster de correo electrónico para abrir las consultas en explorador o búsqueda avanzada para realizar un análisis más profundo y cambiar las consultas si es necesario. Esta funcionalidad permite el refinamiento y la corrección manuales si encuentra que las consultas del clúster de correo electrónico son demasiado estrechas o demasiado amplias (incluidos los correos electrónicos no relacionados).

Estas son mejoras adicionales para el análisis de correo electrónico en las investigaciones.

## <a name="air-investigation-ignores-advanced-delivery-items-secops-mailbox-and-phishedu-messages"></a>La investigación de AIR omite los elementos de entrega avanzados (mensajes de buzón de SecOps y phishEDU)

Durante el análisis de clústeres de correo electrónico, todas las consultas de agrupación en clústeres omitirán los buzones de seguridad configurados como buzones de operaciones de seguridad en la directiva de entrega avanzada. De forma similar, las consultas de agrupación en clústeres de correo electrónico omitirán los mensajes de simulación de phish (educación) configurados en la directiva de entrega avanzada. No se muestran los valores de exclusión de SecOps ni PhishEdu en la consulta para que los atributos de agrupación en clústeres sean más sencillos y fáciles de leer. Esta exclusión garantiza que la inteligencia sobre amenazas y los buzones operativos (buzones de SecOps) y las simulaciones de phish (PhishEdu) se omiten durante el análisis de amenazas y no se quitan durante ninguna corrección.

>[!Note]
>Al abrir un clúster de correo electrónico para verlo en el Explorador desde los detalles del clúster de correo electrónico, los filtros de buzón PhishEdu y SecOps se aplicarán en el Explorador, pero no se mostrarán. Si cambia los filtros del Explorador, las fechas o actualiza la consulta dentro de la página, se quitarán las exclusiones del filtro PhishEdu/SecOps y se mostrarán de nuevo los correos electrónicos que coincidan con ellos. Si actualiza la página Explorador mediante la función de actualización del explorador, los filtros de consulta originales se volverán a cargar, incluidos los filtros PhishEdu/SecOps, pero se quitarán los cambios posteriores que haya realizado.
>

## <a name="air-updates-pending-email-action-status"></a>AIR actualiza el estado de la acción de correo electrónico pendiente

El análisis de correo electrónico de investigación calcula las amenazas y las ubicaciones del correo electrónico en el momento de la investigación para crear las pruebas y acciones de investigación. Estos datos pueden ponerse obsoletos y obsoletos cuando las acciones fuera de la investigación afectan a los correos electrónicos implicados en la investigación. Por ejemplo, la búsqueda manual de operaciones de seguridad y la corrección pueden limpiar los correos electrónicos incluidos en una investigación. Del mismo modo, las acciones de eliminación aprobadas en investigaciones paralelas o las acciones de cuarentena automática de hora cero (ZAP) pueden haber quitado correos electrónicos. Además, las detecciones retrasadas de amenazas después de la entrega de correo electrónico pueden cambiar el número de amenazas incluidas en las consultas o clústeres de correo electrónico de la investigación.

Para asegurarse de que las acciones de investigación estén actualizadas, cualquier investigación que tenga acciones pendientes volverá a ejecutar periódicamente las consultas de análisis de correo electrónico para actualizar las ubicaciones y amenazas del correo electrónico.

- Cuando cambien los datos del clúster de correo electrónico, actualizará los recuentos de amenazas y de ubicación de entrega más recientes.
- Si los correos electrónicos o el clúster de correo electrónico con acciones pendientes ya no están en el buzón de correo, se cancelará la acción pendiente y el clúster o correo electrónico malintencionado se considerará corregido.
- Una vez que todas las amenazas de la investigación se hayan corregido o cancelado como se indicó anteriormente, la investigación pasará a un estado corregido y se resolverá la alerta original.

## <a name="the-display-of-incident-evidence-for-email-and-email-clusters"></a>Visualización de pruebas de incidentes para clústeres de correo electrónico y correo electrónico

Email evidencia basada en la pestaña **Evidencia y respuesta** de un incidente ahora muestra la siguiente información.

:::image type="content" source="../../media/email-analysis-investigations/email-analysis-evidence-example.png" alt-text="La información de análisis de correo electrónico en Evidencia y respuesta" lightbox="../../media/email-analysis-investigations/email-analysis-evidence-example.png":::

A partir de las llamadas numeradas de la figura:

1. Puede realizar acciones de corrección, además del **Centro de acciones**.
2. Puede realizar acciones de corrección para clústeres de correo electrónico con un veredicto **malintencionado** (pero no **sospechoso**).
3. Para el veredicto de correo no deseado, la suplantación de identidad (phishing) se divide en una elevada confianza y una phish normal.

   Para un veredicto malintencionado, las categorías de amenazas son malware, fish de alta confianza, dirección URL malintencionada y archivo malintencionado.

   Para un veredicto sospechoso, las categorías de amenazas son spam y phish normal.

4. El recuento de correo electrónico por se basa en la ubicación de entrega más reciente e incluye contadores de correo electrónico en buzones, no en buzones y locales.
5. Incluye la fecha y hora de la consulta, que podrían actualizarse para los datos más recientes.

Para los clústeres de correo electrónico o correo electrónico en la pestaña **Entidades** de un incidente, **Impedido** significa que no había correos electrónicos malintencionados en el buzón de este elemento (correo o clúster). Aquí le mostramos un ejemplo.

:::image type="content" source="../../media/email-analysis-investigations/email-analysis-evidence-example-prevented.png" alt-text="Un correo electrónico prevenido." lightbox="../../media/email-analysis-investigations/email-analysis-evidence-example-prevented.png":::

En este ejemplo, el correo electrónico es malintencionado, pero no en un buzón de correo.

## <a name="next-steps"></a>Pasos siguientes

- [Ver acciones de corrección pendientes o completadas](air-review-approve-pending-completed-actions.md)
