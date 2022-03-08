---
title: Análisis de correo electrónico en investigaciones para Microsoft Defender para Office 365
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
- M365-security-compliance
- m365initiative-defender-office365
keywords: respuesta automatizada a incidentes, investigación, corrección, protección contra amenazas
description: Vea cómo funcionan los análisis de correo electrónico en las investigaciones en Microsoft Defender para Office 365.
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5737a2d1974805dc55b85b7ff8f4117cbc1da898
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63318191"
---
# <a name="email-analysis-in-investigations-for-microsoft-defender-for-office-365"></a>Análisis de correo electrónico en investigaciones para Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Durante la investigación automatizada de alertas, Microsoft Defender para Office 365 analiza el correo electrónico original en busca de amenazas e identifica otros correos electrónicos relacionados con el correo electrónico original y que podrían formar parte de un ataque. Este análisis es importante porque los ataques de correo electrónico rara vez consisten en un solo correo electrónico.

El análisis de correo electrónico de la investigación automatizada identifica los clústeres de correo electrónico mediante atributos del correo electrónico original para consultar los correos electrónicos enviados y recibidos por su organización. Esto es similar a un analista de operaciones de seguridad que buscaría los correos electrónicos relacionados en explorer o búsqueda avanzada. Se usan varias consultas para identificar correos electrónicos que coincidan porque los atacantes suelen transformar los parámetros de correo electrónico para evitar la detección de seguridad. El análisis de agrupación en clústeres realiza estas comprobaciones para determinar cómo controlar los correos electrónicos implicados en la investigación:

- El análisis de correo electrónico crea consultas (clústeres) de correos electrónicos con atributos del correo electrónico original: valores de remitente (dirección IP, dominio de envío) y contenido (asunto, identificador de clúster) para encontrar correos electrónicos relacionados.
- Si el análisis de las direcciones URL y archivos del correo electrónico original identifica que algunas son malintencionadas (es decir, malware o suplantación de identidad), también creará consultas o clústeres de correos electrónicos que contengan la dirección URL o el archivo malintencionados.
- El análisis de agrupación en clústeres de correo electrónico cuenta las amenazas asociadas con los correos electrónicos que coinciden en el clúster para determinar si los correos electrónicos son malintencionados, sospechosos o no tienen amenazas claras. Si el clúster de correos electrónicos que coincide con la consulta tiene una cantidad suficiente de correo no deseado, phish normal, amenazas de phishing o malware de elevada confianza, el clúster de correo electrónico obtiene ese tipo de amenaza aplicado.
- El análisis de agrupación en clústeres de correo electrónico también comprueba la ubicación de entrega más reciente del correo electrónico original y los correos electrónicos en los clústeres de correo electrónico para ayudar a identificar si los correos electrónicos potencialmente aún necesitan eliminarse o si ya se han corregido o se han evitado. Este análisis es importante porque los atacantes transforman el contenido malintencionado más las directivas de seguridad y la protección pueden variar entre buzones. Esta funcionalidad conduce a situaciones en las que el contenido malintencionado aún puede sentarse en los buzones, aunque uno o varios correos electrónicos malintencionados se han detectado y eliminado mediante la purga automática de cero horas (ZAP).
- Los clústeres de correo electrónico que se consideran malintencionados debido al malware, la suplantación de identidad de elevada confianza, los archivos malintencionados o las amenazas de direcciones URL malintencionadas recibirán una acción pendiente para eliminar temporalmente los correos electrónicos cuando aún haya en el buzón de correo en la nube (bandeja de entrada o carpeta no deseado). Si los correos electrónicos malintencionados o los clústeres de correo electrónico solo son "Not In Mailbox" (bloqueados, en cuarentena, con errores, eliminados temporalmente, etc.) o "Local/Externo" sin ninguno en el buzón de nube, no se configurará ninguna acción pendiente para quitarlos.
- Si se determina que alguno de los clústeres de correo electrónico es malintencionado, la amenaza identificada por el clúster se aplicará de nuevo al correo electrónico original implicado en la investigación. Este comportamiento es similar al de un analista de operaciones de seguridad que usa resultados de búsqueda de correo electrónico para determinar el veredicto de un correo electrónico original basado en correos electrónicos que coinciden. Este resultado garantiza que, independientemente de si se detectan o no direcciones URL, archivos o indicadores de correo electrónico de origen de un correo electrónico original, el sistema puede identificar correos electrónicos malintencionados que puedan eludir la detección mediante personalización, transformación, evasión u otras técnicas de atacante.
- En la investigación de compromiso del usuario, se crean clústeres de correo electrónico adicionales para identificar posibles problemas de correo electrónico creados por el buzón. Este proceso incluye un clúster de correo electrónico limpio (buenos correos electrónicos del usuario, posibles exfiltraciones de datos y posibles correos electrónicos de comando/control), clústeres de correo electrónico sospechosos (correos electrónicos que contienen correo no deseado o phish normal) y clústeres de correo electrónico malintencionados (correos electrónicos que contienen malware o phish de alta confianza). Estos clústeres de correo electrónico proporcionan datos de analistas de operaciones de seguridad para determinar qué otros problemas pueden tener que solucionarse a partir de un compromiso y visibilidad en la que los correos electrónicos pueden haber desencadenado las alertas originales (por ejemplo, phish/spam que desencadenó restricciones de envío de usuarios)

