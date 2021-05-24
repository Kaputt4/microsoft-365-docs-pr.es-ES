---
title: Crear firmas y avisos de declinación de responsabilidades en toda la organización
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
- seo-marvel-may2020
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: Administrar firmas de correo electrónico, incluidas declinaciones de responsabilidades legales o declaraciones de divulgación para todos los mensajes de correo electrónico que entran o salen de la organización.
ms.openlocfilehash: f72d522c7dc592a7f719d716e22ecf726d00a6de
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635659"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>Crear firmas y avisos de declinación de responsabilidades en toda la organización

 Puede administrar firmas de correo electrónico agregando una firma de correo electrónico, un aviso legal o una declaración de divulgación a los mensajes de correo electrónico que entran o salen de su organización. Puede configurarlo para que se aplique a todos los mensajes entrantes y salientes, como se muestra a continuación. O puede aplicarlo a determinados mensajes; por ejemplo, a aquellos que contengan palabras específicas o patrones de texto.

## <a name="watch-create-a-company-wide-email-signature"></a>Watch: Create a company-wide email signature
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](../../business-video/index.yml).

## <a name="create-a-signature-that-applies-to-all-messages"></a>Crear una firma que se aplique a todos los mensajes

> [!TIP]
> Las firmas de toda la organización se denominan "declinaciones de responsabilidades", independientemente de lo que incluyan. Por ejemplo, pueden ser solo una firma, o también incluir su dirección, declinación de responsabilidades legales u otra información que desee.
    
::: moniker range="o365-worldwide"

Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a>.

::: moniker-end

1. Selecciona el iniciador de aplicaciones ![ El icono del iniciador de aplicaciones ](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) y, a continuación, selecciona **Administrador**.
   
    ¿No encuentra la aplicación que busca? En el iniciador de aplicaciones, selecciona **Todas las aplicaciones** para ver una lista alfabética de las aplicaciones disponibles. Ahí podrá buscar una aplicación específica. 
    
2. Seleccione **Centros de administración** y, a **continuación, Exchange**.
    
3. En Flujo de correo, seleccione **Reglas**.
    
4. Seleccione el **+** icono (Agregar) y elija **Aplicar avisos de declinación de responsabilidades.**
    
5. Asigne un nombre a la regla.
    
6. En **Aplicar esta regla,** seleccione **[Aplicar a todos los mensajes]**.
    
    > [!TIP]
    > [Obtenga más información](/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping) sobre cómo especificar condiciones si no quiere que el aviso de declinación de responsabilidades se aplique a todos los mensajes. (Este artículo de ámbito es Exchange Server, pero también se aplica a Microsoft 365). 
  
7. En Realizar lo siguiente, deje la opción **Anexar el aviso de declinación de responsabilidades** seleccionada. 
    
8.  Seleccione **Escribir texto y** escriba su declinación de responsabilidades. 
    
    > [!TIP]
    > [Obtenga más información](/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer) sobre cómo aplicar formato a los avisos de declinación de responsabilidades. (Este artículo de formato es para Exchange Server, pero también se aplica a Microsoft 365). 

9. Seleccione **Seleccionar uno** y elija **Ajustar** como opción de reserva. Después, seleccione **Aceptar**. Esto significa que, si no se puede agregar el aviso de declinación de responsabilidades debido al cifrado o a otra configuración del correo, este se ajustará en un sobre de mensajes.
    
10. Deje la opción **Auditar esta regla con nivel de gravedad** seleccionada. Después, elija qué opción quiere usar en el registro de mensajes: **Bajo**, **Medio** o **Alto**. 
    
11. Elija **Exigir** para activar el aviso de declinación de responsabilidades inmediatamente, a menos que quiera probarlo primero. 
    
12. Elija **Más opciones** para incluir excepciones o condiciones adicionales. 
    
13. Cuando termine, pulse **Guardar**. 
    
## <a name="limitations-of-organization-wide-signatures"></a>Limitaciones de firmas de toda la organización

No puede hacer lo siguiente al administrar firmas de correo electrónico en Microsoft 365:
  
- Insertar la firma directamente debajo de la respuesta o reenvío de correo electrónico más reciente
    
- Mostrar firmas de correo electrónico del lado servidor en carpetas de elementos enviados de los usuarios
    
- Insertar imágenes en firmas de correo electrónico
    
- Omitir líneas que contienen variables que no se pudieron actualizar (por ejemplo, porque el valor no se proporcionó para un usuario)
    
Para obtener estas y otras capacidades para administrar firmas de correo electrónico, use una herramienta de terceros. Realice una búsqueda en Internet para el **software de firma de correo electrónico**. Varios de estos proveedores son socios de Microsoft Gold y su software proporciona estas capacidades. 
  
## <a name="more-resources"></a>Más recursos

Para obtener información acerca del uso de PowerShell, vea Avisos de declinación de responsabilidades de [mensajes, firmas,](/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)pies de página o encabezados de toda la organización en Exchange Online .

## <a name="related-content"></a>Contenido relacionado

[Migrar correo electrónico y contactos a Microsoft 365](migrate-email-and-contacts-admin.md) (vídeo)\
[Configuración de correo electrónico del](../email/office-365-user-email-settings.md) usuario (artículo)\
[Información general del Centro de administración de Microsoft 365](../../business-video/admin-center-overview.md) (vídeo)

