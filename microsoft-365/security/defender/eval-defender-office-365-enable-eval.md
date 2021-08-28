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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: f00daf82a2b6090f6934aba12eb9227efdfa1422
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58576157"
---
# <a name="enable-the-evaluation-environment"></a>Habilitar el entorno de evaluación

**Se aplica a:**
- Microsoft 365 Defender

Este artículo es [el paso 2 de 3](eval-defender-office-365-overview.md) en el proceso de configuración del entorno de evaluación para Microsoft Defender para Office 365. Para obtener más información acerca de este proceso, vea el [artículo de introducción](eval-defender-office-365-overview.md).

Siga estos pasos para habilitar la evaluación de Microsoft Defender para Office 365.

![Pasos para habilitar Microsoft Defender para Office 365 en el entorno de evaluación de Microsoft Defender.](../../media/defender/m365-defender-office-eval-enable-steps.png)

- [Paso 1: Activar licencias de prueba](#step-1-activate-trial-licenses)
- [Paso 2: Auditar y comprobar el registro MX público](#step-2-audit-and-verify-the-public-mx-record)
- [Paso 3: Auditar dominios aceptados](#step-3-audit-accepted-domains)
- [Paso 4: Auditar conectores entrantes](#step-4-audit-inbound-connectors)
- [Paso 5: Activar la evaluación](#step-5-activate-the-evaluation)

## <a name="step-1-activate-trial-licenses"></a>Paso 1: Activar licencias de prueba

Inicie sesión en su microsoft defender existente para Office 365 entorno o portal de administración de inquilinos.

1. Vaya al portal de administración.
2. Selecciona Servicios de compra en el inicio rápido.

   :::image type="content" source="../../media/mdo-eval/1_m365-purchase-services.png" alt-text="Haga clic en Comprar servicios en el panel de navegación de Office 365.":::

3. Desplácese hacia abajo hasta la Add-On (o busque "Defender") para buscar microsoft defender para Office 365 planes.
4. Haga clic en Detalles a continuación del plan que desea evaluar.

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="Haga clic en el botón Detalles, a continuación.":::

5. Haga clic en *el vínculo Iniciar prueba gratuita.*

   :::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="Haga clic en el inicio de prueba gratuita *hyperlink* en este panel.":::

6. Confirme su solicitud y haga clic en *el botón Probar* ahora.

   :::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="Ahora haga clic en el botón Probar ahora **.":::

## <a name="step-2-audit-and-verify-the-public-mx-record"></a>Paso 2: Auditar y comprobar el registro MX público

Para evaluar de forma eficaz microsoft defender para Office 365, es importante que el correo electrónico externo entrante se retransmita a través de la instancia de Exchange Online Protection (EOP) asociada con el inquilino.

1. Inicie sesión en M365 Admin Portal, expanda Configuración y seleccione Dominios.
2. Seleccione el dominio de correo electrónico comprobado y haga clic en Administrar DNS.
3. Anote el registro MX generado y asignado al inquilino de EOP.
4. Obtenga acceso a la zona DNS externa (pública) y compruebe el registro MX principal asociado con el dominio de correo electrónico.
    - Si el registro MX público coincide actualmente con la dirección EOP asignada *(por ejemplo, tenant-com.mail.protection.outlook.com), no* es necesario realizar más cambios de enrutamiento .
    - Si el registro MX público se resuelve actualmente en una puerta de enlace SMTP local o de terceros, es posible que se requieran configuraciones de enrutamiento adicionales.
    - Si el registro MX público se resuelve actualmente en un Exchange local, es posible que aún esté en un modelo híbrido en el que algún buzón de destinatario aún no se haya migrado a EXO.

## <a name="step-3-audit-accepted-domains"></a>Paso 3: Auditar dominios aceptados

1. Inicie sesión en el portal Exchange Online administración, seleccione Correo Flow y, a continuación, haga clic en Dominios aceptados.
2. En la lista de dominios aceptados que se han agregado y comprobado en el espacio empresarial, anote el tipo de dominio **para** el dominio de correo electrónico principal.
    - Si el tipo de  dominio está establecido en Autoritativo, se supone que todos los buzones de destinatarios de la organización residen actualmente en Exchange Online.
    - Si el tipo de dominio se establece en ***Retransmisión*** interna, es posible que aún esté en un modelo híbrido donde algunos buzones de destinatarios aún residen localmente.

## <a name="step-4-audit-inbound-connectors"></a>Paso 4: Auditar conectores entrantes

1. Inicie sesión en el portal Exchange Online administración, seleccione Correo Flow y, a continuación, haga clic en Conectores.
2. En la lista de conectores configurados, anote  las entradas que sean de la organización de partners y que se puedan correlacionar con una puerta de enlace SMTP de terceros.
3. En la lista de conectores configurados, tome  nota de las entradas etiquetadas Desde el servidor de correo electrónico de su organización que puedan indicar que todavía está en un escenario híbrido.

## <a name="step-5-activate-the-evaluation"></a>Paso 5: Activar la evaluación

Use las instrucciones aquí para activar microsoft defender para Office 365 evaluación desde el portal Microsoft 365 Defender web.

1. Inicie sesión en el espacio empresarial con una cuenta que tenga acceso al portal Microsoft 365 Defender usuario.
2. Elige si quieres que el portal de **Microsoft 365 Defender** sea la interfaz predeterminada de Microsoft Defender para Office 365 administración (recomendado).

   :::image type="content" source="../../media/mdo-eval/1_mdo-eval-activate-eval.png" alt-text="Haga clic en el botón Activar configuración para usar el portal de administración centralizado y mejorado Microsoft 365 Defender administración.":::

3. En el menú de navegación, seleccione **Directivas & reglas en** Correo & *colaboración*.

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-activate-eval.png" alt-text="Esta es una imagen del menú Colaboración & correo electrónico que apunta a Directivas & reglas. Haga clic en eso.":::

4. En el *panel Reglas de &,* haga clic en **Directivas de amenazas.**

   :::image type="content" source="../../media/mdo-eval/3_mdo-eval-activate-eval.png" alt-text="Imagen del panel Reglas & directivas y una flecha que apunta a directivas de amenazas. Haga clic en el siguiente!":::

5. Desplácese hacia abajo *hasta Directivas adicionales* y seleccione el icono **Evaluar defender para Office 365** usuario.

   :::image type="content" source="../../media/mdo-eval/4_mdo-eval-activate-eval.png" alt-text="El icono de Eval Defender para Office 365 que dice que es una prueba de 30 días en todos los vectores de colaboración & correo electrónico. Haga clic en.":::

6. Ahora elija si el correo electrónico externo se Exchange Online directamente o a una puerta de enlace o servicio de terceros y haga clic en Siguiente.

   :::image type="content" source="../../media/mdo-eval/5_mdo-eval-activate-eval.png" alt-text="Defender for Office 365 evaluará el envío de correo a los buzones Exchange Online correo. Dar los detalles de cómo se enruta el correo ahora, incluido el nombre del conector saliente que enruta el correo. Si solo usa Exchange Online Protection (EOP) no tendrá un conector. Elija uno de los que estoy usando un proveedor local o de terceros, o solo uso EOP.":::

7. Si usa una puerta de enlace de terceros, seleccione el nombre del proveedor en la lista desplegable junto con el conector de entrada asociado a esa solución. Cuando haya enumerado sus respuestas, haga clic en Siguiente.

   :::image type="content" source="../../media/mdo-eval/6-mdo-eval-activate-eval-settings.png" alt-text="En este cuadro de diálogo, elija el servicio de proveedor de terceros que usa su organización o seleccione *Other*. En el siguiente cuadro de diálogo hacia abajo, seleccione el conector de entrada. A continuación, haga clic en Siguiente.":::

8. Revise la configuración y haga clic en **el botón Crear** evaluación.

   |Antes|Después|
   |:---:|:---:|
   |:::image type="content" source="../../media/mdo-eval/7-mdo-eval-activate-review.png" alt-text="Este panel tiene una lista desplegable para revisar la configuración. También tiene un vínculo que permite hacer clic en Editar el tipo de enrutamiento si es necesario. Cuando esté listo, haga clic en el botón azul grande Crear evaluación.":::|:::image type="content" source="../../media/mdo-eval/8-mdo-eval-activate-complete.png" alt-text="Y ahora la configuración se ha completado. El botón azul de esta página dice &quot;Ir a evaluación&quot;.":::|
   |

## <a name="next-steps"></a>Pasos siguientes

Paso 3 de 3: Configurar el piloto de Microsoft Defender para Office 365

Vuelva a la introducción a [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)

Vuelva a la introducción a [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)