El análisis de agrupación en clústeres de correo electrónico a través de consultas de entidades malintencionadas y de similitud garantiza que los problemas de correo electrónico se identifiquen y se limpien completamente, incluso si solo se identifica un correo electrónico de un ataque. Puede usar vínculos desde las vistas del panel lateral de detalles del clúster de correo electrónico para abrir las consultas en explorador o búsqueda avanzada para realizar análisis más profundos y cambiar las consultas si es necesario. Esta funcionalidad permite el refinamiento manual y la corrección si encuentra que las consultas del clúster de correo electrónico son demasiado estrechas o demasiado amplias (incluidos los correos electrónicos no relacionados).

Estas son mejoras adicionales para el análisis de correo electrónico en las investigaciones.

## <a name="air-investigation-ignores-advanced-delivery-items-secops-mailbox-and-phishedu-messages"></a>La investigación de AIR omite los elementos de entrega avanzados (buzones de SecOps y mensajes phishEDU)

Durante el análisis de agrupación en clústeres de correo electrónico, todas las consultas de agrupación en clústeres omitirán los buzones de seguridad configurados como buzones de operaciones de seguridad en la directiva de entrega avanzada. Del mismo modo, las consultas de agrupación en clústeres de correo electrónico omitirán los mensajes de simulación de suplantación de identidad (educación) configurados en la directiva de entrega avanzada. Ni los valores de exclusión SecOps ni PhishEdu se muestran en la consulta para que los atributos de agrupación en clústeres sean más sencillos y fáciles de leer. Esta exclusión garantiza que la inteligencia de amenazas y los buzones operativos (buzones de SecOps) y las simulaciones de suplantación de identidad (PhishEdu) se omiten durante el análisis de amenazas y no se quitan durante ninguna corrección.

>[!Note]
>Al abrir un clúster de correo electrónico para verlo en el Explorador desde los detalles del clúster de correo electrónico, los filtros de buzón phishedu y secops se aplicarán en el Explorador, pero no se mostrarán. Si cambia los filtros del Explorador, las fechas o la actualización de la consulta dentro de la página, las exclusiones de filtro PhishEdu/SecOps se quitarán y los correos electrónicos que coincidan con estos se mostrarán una vez más. Si actualiza la página explorador mediante la función de actualización del explorador, los filtros de consulta originales se volverán a cargar, incluidos los filtros PhishEdu/SecOps, pero eliminando los cambios posteriores que haya realizado.
>

