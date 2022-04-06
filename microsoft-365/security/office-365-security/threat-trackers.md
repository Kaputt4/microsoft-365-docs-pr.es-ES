---
title: 'Rastreadores de amenazas: nuevos y destacables'
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: a097f5ca-eac0-44a4-bbce-365f35b79ed1
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: ''
description: Obtenga información sobre los rastreadores de amenazas, incluidos los nuevos rastreadores notables, para ayudar a su organización a mantenerse al tanto de los problemas de seguridad.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ba038f94e711470242995a8ea0f082cd6d82dcda
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64663256"
---
# <a name="threat-trackers---new-and-noteworthy"></a>Rastreadores de amenazas: nuevos y destacables

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Office 365 funcionalidades de investigación y respuesta de amenazas](office-365-ti.md) permiten al equipo de seguridad de su organización detectar y tomar medidas contra las amenazas de ciberseguridad. Office 365 funcionalidades de investigación y respuesta de amenazas incluyen características de seguimiento de amenazas, incluidos los rastreadores notables. Lea este artículo para obtener información general sobre estas nuevas características y los pasos siguientes.

> [!IMPORTANT]
> Office 365 Inteligencia sobre amenazas ahora está Microsoft Defender para Office 365 plan 2, junto con funcionalidades adicionales de protección contra amenazas. Para obtener más información, consulte [Microsoft Defender para Office 365 planes y precios](https://products.office.com/exchange/advance-threat-protection) y la [descripción del servicio Microsoft Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

## <a name="what-are-threat-trackers"></a>¿Qué son los rastreadores de amenazas?

Los rastreadores de amenazas son widgets informativos y vistas que le proporcionan inteligencia sobre diferentes problemas de ciberseguridad que podrían afectar a su empresa. Por ejemplo, puede ver información sobre las campañas de malware de tendencias mediante Los rastreadores de amenazas.

:::image type="content" source="../../media/a883b5ac-8e2b-469a-90e0-f8ad39bb63b7.png" alt-text="Ejemplo de seguimiento de amenazas en el que se muestran campañas de malware" lightbox="../../media/a883b5ac-8e2b-469a-90e0-f8ad39bb63b7.png":::

La mayoría de las páginas de seguimiento incluyen números de tendencia que se actualizan periódicamente, widgets para ayudarle a comprender qué problemas son los más grandes o que más han crecido, y un vínculo rápido en la columna **Acciones** que le lleva al Explorador, donde puede ver información más detallada.

:::image type="content" source="../../media/e426f220-fdcb-4dd9-99a2-db97dbcf71d5.png" alt-text="Ejemplo de información de campaña en el Explorador" lightbox="../../media/e426f220-fdcb-4dd9-99a2-db97dbcf71d5.png":::

Los rastreadores son solo algunas de las muchas características excelentes que se obtienen con [Microsoft Defender para Office 365 Plan 2](office-365-ti.md). Los rastreadores de amenazas incluyen [rastreadores notables](#noteworthy-trackers), [seguimientos de tendencias](#trending-trackers), [consultas con seguimiento](#tracked-queries) y [consultas guardadas](#saved-queries).

Para ver y usar los rastreadores de amenazas de su organización, abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>y vaya a **Correo electrónico & seguimiento de amenazas de colaboración**\>. Para ir directamente a la página **Seguimiento de amenazas** , use <https://security.microsoft.com/threattrackerv2>.

> [!NOTE]
> Para usar Los rastreadores de amenazas, debe ser administrador global, administrador de seguridad o lector de seguridad. Consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

### <a name="noteworthy-trackers"></a>Rastreadores destacados

Los rastreadores destacados son los lugares donde encontrará amenazas y riesgos grandes y más pequeños que creemos que debe conocer. Los seguimientos destacados le ayudan a averiguar si estos problemas existen en su entorno de Microsoft 365, además de un vínculo a artículos (como este) que le proporcionan más detalles sobre lo que sucede y cómo afectarán al uso de Office 365 de su organización. Ya sea una gran amenaza nueva (por ejemplo, Wannacry, Petya) o una amenaza existente que podría crear algunos desafíos nuevos (como nuestro otro elemento destacado inaugural: Nemucod), aquí es donde encontrará nuevos elementos importantes que usted y su equipo de seguridad deben revisar y examinar periódicamente.

Normalmente, los rastreadores notables se publicarán durante un par de semanas cuando identifiquemos nuevas amenazas y creamos que es posible que necesite la visibilidad adicional que proporciona esta característica. Una vez que haya pasado el mayor riesgo para una amenaza, quitaremos ese elemento notable. De este modo, podemos mantener la lista actualizada y actualizada con otros elementos nuevos relevantes.

### <a name="trending-trackers"></a>Seguimientos de tendencias

Los seguimientos de tendencias (anteriormente denominados Campañas) resaltan las nuevas amenazas recibidas en el correo electrónico de la organización en la última semana. La vista Seguimientos de tendencias proporciona evaluaciones dinámicas de las amenazas de correo electrónico que afectan al entorno de Office 365 de su organización. Esta vista muestra las tendencias de malware en el nivel de inquilino, identificando las familias de malware en aumento, planas o en declive, lo que proporciona a los administradores una mayor información sobre qué amenazas requieren más atención.

:::image type="content" source="../../media/d2ccc1a0-2a1d-4e36-99b5-6766c207772f.png" alt-text="El ejemplo del widget de campañas de malware más populares" lightbox="../../media/d2ccc1a0-2a1d-4e36-99b5-6766c207772f.png":::

Los rastreadores de tendencias le ofrecen una idea de las nuevas amenazas que debe revisar para asegurarse de que su entorno corporativo más amplio está preparado contra ataques.

### <a name="tracked-queries"></a>Consultas de seguimiento

Las consultas de seguimiento aprovechan las consultas guardadas para evaluar periódicamente Microsoft 365 actividad en su organización. Esto le ofrece tendencias de eventos, con más que venir en los próximos meses. Las consultas de seguimiento se ejecutan automáticamente, lo que proporciona información actualizada sin tener que recordar volver a ejecutar las consultas.

:::image type="content" source="../../media/0c556174-06eb-4ae5-b32a-5ff76b9e4f13.png" alt-text="Ejemplo de consultas de seguimiento con una seleccionada" lightbox="../../media/0c556174-06eb-4ae5-b32a-5ff76b9e4f13.png":::

### <a name="saved-queries"></a>Consultas guardadas

Las consultas guardadas también se encuentran en la sección Rastreadores. Puede usar consultas guardadas para almacenar las búsquedas comunes del Explorador a las que desea volver más rápido y repetidamente, sin tener que volver a crear la búsqueda cada vez.

:::image type="content" source="../../media/188cf3ff-58f1-41ea-81aa-76158d8f40c3.png" alt-text="Lista de consultas de seguimiento con una seleccionada" lightbox="../../media/188cf3ff-58f1-41ea-81aa-76158d8f40c3.png":::

Siempre puede guardar una consulta de seguimiento notable o cualquiera de sus propias consultas del Explorador mediante el botón **Guardar consulta** en la parte superior de la página Explorador. Cualquier cosa guardada allí se mostrará en la lista **Consultas guardadas** en la página Seguimiento.

## <a name="trackers-and-explorer"></a>Rastreadores y explorador

Tanto si está revisando el correo electrónico, el contenido o las actividades de Office (próximamente), Explorer y Trackers trabajan juntos para ayudarle a investigar y realizar un seguimiento de los riesgos y amenazas de seguridad. Todos juntos, Trackers le proporcionan información para proteger a los usuarios resaltando los problemas nuevos, notables y de búsqueda frecuente, lo que garantiza que su negocio esté mejor protegido a medida que se mueve a la nube.

Y recuerde que siempre puede proporcionarnos comentarios sobre esta u otras características de seguridad Microsoft 365 haciendo clic en el botón **Comentarios** de la esquina inferior derecha.

:::image type="content" source="../../media/microsoft-365-defender-portal.png" alt-text="El portal de Microsoft 365 Defender incluye:" lightbox="../../media/microsoft-365-defender-portal.png":::

## <a name="trackers-and-microsoft-defender-for-office-365"></a>Seguimientos y Microsoft Defender para Office 365

Con nuestra amenaza destacada inaugural, estamos resaltando las amenazas de malware avanzadas detectadas por [Caja fuerte Attachments](safe-attachments.md). Si es un cliente Office 365 Enterprise E5 y no usa [Microsoft Defender para Office 365](defender-for-office-365.md), debería estarlo: se incluye en su suscripción. Defender para Office 365 proporciona valor incluso si tiene otras herramientas de seguridad que filtran el flujo de correo electrónico con los servicios de Office 365. Sin embargo, las características de vínculos [Caja fuerte](safe-links.md) y antispam funcionan mejor cuando la solución de seguridad de correo electrónico principal se realiza a través de Office 365.

:::image type="content" source="../../media/policies.png" alt-text="El Microsoft Defender para Office 365 en el portal de Microsoft 365 Defender" lightbox="../../media/policies.png":::

En el mundo acertijo de amenazas de hoy en día, ejecutar solo exámenes antimalware tradicionales significa que no está protegido lo suficientemente bien frente a ataques. Los atacantes más sofisticados de hoy en día usan herramientas disponibles habitualmente para crear nuevos ataques, ofuscados o retrasados que no serán reconocidos por los motores antimalware tradicionales basados en firmas. La característica datos adjuntos de Caja fuerte toma datos adjuntos de correo electrónico y los detona en un entorno virtual para determinar si son seguros o malintencionados. Este proceso de detonación abre cada archivo en un entorno de equipo virtual y, a continuación, observa lo que sucede después de abrir el archivo. Ya sea un archivo PDF y comprimido, o un documento Office, el código malintencionado se puede ocultar en un archivo, activando solo una vez que la víctima lo abre en su equipo. Al detonar y analizar el archivo en el flujo de correo electrónico, Defender para Office 365 capacidades encuentra estas amenazas en función de comportamientos, reputación de archivos y una serie de reglas heurísticas.

El nuevo filtro de amenazas notable resalta los elementos que se detectaron recientemente a través de Caja fuerte Datos adjuntos. Estas detecciones representan elementos que son archivos malintencionados nuevos, no encontrados previamente por Microsoft 365 en el flujo de correo electrónico o en el correo electrónico de otros clientes. Preste atención a los elementos del Rastreador de amenazas notables, vea quién fue el objetivo de ellos y revise los detalles de la detonación que se muestran en la pestaña Análisis avanzado (se encuentra haciendo clic en el asunto del correo electrónico en el Explorador). Tenga en cuenta que solo encontrará esta pestaña en los correos electrónicos detectados por la funcionalidad de datos adjuntos de Caja fuerte: este seguimiento notable incluye ese filtro, pero también puede usar ese filtro para otras búsquedas en el Explorador.

## <a name="next-steps"></a>Siguientes pasos

- Si su organización aún no tiene estas funcionalidades de investigación y respuesta de amenazas Office 365, consulte [¿Cómo obtenemos Office 365 funcionalidades de investigación y respuesta de amenazas?](office-365-ti.md).

- Asegúrese de que el equipo de seguridad tiene asignados los roles y permisos correctos. Debe ser administrador global o tener asignado el rol Administrador de seguridad o Buscar y purgar en el portal de Microsoft 365 Defender. Consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

- Vea los nuevos rastreadores para que aparezcan en su entorno de Microsoft 365. Cuando esté disponible, encontrará los rastreadores en la página **Seguimiento de amenazas** en el portal de Microsoft 365 Defender en <https://security.microsoft.com/threattracker>.

- Si aún no lo ha hecho, obtenga más información y configure [Microsoft Defender para Office 365](defender-for-office-365.md) para su organización, [incluidos Caja fuerte vínculos](safe-links.md) y [datos adjuntos de Caja fuerte](safe-attachments.md).
