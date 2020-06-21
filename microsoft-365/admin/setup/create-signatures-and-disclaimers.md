---
title: Crear firmas y avisos de declinación de responsabilidad en toda la organización
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: Obtenga información sobre cómo agregar una firma de correo electrónico, una declinación de responsabilidades o una declaración de divulgación a todos los mensajes de correo electrónico que entran o salen de la organización.
ms.openlocfilehash: d7e19c6e3f425f95429aefd769d2b8992fde141e
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779886"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>Crear firmas y avisos de declinación de responsabilidad en toda la organización

 You can add an email signature, legal disclaimer, or disclosure statement to the email messages that enter or leave your organization. You can set it up to apply to all incoming and outgoing messages as shown below. Or you can apply it to certain messages like those containing specific words or text patterns.

 Vea un breve vídeo sobre cómo crear una firma de correo electrónico de toda la empresa. <br><br>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="create-a-signature-that-applies-to-all-messages"></a>Crear una firma que se aplique a todos los mensajes

> [!TIP]
> Las firmas de toda la organización se denominan "declinación de responsabilidad", independientemente de lo que incluyan. Por ejemplo, pueden ser simplemente una firma o incluir su dirección, la declinación de responsabilidades legal u otra información que desee.
    
::: moniker range="o365-worldwide"

Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a>.

::: moniker-end

1. Seleccione el iniciador ![ de aplicaciones el icono del iniciador de aplicaciones ](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) y, a continuación, seleccione **Administración**.
   
    ¿No encuentra la aplicación que busca? En el iniciador de aplicaciones, seleccione **todas las aplicaciones** para ver una lista alfabética de las aplicaciones disponibles para usted. Ahí podrá buscar una aplicación específica. 
    
2. Seleccione **centros de administración**y, a continuación, elija **Exchange**.
    
3. En flujo de correo, seleccione **reglas**.
    
4. Seleccione el **+** icono (agregar) y elija **aplicar avisos de declinación de responsabilidad**.
    
5. Asigne un nombre a la regla.
    
6. En **aplicar esta regla**, seleccione **[aplicar a todos los mensajes]**.
    
    > [!TIP]
    > [Obtenga más información](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping) sobre cómo especificar condiciones si no quiere que el aviso de declinación de responsabilidades se aplique a todos los mensajes. (Este artículo de ámbito es para Exchange Server, pero también se aplica a Microsoft 365). 
  
7. En Realizar lo siguiente, deje la opción **Anexar el aviso de declinación de responsabilidades** seleccionada. 
    
8.  Seleccione **escribir texto** y escriba el aviso de declinación de responsabilidades. 
    
    > [!TIP]
    > [Obtenga más información](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer) sobre cómo aplicar formato a los avisos de declinación de responsabilidades. (Este artículo de formato es para Exchange Server, pero también se aplica a Microsoft 365). 

9. Seleccione **seleccionar una** y elija **ajustar** como opción de reserva. Después, seleccione **Aceptar**. Esto significa que, si no se puede agregar el aviso de declinación de responsabilidades debido al cifrado o a otra configuración del correo, este se ajustará en un sobre de mensajes.
    
10. Leave **Audit this rule with severity level** selected. Then choose **Low**, **Medium**, or **High** to be used in the message log. 
    
11. Elija **Exigir** para activar el aviso de declinación de responsabilidades inmediatamente, a menos que quiera probarlo primero. 
    
12. Elija **Más opciones** para incluir excepciones o condiciones adicionales. 
    
13. Cuando termine, pulse **Guardar**. 
    
## <a name="limitations-of-organization-wide-signatures"></a>Limitaciones de las firmas de toda la organización

No puede hacer lo siguiente con las firmas 365 de Microsoft:
  
- Insertar la firma directamente bajo la última respuesta de correo electrónico o reenvío
    
- Mostrar firmas de correo electrónico del servidor en las carpetas de elementos enviados de los usuarios
    
- Insertar imágenes en firmas de correo electrónico
    
- Saltar líneas que contienen variables que no se pudieron actualizar (por ejemplo, porque el valor no se proporcionó para un usuario)
    
Para obtener estas y otras funciones, use una herramienta de terceros. Realice una búsqueda en Internet de **software de firma de correo electrónico**. Varios de estos proveedores son Partners Gold de Microsoft y su software proporciona estas capacidades. 
  
## <a name="more-resources"></a>Más recursos

- Consulte [renuncias de mensajes de toda la organización, firmas, pies de página o encabezados en Microsoft 365](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers) para obtener información sobre el uso de PowerShell. 
    