## <a name="air-updates-pending-email-action-status"></a>Estado de acción de correo electrónico pendiente de actualizaciones de AIR

El análisis de correo electrónico de investigación calcula las amenazas y ubicaciones de correo electrónico en el momento de la investigación para crear las pruebas y acciones de investigación. Estos datos pueden estar obsoletos y obsoletos cuando las acciones fuera de la investigación afectan a los correos electrónicos implicados en la investigación. Por ejemplo, la búsqueda manual de operaciones de seguridad y la corrección pueden limpiar los correos electrónicos incluidos en una investigación. Del mismo modo, las acciones de eliminación aprobadas en investigaciones paralelas o acciones de cuarentena automática de purga automática de hora cero (ZAP) pueden haber quitado correos electrónicos. Además, las detecciones retrasadas de amenazas después de la entrega de correo electrónico pueden cambiar el número de amenazas incluidas en las consultas o clústeres de correo electrónico de la investigación.

Para garantizar que las acciones de investigación estén actualizadas, cualquier investigación que tenga acciones pendientes volverá a ejecutar periódicamente las consultas de análisis de correo electrónico para actualizar las ubicaciones de correo electrónico y las amenazas.

- Cuando cambien los datos del clúster de correo electrónico, se actualizarán los recuentos de amenazas y de ubicación de entrega más recientes.
- Si los correos electrónicos o el clúster de correo electrónico con acciones pendientes ya no están en el buzón de correo, se cancelará la acción pendiente y se considerará corregido el correo electrónico o clúster malintencionado.
- Una vez que todas las amenazas de la investigación se hayan corregido o cancelado como se mencionó anteriormente, la investigación pasará a un estado corregido y se resolverá la alerta original.

## <a name="the-display-of-incident-evidence-for-email-and-email-clusters"></a>Presentación de pruebas de incidentes para clústeres de correo electrónico y correo electrónico

Las pruebas basadas en correo electrónico en **la pestaña Evidencia y respuesta** de un incidente ahora muestran la siguiente información.

:::image type="content" source="../../media/email-analysis-investigations/email-analysis-evidence-example.png" alt-text="Ejemplo de información de análisis de correo electrónico en Evidencia y respuesta." lightbox="../../media/email-analysis-investigations/email-analysis-evidence-example.png":::

De las llamadas numeradas de la figura:

1. Puede realizar acciones de corrección, además del Centro **de acciones**.
2. Puede realizar acciones de corrección para clústeres de correo electrónico **con un** veredicto malintencionado (pero no **sospechoso**).
3. Para el veredicto de correo no deseado de correo electrónico, la suplantación de identidad (phishing) se divide en alta confianza y phishing normal.

   Para un veredicto malintencionado, las categorías de amenazas son malware, phish de elevada confianza, dirección URL malintencionada y archivo malintencionado.

   Para un veredicto sospechoso, las categorías de amenazas son correo no deseado y phish normal.

4. El recuento de correo electrónico por se basa en la ubicación de entrega más reciente e incluye contadores para correo electrónico en buzones de correo, no en buzones y locales.
5. Incluye la fecha y hora de la consulta, que podrían actualizarse para los datos más recientes.

Para los clústeres de correo electrónico o  correo electrónico de la pestaña Entidades de un **incidente,** Prevenido significa que no había correos electrónicos malintencionados en el buzón para este elemento (correo o clúster). Aquí le mostramos un ejemplo.

:::image type="content" source="../../media/email-analysis-investigations/email-analysis-evidence-example-prevented.png" alt-text="Ejemplo de un correo electrónico impedido." lightbox="../../media/email-analysis-investigations/email-analysis-evidence-example-prevented.png":::

En este ejemplo, el correo electrónico es malintencionado, pero no en un buzón.

## <a name="next-steps"></a>Pasos siguientes

- [Ver acciones de corrección pendientes o completadas](air-review-approve-pending-completed-actions.md)
