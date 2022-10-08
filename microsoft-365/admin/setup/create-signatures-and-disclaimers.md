---
title: Creación de firmas y declinaciones de responsabilidades para toda la organización
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- highpri
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- VSBFY23
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-may2020
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- adminvideo
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: Administre las firmas de correo electrónico, incluidas las declaraciones de divulgación o declinación de responsabilidades legales para todos los mensajes de correo electrónico que entran o salen de su organización.
ms.openlocfilehash: e1c9d9d449e3e6f49ac405bdbd34ab67a2c01daf
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68166513"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>Creación de firmas y declinaciones de responsabilidades para toda la organización

Consulte [ayuda de Microsoft 365 para pequeñas empresas](https://go.microsoft.com/fwlink/?linkid=2197659) en YouTube.

 Puede administrar las firmas de correo electrónico agregando una firma de correo electrónico, una declinación de responsabilidad legal o una declaración de divulgación a los mensajes de correo electrónico que entran o salen de su organización. Puede configurarlo para que se aplique a todos los mensajes entrantes y salientes, como se muestra a continuación. O puede aplicarlo a determinados mensajes; por ejemplo, a aquellos que contengan palabras específicas o patrones de texto.

## <a name="watch-create-a-company-wide-email-signature"></a>Inspección: Creación de una firma de correo electrónico para toda la empresa
  
Consulte este vídeo y otros en nuestro [canal de YouTube](https://go.microsoft.com/fwlink/?linkid=2198031).

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

1. En el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>, seleccione **Exchange**.
1. Seleccione **Flujo de correo**.
1. Seleccione **Agregar +** y, a continuación, seleccione **Aplicar declinaciones de responsabilidades**.
1. En la página **Nueva regla** , complete los pasos. 

Si este vídeo le ha sido de ayuda, consulte la [serie completa de aprendizaje para las pequeñas empresas y las novedades de Microsoft 365](../../business-video/index.yml).

## <a name="create-a-signature-that-applies-to-all-messages"></a>Crear una firma que se aplique a todos los mensajes

> [!TIP]
> Las firmas de toda la organización se denominan "declinaciones de responsabilidades", independientemente de lo que incluyan. Por ejemplo, pueden ser simplemente una firma o incluir también su dirección, declinación de responsabilidad legal u otra información que desee.
    
::: moniker range="o365-worldwide"

Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-21vianet"

Vaya al Centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a>.

::: moniker-end

1. Seleccione el iniciador ![de aplicaciones Icono del iniciador](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) de aplicaciones y, a continuación, seleccione **Administración**.
   
    ¿No encuentra la aplicación que busca? En el iniciador de aplicaciones, seleccione **Todas las aplicaciones** para ver una lista alfabética de las aplicaciones disponibles. Ahí podrá buscar una aplicación específica. 
    
2. Seleccione **Administración centros** y, a continuación, elija **Exchange**.
    
3. En Flujo de correo, seleccione **Reglas**.
    
4. Seleccione el **+** icono (Agregar) y elija **Aplicar declinaciones de responsabilidades**.
    
5. Asigne un nombre a la regla.
    
6. En **Aplicar esta regla**, seleccione **[Aplicar a todos los mensajes]**.
    
    > [!TIP]
    > [Obtenga más información](/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping) sobre cómo especificar condiciones si no quiere que el aviso de declinación de responsabilidades se aplique a todos los mensajes. (Este artículo de ámbito es para Exchange Server, pero también se aplica a Microsoft 365). 
  
7. En Realizar lo siguiente, deje la opción **Anexar el aviso de declinación de responsabilidades** seleccionada. 
    
8.  Seleccione **Escribir texto** y escriba su declinación de responsabilidades. 
    
    > [!TIP]
    > [Obtenga más información](/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer) sobre cómo aplicar formato a los avisos de declinación de responsabilidades. (Este artículo de formato es para Exchange Server, pero también se aplica a Microsoft 365). 

9. Seleccione **Seleccionar uno** y elija **la opción Ajustar** como reserva. Después, seleccione **Aceptar**. Esto significa que, si no se puede agregar el aviso de declinación de responsabilidades debido al cifrado o a otra configuración del correo, este se ajustará en un sobre de mensajes.
    
10. Deje la opción **Auditar esta regla con nivel de gravedad** seleccionada. Después, elija qué opción quiere usar en el registro de mensajes: **Bajo**, **Medio** o **Alto**. 
    
11. Elija **Exigir** para activar el aviso de declinación de responsabilidades inmediatamente, a menos que quiera probarlo primero. 
    
12. Elija **Más opciones** para incluir excepciones o condiciones adicionales. 
    
13. Cuando termine, pulse **Guardar**. 
    
## <a name="limitations-of-organization-wide-signatures"></a>Limitaciones de las firmas de toda la organización

No puede hacer lo siguiente al administrar firmas de correo electrónico en Microsoft 365:
  
- Inserte la firma directamente en la respuesta o reenvío de correo electrónico más reciente.
    
- Mostrar firmas de correo electrónico del lado servidor en las carpetas de elementos enviados de los usuarios
    
- Insertar imágenes en firmas de correo electrónico
    
- Omitir líneas que contienen variables que no se pudieron actualizar (por ejemplo, porque el valor no se proporcionó para un usuario)
    
Para obtener estas y otras funcionalidades para administrar firmas de correo electrónico, use una herramienta de terceros. Realice una búsqueda en Internet del **software de firma de correo electrónico**. Varios de estos proveedores son asociados de Microsoft Gold y su software proporciona estas funcionalidades. 
  
## <a name="more-resources"></a>Más recursos

Para obtener información sobre el uso de PowerShell, consulte [Declinaciones de responsabilidades de mensajes de toda la organización, firmas, pies de página o encabezados en Exchange Online](/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers).

## <a name="related-content"></a>Contenido relacionado

[Migración de correo electrónico y contactos a Microsoft 365](migrate-email-and-contacts-admin.md) (vídeo)\
[Configuración del correo electrónico del usuario](../email/office-365-user-email-settings.md) (artículo)\
[Información general del Centro de administración de Microsoft 365] (Información general del Centro de administración de Microsoft 365] (../admin-overview/admin-center-overview.md) (vídeo)

