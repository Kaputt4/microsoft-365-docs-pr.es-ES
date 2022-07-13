---
title: Habilitación del entorno de evaluación para Microsoft Defender para Office 365 en el entorno de producción
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
- zerotrust-solution
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: f3298c67421dea921a014bc32e91be8033733183
ms.sourcegitcommit: 61b22df76e0f81e5ef11c587b129287886151c79
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2022
ms.locfileid: "66750108"
---
# <a name="enable-the-evaluation-environment"></a>Habilitación del entorno de evaluación

**Se aplica a:**
- Microsoft 365 Defender

Este artículo es el [paso 2 del 3](eval-defender-office-365-overview.md) en el proceso de configuración del entorno de evaluación para Microsoft Defender para Office 365. Para obtener más información sobre este proceso, consulte el [artículo de información general](eval-defender-office-365-overview.md).

Siga estos pasos para habilitar la evaluación para Microsoft Defender para Office 365.

:::image type="content" source="../../media/defender/m365-defender-office-eval-enable-steps.png" alt-text="Los pasos para habilitar Microsoft Defender para Office 365 en el entorno de evaluación de Microsoft Defender" lightbox="../../media/defender/m365-defender-office-eval-enable-steps.png":::


- [Paso 1: Activación de licencias de prueba](#step-1-activate-trial-licenses)
- [Paso 2: Auditar y comprobar el registro MX público](#step-2-audit-and-verify-the-public-mx-record)
- [Paso 3: Auditar dominios aceptados](#step-3-audit-accepted-domains)
- [Paso 4: Auditoría de conectores de entrada](#step-4-audit-inbound-connectors)
- [Paso 5: Activar la evaluación](#step-5-activate-the-evaluation)

## <a name="step-1-activate-trial-licenses"></a>Paso 1: Activación de licencias de prueba

Inicie sesión en el entorno de Microsoft Defender para Office 365 existente o en el portal de administración de inquilinos.

1. Vaya al portal de administración.
2. Seleccione Comprar servicios en el inicio rápido.

   :::image type="content" source="../../media/mdo-eval/1_m365-purchase-services.png" alt-text="La opción Comprar servicios en la que se va a hacer clic en el Centro de administración de Microsoft 365" lightbox="../../media/mdo-eval/1_m365-purchase-services.png":::

3. Desplácese hacia abajo hasta la sección Add-On (o busque "Defender") para buscar los planes de Microsoft Defender para Office 365.
4. Haga clic en Detalles junto al plan que desea evaluar.

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="Botón Detalles en el que se va a hacer clic" lightbox="../../media/mdo-eval/2_mdo-eval-license-details.png":::

5. Haga clic en el vínculo *Iniciar evaluación gratuita* .

   :::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="El hipervínculo Iniciar evaluación gratuita" lightbox="../../media/mdo-eval/3-m365-purchase-button.png":::

6. Confirme la solicitud y haga clic en el botón *Probar ahora* .

   :::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="Botón Probar ahora" lightbox="../../media/mdo-eval/4_mdo-trial-order.png":::

## <a name="step-2-audit-and-verify-the-public-mx-record"></a>Paso 2: Auditar y comprobar el registro MX público

Para evaluar de forma eficaz Microsoft Defender para Office 365, es importante que el correo electrónico externo entrante se transmita a través de la instancia de Exchange Online Protection (EOP) asociada al inquilino.

1. Inicie sesión en el Portal de Administración M365, expanda Configuración y seleccione Dominios.
2. Seleccione el dominio de correo electrónico comprobado y haga clic en Administrar DNS.
3. Anote el registro MX generado y asignado al inquilino de EOP.
4. Acceda a la zona DNS externa (pública) y compruebe el registro MX principal asociado al dominio de correo electrónico.
    - *Si el registro MX público coincide actualmente con la dirección EOP asignada (por ejemplo, tenant-com.mail.protection.outlook.com), no se deben requerir más cambios de enrutamiento*.
    - Si el registro MX público se resuelve actualmente en una puerta de enlace SMTP local o de terceros, es posible que se requieran configuraciones de enrutamiento adicionales.
    - Si el registro MX público se resuelve actualmente en Exchange local, es posible que todavía esté en un modelo híbrido en el que algún buzón de correo de destinatario aún no se haya migrado a EXO.

## <a name="step-3-audit-accepted-domains"></a>Paso 3: Auditar dominios aceptados

1. Inicie sesión en Exchange Online Administración Portal, seleccione Flujo de correo y, a continuación, haga clic en Dominios aceptados.
2. En la lista de dominios aceptados que se han agregado y comprobado en el inquilino, anote el **tipo de dominio** del dominio de correo electrónico principal.
    - Si el tipo de dominio está establecido en ***Autoritativo***, se supone que todos los buzones de correo de destinatario de la organización residen actualmente en Exchange Online.
    - Si el tipo de dominio está establecido en ***Retransmisión interna*** , es posible que todavía esté en un modelo híbrido en el que algunos buzones de correo de destinatario siguen residiendo en el entorno local.

## <a name="step-4-audit-inbound-connectors"></a>Paso 4: Auditoría de conectores de entrada

1. Inicie sesión en Exchange Online Administración Portal, seleccione Flujo de correo y, a continuación, haga clic en Conectores.
2. En la lista de conectores configurados, anote las entradas que proceden de **la organización asociada** y pueden correlacionarse con una puerta de enlace SMTP de terceros.
3. En la lista de conectores configurados, anote las entradas etiquetadas **desde el servidor de correo electrónico de su organización** , lo que puede indicar que todavía está en un escenario híbrido.

## <a name="step-5-activate-the-evaluation"></a>Paso 5: Activar la evaluación

Siga estas instrucciones para activar la evaluación de Microsoft Defender para Office 365 desde el portal de Microsoft 365 Defender.

1. Inicie sesión en el inquilino con una cuenta que tenga acceso al portal de Microsoft 365 Defender.
2. Elija si desea que el **portal de Microsoft 365 Defender** sea la interfaz predeterminada para la administración de Microsoft Defender para Office 365 (recomendado).

   :::image type="content" source="../../media/mdo-eval/1_mdo-eval-activate-eval.png" alt-text="El botón Activar en configuración para dar lugar a un portal de Microsoft 365 Defender centralizado y mejorado para la administración" lightbox="../../media/mdo-eval/1_mdo-eval-activate-eval.png":::

3. En el menú de navegación, seleccione **Directivas & reglas** en *Correo electrónico & colaboración*.

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-activate-eval.png" alt-text="El elemento de menú Directivas & reglas en el que se va a hacer clic" lightbox="../../media/mdo-eval/2_mdo-eval-activate-eval.png":::

4. En el panel *Reglas de &* de directivas, haga clic en **Directivas de amenazas**.

   :::image type="content" source="../../media/mdo-eval/3_mdo-eval-activate-eval.png" alt-text="Elemento de menú Directivas de amenazas en el que se va a hacer clic" lightbox="../../media/mdo-eval/3_mdo-eval-activate-eval.png":::

5. Desplácese hacia abajo hasta *Directivas adicionales* y seleccione el icono **Evaluar Defender para Office 365**.

   :::image type="content" source="../../media/mdo-eval/4_mdo-eval-activate-eval.png" alt-text="Icono de Eval Defender para Office 365" lightbox="../../media/mdo-eval/4_mdo-eval-activate-eval.png":::

6. Ahora elija si el correo electrónico externo se enruta a Exchange Online directamente o a una puerta de enlace o servicio de terceros y haga clic en Siguiente.

   :::image type="content" source="../../media/mdo-eval/5_mdo-eval-activate-eval.png" alt-text="Panel Configuración de enrutamiento en el portal de Microsoft Defender para Office 365" lightbox="../../media/mdo-eval/5_mdo-eval-activate-eval.png":::

7. Si usa una puerta de enlace de terceros, seleccione el nombre del proveedor en la lista desplegable junto con el conector de entrada asociado a esa solución. Cuando haya enumerado las respuestas, haga clic en Siguiente.

   :::image type="content" source="../../media/mdo-eval/6-mdo-eval-activate-eval-settings.png" alt-text="Panel Configuración local o de terceros en el portal de Microsoft Defender para Office 365" lightbox="../../media/mdo-eval/6-mdo-eval-activate-eval-settings.png":::

8. Revise la configuración y haga clic en el botón **Crear evaluación** .

   |Antes|Después|
   |:---:|:---:|
   |:::image type="content" source="../../media/mdo-eval/7-mdo-eval-activate-review.png" alt-text="El panel Revisar la configuración del portal de Microsoft Defender para Office 365" lightbox="../../media/mdo-eval/7-mdo-eval-activate-review.png":::|:::image type="content" source="../../media/mdo-eval/8-mdo-eval-activate-complete.png" alt-text="La notificación de finalización de la instalación de evaluación en el portal de Microsoft Defender para Office 365" lightbox="../../media/mdo-eval/8-mdo-eval-activate-complete.png":::|
   |

## <a name="next-steps"></a>Siguientes pasos

Paso 3 de 3: Configurar el piloto para Microsoft Defender para Office 365

Vuelva a la introducción para [Evaluar Microsoft Defender para Office 365](eval-defender-office-365-overview.md)

Vuelva a la información general sobre [la evaluación y la Microsoft 365 Defender piloto](eval-overview.md)
