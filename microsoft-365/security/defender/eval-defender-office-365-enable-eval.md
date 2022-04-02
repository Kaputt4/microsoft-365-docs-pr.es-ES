---
title: Habilitar el entorno de evaluación de Microsoft Defender para Office 365 en el entorno de producción
description: Pasos para activar Microsoft Defender para Office 365 evaluación, con licencias de prueba, control de registros MX, & auditoría de dominios aceptados y conexiones entrantes.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 07/01/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: a5a14d507f7cd10ff4f7ab62b552ab256f0e4a5e
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2022
ms.locfileid: "64499009"
---
# <a name="enable-the-evaluation-environment"></a>Habilitar el entorno de evaluación

**Se aplica a:**
- Microsoft 365 Defender

Este artículo es [el paso 2 de 3](eval-defender-office-365-overview.md) en el proceso de configuración del entorno de evaluación para Microsoft Defender para Office 365. Para obtener más información acerca de este proceso, vea el [artículo de introducción](eval-defender-office-365-overview.md).

Siga estos pasos para habilitar la evaluación de Microsoft Defender para Office 365.

:::image type="content" source="../../media/defender/m365-defender-office-eval-enable-steps.png" alt-text="Los pasos para habilitar Microsoft Defender para Office 365 en el entorno de evaluación de Microsoft Defender" lightbox="../../media/defender/m365-defender-office-eval-enable-steps.png":::


