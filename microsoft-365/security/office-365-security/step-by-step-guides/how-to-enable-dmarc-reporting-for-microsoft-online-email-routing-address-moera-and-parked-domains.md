---
title: Cómo habilitar dmarc reporting for Microsoft Online Email Routing Address (MOERA) and parked Domains
description: Los pasos para configurar DMARC para MOERA y dominios estacionados.
search.product: ''
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
search.appverid: met150
ms.openlocfilehash: 231fce344ef9b9b617f58bc3a355ea748283e8ba
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2022
ms.locfileid: "67741266"
---
# <a name="how-to-enable-dmarc-reporting-for-microsoft-online-email-routing-address-moera-and-parked-domains"></a>Cómo habilitar dmarc reporting for Microsoft Online Email Routing Address (MOERA) and parked Domains

El procedimiento recomendado para la protección de la seguridad del correo electrónico de dominio es protegerse contra la suplantación de identidad mediante la autenticación de mensajes basada en dominio, la generación de informes y la conformidad (DMARC). Si aún no ha habilitado DMARC para los dominios, debe ser el primer paso, que se detalla aquí: Autenticación de [mensajes basada en dominio, informes y conformidad (DMARC)](/microsoft-365/security/office-365-security/use-dmarc-to-validate-email)

Esta guía está diseñada para ayudarle a configurar DMARC para dominios no cubiertos por el artículo principal de DMARC. Estos dominios incluyen dominios que no se usan para el correo electrónico, pero que los atacantes podrían aprovechar si permanecen desprotegidos:

- Su `onmicrosoft.com` dominio, también conocido como dominio de direcciones de enrutamiento de Email (MOERA) de Microsoft Online.
- Dominios personalizados estacionados que aún no está usando para el correo electrónico.

## <a name="what-youll-need"></a>Lo que necesitará

- Centro de administración de Microsoft 365 y acceso al proveedor DNS que hospeda los dominios.
- Permisos suficientes como Administración global para realizar los cambios adecuados en el Centro de administración de Microsoft 365.
- 10 minutos para completar los pasos de este artículo.

## <a name="activate-dmarc-for-moera-domain"></a>Activación de DMARC para el dominio MOERA

1. Abra el Centro de administración de Microsoft 365 en <https://admin.microsoft.com>.
1. En el panel de navegación izquierdo, seleccione **Mostrar todo**.
1. Expanda **Configuración** y presione **Dominios**.
1. Seleccione el dominio de inquilino (por ejemplo, contoso.onmicrosoft.com).
1. En la página que se carga, seleccione **Registros DNS**.
1. Seleccione **+ Agregar registro**.
1. Aparecerá un control flotante a la derecha. Asegúrese de que el tipo seleccionado es **TXT (texto).**
1. Agregue `_dmarc` como **nombre TXT**.
1. Agregue el valor de DMARC específico.
1. Presione **Guardar**.

## <a name="active-dmarc-for-parked-domains"></a>DMARC activo para dominios estacionados

1. Compruebe si SPF ya está configurado para el dominio estacionado. Para obtener instrucciones, consulte [Configuración de SPF para ayudar a evitar la suplantación de identidad: Office 365 | Microsoft Docs](/microsoft-365/security/office-365-security/set-up-spf-in-office-365-to-help-prevent-spoofing#how-to-handle-subdomains)
1. Póngase en contacto con el proveedor de dominio DNS.
1. Pida que agregue este registro txt de DMARC con las direcciones de correo electrónico adecuadas: `v=DMARC1; p=reject; rua=mailto:d@rua.contoso.com;ruf=mailto:d@ruf.contoso.com`.

## <a name="next-steps"></a>Pasos siguientes

Espere hasta que se propaguen los cambios de DNS e intente suplantar los dominios configurados. Compruebe si el intento está bloqueado en función del registro DMARC y recibe un informe de DMARC.

## <a name="more-information"></a>Más información

[Configuración de SPF para ayudar a evitar la suplantación de identidad: Office 365 | Microsoft Docs](/microsoft-365/security/office-365-security/set-up-spf-in-office-365-to-help-prevent-spoofing)

[Uso de DMARC para validar el correo electrónico y los pasos de configuración: Office 365 | Microsoft Docs](/microsoft-365/security/office-365-security/use-dmarc-to-validate-email)
