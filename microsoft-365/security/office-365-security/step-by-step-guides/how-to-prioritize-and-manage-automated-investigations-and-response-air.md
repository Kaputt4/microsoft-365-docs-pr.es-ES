---
title: Cómo priorizar y administrar investigaciones y respuestas automatizadas (AIR).
description: Pasos para analizar y aprobar acciones de AIR directamente desde el Centro de acciones. Cuando se desencadenan alertas, la investigación y respuesta automatizadas (AIR) determina el ámbito de impacto de una amenaza en su organización y proporciona las acciones de corrección recomendadas.
search.product: ''
search.appverid: ''
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
ms.openlocfilehash: 234ce1ecb486c01b95c91aa51a0c5fd6b46e7a3c
ms.sourcegitcommit: a7c1acfb3d2cbba913e32493b16ebd8cbfeee456
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "66998249"
---
# <a name="prioritize-and-manage-automated-investigations-and-response-air"></a>Priorizar y administrar investigaciones y respuestas automatizadas (AIR)

La investigación y respuesta automatizadas (AIR) ahorra tiempo y esfuerzo al equipo de operaciones de seguridad.

- Cuando se desencadenan alertas, la investigación automatizada determinará el ámbito de impacto de una amenaza en su organización y proporcionará las acciones de corrección recomendadas.
- Los equipos de seguridad pueden ahorrar tiempo aprovechando la automatización de AIR para reducir la necesidad de búsqueda manual.
- Estas investigaciones pueden identificar correos electrónicos que no se han limpiado mediante purga automática de cero horas (ZAP) u otra corrección.
- Las investigaciones de AIR también identifican configuraciones de buzón que pueden ser de riesgo o indicar un buzón en peligro.

Las acciones de investigación (y las investigaciones) son accesibles desde varios puntos del portal de seguridad de Microsoft: a través de *incidentes, alertas* o a través *del Centro de acciones*. Los administradores que usan se basan en el flujo de trabajo que está persiguiendo un administrador.

## <a name="why-use-the-action-center-workflow"></a>¿Por qué usar el flujo de trabajo del Centro de acciones?

A medida que las investigaciones automatizadas sobre Email & contenido de *colaboración* producen veredictos, como *Malintencionados* o *Sospechosos*, se crean ciertas acciones de corrección. Las acciones de corrección sugeridas no se llevan a cabo automáticamente. SecOps debe ir a cada investigación para *aprobar* esas acciones sugeridas. En el *Centro de acciones* , todas las acciones pendientes se agregan para una aprobación rápida.

## <a name="what-youll-need"></a>Lo que necesitará

- Microsoft Defender para Office 365 plan 2 o superior (incluido con E5)
- Permisos suficientes (lector de seguridad, operaciones de seguridad o administrador de seguridad, además del rol [buscar y purgar](../permissions-microsoft-365-security-center.md) )

## <a name="steps-to-analyze-and-approve-air-actions-directly-from-the-action-center"></a>Pasos para analizar y aprobar acciones de AIR directamente desde el Centro de acciones

1. Vaya a [Microsoft 365 Defender portal](https://security.microsoft.com/action-center) e inicie sesión.
2. Cuando se cargue el Centro de acciones, filtre y priorice haciendo clic en columnas para ordenar las acciones, o presione **Filtros** para aplicar un filtro como el *tipo de entidad* (para una dirección URL determinada) o el tipo de acción (como el correo electrónico de eliminación temporal).
3. Se abrirá un control flotante una vez que se haga clic en una acción. Aparecerá en el lado derecho de la pantalla para su revisión.
4. Para obtener más información sobre por qué se solicita una acción, seleccione **Abrir página de investigación** en el control flotante para obtener más información sobre la investigación o las alertas vinculadas a esta acción. (Los administradores también pueden aprobar las acciones que se ven en la página de investigación seleccionando la pestaña *Acciones pendientes* ).
5. De lo contrario, seleccione **Aprobar** para realizar la acción recomendada directamente desde el Centro de acciones.
6. Rechace la acción si determina que es innecesaria.

## <a name="check-air-history"></a>Comprobación del historial de AIR

1. Vaya al [portal de Microsoft 365 Defender](https://security.microsoft.com) e inicie sesión.
2. En el panel de navegación izquierdo, expanda **Acciones & envíos** y, a continuación, haga clic en **Centro de acciones**.
3. Cuando se cargue el Centro de acciones, presione la pestaña **Historial** .
4. Vea el historial de AIR, incluidas las decisiones tomadas, el origen de la acción y el administrador que tomó la decisión, si procede.

## <a name="more-information"></a>Más información

[Ver los resultados de una investigación automatizada en Microsoft 365: Office 365 | Microsoft Docs](../air-view-investigation-results.md)

[Obtenga información sobre cómo aprobar y rechazar acciones pendientes en la página Investigación](../air-review-approve-pending-completed-actions.md)
