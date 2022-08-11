---
title: Administrar comentarios de Microsoft para la organización
f1.keywords:
- NOCSH
ms.author: Kwekua
author: Kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
description: Administre los comentarios que los usuarios pueden enviar a Microsoft sobre los productos de Microsoft.
ms.openlocfilehash: d32b9f1150443bc4fc4e859004949d6f27b6914d
ms.sourcegitcommit: 6bff75867764335685f972943170c7db46e33a6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2022
ms.locfileid: "67300812"
---
# <a name="manage-microsoft-feedback-for-your-organization"></a>Administrar comentarios de Microsoft para la organización

Como administrador de una organización de Microsoft 365, ahora hay varias directivas que le ayudarán a administrar la recopilación de comentarios y la experiencia de participación del cliente de los usuarios al usar aplicaciones de Microsoft 365. Puede crear y usar grupos de Azure Active Directory existentes en su organización para cada una de estas directivas. Con estas directivas, puede controlar cómo los distintos departamentos de su organización pueden enviar comentarios a Microsoft. Microsoft revisa todos los comentarios enviados por los clientes y usa estos comentarios para mejorar el producto. Mantener activadas las experiencias de comentarios **le permite ver** lo que los usuarios dicen sobre los productos de Microsoft que usan. Los comentarios que recopilamos de los usuarios pronto estarán disponibles en la <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>.

Para obtener más información sobre los tipos de comentarios y cómo Microsoft usa los comentarios de los usuarios, consulte [Información sobre los comentarios de Microsoft para su organización](../misc/feedback-user-control.md).

La tabla siguiente representa qué aplicaciones y servicios están conectados actualmente a las directivas de comentarios que se muestran en la tabla de directivas de comentarios siguiente. Vea debajo de la tabla para ver ejemplos de captura de pantalla.

|**Aplicaciones & Services**|**Comentarios sobre los productos** <br> |**Encuestas en el producto** <br> |**Colección de metadatos** <br> |**Interacción con el cliente** <br> |
|:-----|:-----|:-----|:-----|:-----|
|**Access**|Sí|Sí|Sí|Sí|
|**Excel**|Sí|Sí|Sí|Sí|
|**Office.com**|Próximamente|Próximamente|Próximamente|Próximamente|
|**OneNote**|Sí|Sí|Sí|Sí|
|**OneDrive**|[Algunas configuraciones administradas actualmente por otros controles.](/onedrive/disable-contact-support-send-feedback)||||
|**Outlook**|Próximamente|Próximamente|Próximamente|Próximamente|
|**PowerPoint**|Sí|Sí|Sí|Sí|
|**Proyecto**|Próximamente|Próximamente|Próximamente|Próximamente|
|**Publicador**|Sí|Sí|Sí|Sí|
|**SharePoint**|[Algunas configuraciones administradas actualmente por otros controles.](/powershell/module/sharepoint-online/set-spotenant)||||
|**Teams**|[Algunas configuraciones administradas actualmente por otros controles.](/microsoftteams/manage-feedback-policies-in-teams)||||
|**Word**|Sí|Sí|Sí|Sí|
|**Visio**|Sí|Sí|Sí|Sí|
|**Yammer**|Sí|Sí|Sí|Sí|

[Consulte aquí algunos ejemplos de encuestas y comentarios en el producto.](/microsoft-365/admin/misc/feedback-user-control#in-product-surveys)

**Colección de metadatos**

:::image type="content" source="../../media/feedback-metadata2.png" alt-text="Captura de pantalla: página Comentarios que muestra el ejemplo de metadatos":::

**Interacción con el cliente**

:::image type="content" source="../../media/feedback-in-product-customer-engagement.png" alt-text="Captura de pantalla: Ejemplo de pregunta de investigación del cliente en el producto":::

## <a name="before-you-begin"></a>Antes de empezar

Los dispositivos deben tener un número mínimo de compilación para usar estas directivas. Consulte la tabla siguiente para obtener más información.

|**Construir #**|**Win32**|**iOS**|**Android**|**Mac**|**Web**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Comentarios sobre los productos|Al menos la versión 2010|Al menos 2,42|Al menos 16.0.13328|Al menos 16.42|Disponible públicamente|
|Encuestas en el producto|Al menos la versión 2010|Al menos 2,42|Al menos 16.0.13426|Al menos 16.42|Lanzamiento pendiente|
|Colección de metadatos|Al menos la versión 2010|Al menos 2,42|Al menos 16.0.13328|Al menos 16.42|Disponible públicamente|
|Interacción con el cliente|Al menos la versión 2010|Al menos 2,42|Al menos 16.0.13426|Al menos 16.42|Lanzamiento pendiente|

## <a name="specific-policies-you-can-configure"></a>Directivas específicas que puede configurar

### <a name="feedback-policies"></a>Directivas de comentarios

|**Nombre de la directiva**|**Estado predeterminado**|**Resumen de control**|
|:-----|:-----|:-----|
|Permitir a los usuarios acceder al portal de comentarios|Activada|Administración del acceso de los usuarios al portal de comentarios|
|Permitir que los usuarios envíen comentarios a Microsoft|Activada|Controla los puntos de entrada de comentarios entre las aplicaciones|
|Permitir que los usuarios reciban y respondan encuestas de Microsoft dentro de un producto|Activado|Controla las solicitudes de encuesta dentro del producto|
|Permitir que los usuarios incluyan capturas de pantalla y datos adjuntos cuando envíen comentarios a Microsoft|Desactivada|Determina qué metadatos puede decidir enviar el usuario con comentarios o encuestas|
|Permitir que Microsoft realice un seguimiento de los comentarios enviados por los usuarios|Desactivada|Determina si el usuario puede compartir información de contacto con comentarios o encuestas|
|Permitir que los usuarios incluyan archivos de registro y ejemplos de contenido cuando envíen comentarios a Microsoft|Desactivado|Determina los metadatos que el usuario puede decidir enviar con comentarios o encuestas.|

> [!NOTE]
> **La directiva Permitir a los usuarios acceder a la directiva del portal de comentarios** es una directiva en la nube. Esta directiva no está definida en ADMX y no tiene una clave del Registro correspondiente disponible para establecer la directiva. Debe crear una directiva en la nube para aplicarla. Se trata de una directiva en la nube porque el portal de comentarios es una aplicación web que realiza una llamada al servicio de directivas en la nube, que también es una aplicación web, solicitando las directivas para la persona que inicia sesión. Si se configura esta directiva, el portal de comentarios recibirá el valor de directiva configurado en la respuesta del servicio de directivas en la nube.

## <a name="configure-policies"></a>Configuración de directivas

Para configurar estas opciones de directiva, puede usar el servicio de directivas en la nube de Office. Para obtener más información, vea [Información general del servicio de directivas en la nube de Office](/deployoffice/overview-office-cloud-policy-service). Puede buscar "comentarios" o "encuesta" en la interfaz de usuario del servicio de directivas en la nube de Office para encontrar la configuración de directiva para configurarlas. 

Esta configuración de directiva también está disponible si usa directiva de grupo. Para usar esta configuración de directiva, descargue al menos la versión 5146.1000 de los [archivos de plantilla administrativa (ADMX/ADML),](https://www.microsoft.com/download/details.aspx?id=49030) publicada el 22 de marzo de 2021.

Puede encontrar esta configuración de directiva en Configuración de usuario\Directivas\Plantillas administrativas\Microsoft Office 2016\Privacidad\Centro de confianza.

> [!NOTE]
> Las aplicaciones cliente tardan unas horas en actualizarse.