- [Paso 1: Activar licencias de prueba](#step-1-activate-trial-licenses)
- [Paso 2: Auditar y comprobar el registro MX público](#step-2-audit-and-verify-the-public-mx-record)
- [Paso 3: Auditar dominios aceptados](#step-3-audit-accepted-domains)
- [Paso 4: Auditar conectores entrantes](#step-4-audit-inbound-connectors)
- [Paso 5: Activar la evaluación](#step-5-activate-the-evaluation)

## <a name="step-1-activate-trial-licenses"></a>Paso 1: Activar licencias de prueba

Inicie sesión en su microsoft defender existente para Office 365 o portal de administración de inquilinos.

1. Vaya al portal de administración.
2. Selecciona Servicios de compra en el inicio rápido.

   :::image type="content" source="../../media/mdo-eval/1_m365-purchase-services.png" alt-text="La opción Servicios de compra que se va a hacer clic en el Centro de administración de Microsoft 365" lightbox="../../media/mdo-eval/1_m365-purchase-services.png":::

3. Desplácese hacia abajo hasta la Add-On (o busque "Defender") para buscar microsoft defender para Office 365 planes.
4. Haga clic en Detalles a continuación del plan que desea evaluar.

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="El botón Detalles que se va a hacer clic" lightbox="../../media/mdo-eval/2_mdo-eval-license-details.png":::

5. Haga clic en *el vínculo Iniciar prueba gratuita* .

   :::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="El hipervínculo Iniciar prueba gratuita" lightbox="../../media/mdo-eval/3-m365-purchase-button.png":::

6. Confirme su solicitud y haga clic en *el botón Probar* ahora.

   :::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="El botón Probar ahora" lightbox="../../media/mdo-eval/4_mdo-trial-order.png":::

## <a name="step-2-audit-and-verify-the-public-mx-record"></a>Paso 2: Auditar y comprobar el registro MX público

Para evaluar de forma eficaz microsoft defender para Office 365, es importante que el correo electrónico externo entrante se retransmita a través de la instancia de Exchange Online Protection (EOP) asociada con el inquilino.

1. Inicie sesión en M365 Admin Portal, expanda Configuración y seleccione Dominios.
2. Seleccione el dominio de correo electrónico comprobado y haga clic en Administrar DNS.
3. Anote el registro MX generado y asignado al inquilino de EOP.
4. Obtenga acceso a la zona DNS externa (pública) y compruebe el registro MX principal asociado con el dominio de correo electrónico.
    - *Si el registro MX público coincide actualmente con la dirección EOP asignada (por ejemplo, tenant-com.mail.protection.outlook.com), no* es necesario realizar más cambios de enrutamiento.
    - Si el registro MX público se resuelve actualmente en una puerta de enlace SMTP local o de terceros, es posible que se requieran configuraciones de enrutamiento adicionales.
    - Si el registro MX público se resuelve actualmente en un Exchange local, es posible que aún esté en un modelo híbrido donde aún no se haya migrado algún buzón de destinatario a EXO.

## <a name="step-3-audit-accepted-domains"></a>Paso 3: Auditar dominios aceptados

1. Inicie sesión en el portal Exchange Online administración, seleccione Correo Flow y, a continuación, haga clic en Dominios aceptados.
2. En la lista de dominios aceptados que se han agregado y comprobado en el espacio empresarial, anote el tipo de **dominio para el** dominio de correo electrónico principal.
    - Si el tipo de dominio está establecido en ***Autoritativo***, se supone que todos los buzones de destinatarios de la organización residen actualmente en Exchange Online.
    - Si el tipo de dominio se establece en ***Retransmisión*** interna, es posible que aún esté en un modelo híbrido donde algunos buzones de destinatarios aún residen localmente.

## <a name="step-4-audit-inbound-connectors"></a>Paso 4: Auditar conectores entrantes

1. Inicie sesión en el portal Exchange Online administración, seleccione Correo Flow y, a continuación, haga clic en Conectores.
2. En la lista de conectores configurados, anote las entradas que sean de la  organización de partners y que se puedan correlacionar con una puerta de enlace SMTP de terceros.
3. En la lista de conectores configurados, tome nota de las entradas etiquetadas  Desde el servidor de correo electrónico de su organización que puedan indicar que todavía está en un escenario híbrido.

## <a name="step-5-activate-the-evaluation"></a>Paso 5: Activar la evaluación

Use las instrucciones aquí para activar microsoft defender para Office 365 evaluación desde el portal Microsoft 365 Defender web.

1. Inicie sesión en el espacio empresarial con una cuenta que tenga acceso al portal de Microsoft 365 Defender cliente.
2. Elige si quieres que el portal de **Microsoft 365 Defender sea** la interfaz predeterminada de Microsoft Defender para Office 365 administración (recomendado).

   :::image type="content" source="../../media/mdo-eval/1_mdo-eval-activate-eval.png" alt-text="El botón Activar en Configuración para llevar a un portal de administración centralizado y mejorado Microsoft 365 Defender administración" lightbox="../../media/mdo-eval/1_mdo-eval-activate-eval.png":::

3. En el menú de navegación, seleccione **Directivas & reglas en** *Correo & colaboración*.

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-activate-eval.png" alt-text="El elemento de menú & reglas que se va a hacer clic en" lightbox="../../media/mdo-eval/2_mdo-eval-activate-eval.png":::

4. En el panel *Reglas & directivas* , haga clic en **Directivas de amenazas**.

   :::image type="content" source="../../media/mdo-eval/3_mdo-eval-activate-eval.png" alt-text="El elemento de menú Directivas de amenazas que se va a hacer clic en" lightbox="../../media/mdo-eval/3_mdo-eval-activate-eval.png":::

5. Desplácese hacia abajo *hasta Directivas* adicionales y seleccione **el icono Evaluar defender para Office 365** usuario.

   :::image type="content" source="../../media/mdo-eval/4_mdo-eval-activate-eval.png" alt-text="El icono Eval Defender para Office 365 ventana" lightbox="../../media/mdo-eval/4_mdo-eval-activate-eval.png":::

6. Ahora elija si el correo electrónico externo se Exchange Online directamente o a una puerta de enlace o servicio de terceros y haga clic en Siguiente.

   :::image type="content" source="../../media/mdo-eval/5_mdo-eval-activate-eval.png" alt-text="El panel Configuración de enrutamiento en el portal de Microsoft Defender Office 365 web" lightbox="../../media/mdo-eval/5_mdo-eval-activate-eval.png":::

7. Si usa una puerta de enlace de terceros, seleccione el nombre del proveedor en la lista desplegable junto con el conector de entrada asociado a esa solución. Cuando haya enumerado sus respuestas, haga clic en Siguiente.

   :::image type="content" source="../../media/mdo-eval/6-mdo-eval-activate-eval-settings.png" alt-text="Panel de configuración de terceros o local en el portal de Microsoft Defender para Office 365 local" lightbox="../../media/mdo-eval/6-mdo-eval-activate-eval-settings.png":::

8. Revise la configuración y haga clic en **el botón Crear** evaluación.

   |Antes|Después|
   |:---:|:---:|
   |:::image type="content" source="../../media/mdo-eval/7-mdo-eval-activate-review.png" alt-text="El panel Revisar la configuración en el portal de Microsoft Defender para Office 365 web" lightbox="../../media/mdo-eval/7-mdo-eval-activate-review.png":::|:::image type="content" source="../../media/mdo-eval/8-mdo-eval-activate-complete.png" alt-text="Notificación de finalización de la configuración de evaluación en el portal de Microsoft Defender para Office 365 evaluación" lightbox="../../media/mdo-eval/8-mdo-eval-activate-complete.png":::|
   |

## <a name="next-steps"></a>Pasos siguientes

Paso 3 de 3: Configurar el piloto de Microsoft Defender para Office 365

Vuelva a la introducción a [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)

Vuelva a la introducción a [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)
