---
title: Plan for end-of-support software and software versions
description: Descubra y planee versiones de software y software que ya no son compatibles y no recibirán actualizaciones de seguridad.
keywords: Administración de amenazas y vulnerabilidades, recomendación de seguridad de Microsoft Defender para endpoint tvm, recomendación de ciberseguridad, recomendación de seguridad que se puede tomar
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: cf09fb75ca14a35f0ca29c9352864329459b3203
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2021
ms.locfileid: "60881738"
---
# <a name="plan-for-end-of-support-software-and-software-versions-with-threat-and-vulnerability-management"></a>Plan for end-of-support software and software versions with Administración de amenazas y vulnerabilidades

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

El fin de la compatibilidad (EOS), también conocido como fin de vida (EOL), para las versiones de software o software significa que ya no se admitirán ni se les dará servicio y no recibirán actualizaciones de seguridad. Cuando usa versiones de software o software con soporte técnico finalizado, expone su organización a vulnerabilidades de seguridad, riesgos legales y financieros.

Es fundamental que los administradores de SEGURIDAD y TI trabajen juntos y se aseguren de que el inventario de software de la organización esté configurado para obtener resultados óptimos, cumplimiento y un ecosistema de red en buen estado. Deben examinar las opciones para quitar o reemplazar aplicaciones que han alcanzado versiones de fin de soporte y actualización que ya no son compatibles. Es mejor crear e implementar un **plan** antes de que finalicen las fechas de soporte técnico.

> [!NOTE]
> Actualmente, la funcionalidad de fin de soporte técnico solo está disponible para Windows productos.

## <a name="find-software-or-software-versions-that-are-no-longer-supported"></a>Buscar versiones de software o software que ya no son compatibles

1. En el menú Administración de amenazas y vulnerabilidades, vaya a [**Recomendaciones de seguridad**](tvm-security-recommendation.md).
2. Vaya al panel **Filtros** y busque la sección etiquetas. Seleccione una o varias de las opciones de etiqueta de EOS. A **continuación, aplique**.

    ![Etiquetas de captura de pantalla que dicen software de EOS, versiones de EOS y próximas versiones de EOS.](images/tvm-eos-tag.png)

3. Verá una lista de recomendaciones relacionadas con el software con soporte finalizado, las versiones de software que han finalizado el soporte técnico o las versiones con el próximo final de soporte técnico. Estas etiquetas también están visibles en la [página de inventario de](tvm-software-inventory.md) software.

    ![Recomendaciones con etiqueta EOS.](images/tvm-eos-tags-column.png)

## <a name="list-of-versions-and-dates"></a>Lista de versiones y fechas

Para ver una lista de versiones que han llegado al final de la compatibilidad, o finalizar o admitir pronto, y esas fechas, siga los pasos siguientes:

1. Aparecerá un mensaje en el control de recomendación de seguridad para software con versiones que han llegado al final del soporte técnico, o llegará al final de la compatibilidad pronto.

    ![Captura de pantalla del vínculo de distribución de versiones.](images/eos-upcoming-eos.png)

2. Seleccione el **vínculo de distribución** de versiones para ir a la página de desglose de software. Allí, puede ver una lista filtrada de versiones con etiquetas que las identifican como el final de la compatibilidad o el próximo final de la compatibilidad.

    ![Captura de pantalla de la página de análisis de software con el software de fin de soporte técnico.](images/software-drilldown-eos.png)

3. Seleccione una de las versiones de la tabla que desea abrir. Por ejemplo, versión 10.0.18362.1. Aparecerá un menú desplegable con la fecha de finalización del soporte técnico.

    ![Captura de pantalla de la fecha de finalización del soporte técnico.](images/version-eos-date.png)

Una vez que identifique qué versiones de software y software son vulnerables debido a su estado de fin de soporte técnico, debe decidir si desea actualizarlas o quitarlas de su organización. Si lo hace, disminuirá la exposición de las organizaciones a vulnerabilidades y amenazas persistentes avanzadas.

## <a name="related-topics"></a>Temas relacionados

- [Información general sobre amenazas administración de vulnerabilidades amenazas](next-gen-threat-and-vuln-mgt.md)
- [Recomendaciones de seguridad](tvm-security-recommendation.md)
- [Inventario de software](tvm-software-inventory.md)
