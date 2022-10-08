---
title: Habilitación del entorno de evaluación para Microsoft Defender para Office 365 en el entorno de producción
description: Pasos para activar Microsoft Defender para Office 365 evaluación, con licencias de prueba, control de registros MX, & auditoría de dominios aceptados y conexiones entrantes.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 09/01/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
- tier1
ms.topic: how-to
ms.openlocfilehash: 2bf372cb9836b5565a5e311a17806d6f52d3945a
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68072973"
---
# <a name="enable-the-evaluation-environment"></a>Habilitación del entorno de evaluación

**Se aplica a:**
- Microsoft 365 Defender

Este artículo es el [paso 2 del 3](eval-defender-office-365-overview.md) en el proceso de configuración del entorno de evaluación para Microsoft Defender para Office 365. Para obtener más información sobre este proceso, consulte el [artículo de información general](eval-defender-office-365-overview.md).

Siga estos pasos para habilitar la evaluación para Microsoft Defender para Office 365.

:::image type="content" source="../../media/defender/m365-defender-office-eval-enable-steps.png" alt-text="Pasos para habilitar Microsoft Defender para Office 365 en el entorno de evaluación de Microsoft Defender." lightbox="../../media/defender/m365-defender-office-eval-enable-steps.png":::

- [Paso 1: Auditar y comprobar el registro MX público](#step-1-audit-and-verify-the-public-mx-record)
- [Paso 2: Auditar dominios aceptados](#step-2-audit-accepted-domains)
- [Paso 3: Auditoría de conectores de entrada](#step-3-audit-inbound-connectors)
- [Paso 4: Activar la evaluación](#step-4-activate-the-evaluation)

## <a name="step-1-audit-and-verify-the-public-mx-record"></a>Paso 1: Auditar y comprobar el registro MX público

Para evaluar de forma eficaz Microsoft Defender para Office 365, es importante que el correo electrónico externo entrante se transmita a través de la instancia de Exchange Online Protection (EOP) asociada al inquilino.

1. En el portal de Administración M365 en <https://admin.microsoft.com>, expanda *... Mostrar todo* si es necesario, expanda *Configuración* y, a continuación, seleccione **Dominios**. O bien, para ir directamente a la página *Dominios* , use <https://admin.microsoft.com/Adminportal/Home#/Domains>.
2. En la página *Dominios* , seleccione el dominio de correo electrónico comprobado haciendo clic en cualquier parte de la entrada que no sea la casilla.
3. En el control flotante de detalles del dominio que se abre, seleccione la pestaña **Registros DNS** . Anote el registro MX que se genera y asigna al inquilino de EOP.
4. Acceda a la zona DNS externa (pública) y compruebe el registro MX principal asociado al dominio de correo electrónico:
    - *Si el registro MX público coincide actualmente con la dirección EOP asignada (por ejemplo, contoso-com.mail.protection.outlook.com), no se deben requerir más cambios de enrutamiento*.
    - Si el registro MX público se resuelve actualmente en una puerta de enlace SMTP local o de terceros, es posible que se requieran configuraciones de enrutamiento adicionales.
    - Si el registro MX público se resuelve actualmente en Exchange local, es posible que todavía esté en un modelo híbrido en el que algún buzón de correo de destinatario aún no se haya migrado a EXO.

## <a name="step-2-audit-accepted-domains"></a>Paso 2: Auditar dominios aceptados

1. En el Centro de administración de Exchange (EAC) en <https://admin.exchange.microsoft.com>, expanda *Flujo de correo* y, a continuación, haga clic en **Dominios aceptados**. O bien, para ir directamente a la página *Dominios aceptados* , use <https://admin.exchange.microsoft.com/#/accepteddomains>.
2. En la página *Dominios aceptados* , anote el valor **de Tipo de dominio** del dominio de correo electrónico principal.
    - Si el tipo de dominio está establecido en **Autoritativo**, se supone que todos los buzones de correo de destinatario de la organización residen actualmente en Exchange Online.
    - Si el tipo de dominio está establecido en **InternalRelay** , es posible que todavía esté en un modelo híbrido en el que algunos buzones de correo de destinatario siguen residiendo en el entorno local.

## <a name="step-3-audit-inbound-connectors"></a>Paso 3: Auditoría de conectores de entrada

1. En el Centro de administración de Exchange (EAC) en <https://admin.exchange.microsoft.com>, expanda *Flujo de correoy*, a continuación, haga clic en **Conectores**. O bien, para ir directamente a la página *Conectores*, use <https://admin.exchange.microsoft.com/#/connectors>.
2. En la página *Conectores* , anote los conectores con la siguiente configuración:
   - El valor **From** es **una organización de asociados** que podría correlacionarse con una puerta de enlace SMTP de terceros.
   - El valor **De** es **Su organización** que podría indicar que sigue en un escenario híbrido.

## <a name="step-4-activate-the-evaluation"></a>Paso 4: Activar la evaluación

Siga estas instrucciones para activar la evaluación de Microsoft Defender para Office 365 desde el portal de Microsoft 365 Defender.

Para obtener información detallada, consulte [Probar Microsoft Defender para Office 365](../office-365-security/try-microsoft-defender-for-office-365.md).

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com> expandir *Email & colaboración*\>, seleccione **Directivas & reglas**\>, seleccione **Directivas** \> de amenazas desplácese hacia abajo hasta la sección *Otros* y, a continuación, seleccione **Modo de evaluación**. O bien, para ir directamente a la página *Modo de evaluación* , use <https://security.microsoft.com/atpEvaluation>.

2. En la página *Modo de evaluación* , haga clic en **Iniciar evaluación**.

   :::image type="content" source="../../media/mdo-eval/mdo-eval-activate-eval_05.png" alt-text="La página Modo de evaluación y el botón Iniciar evaluación para hacer clic." lightbox="../../media/mdo-eval/mdo-eval-activate-eval_05.png":::

3. En el cuadro de diálogo *Activar protección* , seleccione **No, Solo quiero informes** y, a continuación, haga clic en **Continuar**.

   :::image type="content" source="../../media/mdo-eval/mdo-eval-activate-eval_06.png" alt-text="El cuadro de diálogo Activar protección y la opción No, solo quiero que se seleccionen informes." lightbox="../../media/mdo-eval/mdo-eval-activate-eval_06.png":::

4. En el cuadro de diálogo *Seleccionar los usuarios que desea incluir* , seleccione **Todos los usuarios** y, a continuación, haga clic en **Continuar**.

   :::image type="content" source="../../media/mdo-eval/mdo-eval-activate-eval_07.png" alt-text="El cuadro de diálogo Seleccionar los usuarios que desea incluir y la opción Todos los usuarios que desea seleccionar." lightbox="../../media/mdo-eval/mdo-eval-activate-eval_07.png":::

5. En el cuadro de diálogo *Help us understand your mail flow (Ayudarnos a comprender el flujo de correo* ), se selecciona automáticamente una de las siguientes opciones en función de la detección del registro MX para su dominio:

   - **Solo estoy usando Microsoft Exchange Online**: los registros MX de su dominio apuntan a Microsoft 365. No queda nada que configurar, por lo que haga clic en **Finalizar**.

     :::image type="content" source="../../media/mdo-eval/mdo-eval-activate-eval_08a.png" alt-text="El cuadro de diálogo Help us understand your mail flow (Ayudarnos a comprender el flujo de correo) con la opción Solo estoy usando Microsoft Exchange Online seleccionada." lightbox="../../media/mdo-eval/mdo-eval-activate-eval_08a.png":::

   - **Estoy usando un proveedor de servicios local o de terceros**: en las próximas pantallas, seleccione el nombre del proveedor junto con el conector de entrada que acepta correo de esa solución. También decide si necesita una regla de flujo de correo Exchange Online (también conocida como regla de transporte) que omita el filtrado de correo no deseado para los mensajes entrantes desde el dispositivo o servicio de protección de terceros. Cuando haya terminado, haga clic en **Finalizar**.

## <a name="next-steps"></a>Pasos siguientes

Paso 3 de 3: Configurar el piloto para Microsoft Defender para Office 365

Vuelva a la introducción para [Evaluar Microsoft Defender para Office 365](eval-defender-office-365-overview.md)

Vuelva a la información general sobre [la evaluación y la Microsoft 365 Defender piloto](eval-overview.md)
