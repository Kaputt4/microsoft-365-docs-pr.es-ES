---
title: Cómo priorizar, administrar, investigar y actuar ante incidentes en Microsoft 365 Defender
description: Los pasos para administrar las alertas desencadenadas en Microsoft 365 Defender. La investigación y respuesta automatizadas (AIR) recorren la suscripción y determinan el impacto y el ámbito de una amenaza, y combinan la información en un único incidente.
search.product: ''
search.appverid: ''
ms.service: microsoft-365-security
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
ms.subservice: mdo
ms.openlocfilehash: 578c2e93cf18b7c80390cc7719a6af1a6ace241c
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67596663"
---
# <a name="prioritize-manage-investigate--respond-to-incidents-in-microsoft-365-defender"></a>Priorizar, administrar, investigar & responder a incidentes en Microsoft 365 Defender

Cuando se desencadenan alertas en Microsoft 365 Defender, la investigación y la respuesta automatizadas (AIR) se desencadenarán para buscar en la suscripción de una organización, determinar el impacto y el ámbito de la amenaza y intercalar la información en un único incidente para que los administradores no tengan que administrar varios incidentes.

## <a name="what-youll-need"></a>Lo que necesitará

- Microsoft Defender para Office 365 Plan 2 o superior
- Permisos suficientes (lector de seguridad, operaciones de seguridad o administrador de seguridad, además del rol [buscar y purgar](../permissions-microsoft-365-security-center.md) )

## <a name="prioritize--manage-incidents"></a>Priorizar & administrar incidentes

Vaya a la página https://security.microsoft.com/incidentsIncidentes del portal de seguridad .

Cuando se carga la página Incidente, puede filtrar y priorizar haciendo clic en columnas para ordenar las acciones o presione Filtros para aplicar un filtro como origen de datos, etiquetas o estado.

Ahora tiene una lista con prioridad de incidentes, desde la que puede seleccionar cambiar el nombre, asignar, clasificar, etiquetar, cambiar el estado o agregar comentarios mediante el botón Administrar incidentes.

Use los filtros para asegurarse de que se incluyen los elementos de Microsoft Defender para Office.

Si busca alertas específicas, use la funcionalidad de búsqueda de incidentes (*buscar nombre o identificador*) o considere la posibilidad de usar el filtrado de cola de alertas en una alerta específica.

## <a name="investigate--respond-to-incidents"></a>Investigar & responder a incidentes

Una vez que haya priorizado la cola de incidentes, haga clic en la página Información general sobre el incidente que desea investigar para cargar los incidentes. Habrá información útil como *MITRE ATT&técnicas de CK observadas* y una *escala de tiempo del ataque*.

Las pestañas de la parte superior de la página de incidentes le permiten explorar más detalles, como los usuarios afectados, los buzones de correo, los puntos de conexión y et cetera.

La pestaña *Evidencia y respuesta* muestra los elementos identificados como relacionados con la alerta original a través de la investigación.

Los elementos que se muestran como *Acción pendiente* en Evidencia y Respuesta están a la espera de la aprobación de un administrador.  Se recomienda ordenar por la columna de estado de corrección en la vista *Todas las evidencias* , seguida de hacer clic en la entidad o el clúster para cargar el menú flotante, donde puede aprobar las acciones si procede.

Si necesita comprender aún más los elementos implicados, puede usar el gráfico de incidentes para ver la vinculación visual de las evidencias y las entidades implicadas. Como alternativa, puede revisar las investigaciones subyacentes, que mostrarán más entidades y elementos implicados en el evento de seguridad.

## <a name="next-steps"></a>Pasos siguientes

Puede empezar a usar *el Centro* de acciones para actuar sobre los elementos de acción pendientes de todos los incidentes de su organización si desea centrarse en los elementos de acción para los que AIR necesita aprobación.  

## <a name="more-information"></a>Más información

[Administración de incidentes en Microsoft 365 Defender | Microsoft Docs](../../defender/manage-incidents.md)

[Funcionamiento de la investigación y respuesta automatizadas en Microsoft Defender para Office 365](../automated-investigation-response-office.md)

[Acciones de corrección en Microsoft Defender para Office 365](../air-remediation-actions.md)