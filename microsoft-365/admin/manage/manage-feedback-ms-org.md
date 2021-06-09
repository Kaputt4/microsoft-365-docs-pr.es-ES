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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Administrar comentarios que los usuarios pueden enviar a Microsoft acerca de los productos de Microsoft.
ms.openlocfilehash: 70ea1d5c176dd603f6a5addb09356909f13f9ace
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840675"
---
# <a name="manage-microsoft-feedback-for-your-organization"></a>Administrar comentarios de Microsoft para la organización

Como administrador de una organización Microsoft 365, ahora hay varias directivas que le ayudarán a administrar la recopilación de comentarios y la experiencia de participación del cliente de los usuarios al usar Microsoft 365 aplicaciones. Puede crear y usar grupos de Azure Active Directory existentes en su organización para cada una de estas directivas. Con estas policías, puede controlar cómo los distintos departamentos de su organización pueden enviar comentarios a Microsoft. Microsoft revisa todos los comentarios enviados por los clientes y usa estos comentarios para mejorar el producto. Mantener activadas las **experiencias** de comentarios te permite ver lo que los usuarios están diciendo acerca de los productos de Microsoft que usan. Los comentarios que recopilamos de los usuarios pronto estarán disponibles en el centro Microsoft 365 administración.

Para obtener más información sobre los tipos de comentarios y el modo en que Microsoft usa los comentarios de los usuarios, vea [Learn about Microsoft feedback for your organization](../misc/feedback-user-control.md).

La tabla siguiente representa qué aplicaciones y servicios están conectados actualmente a las directivas de comentarios que se muestran en la siguiente tabla de directivas de comentarios. Consulta debajo de la tabla ejemplos de capturas de pantalla.

|**Servicios & aplicaciones**|**Comentarios en el producto** <br> |**Encuestas desde el producto** <br> |**Colección Metadata** <br> |**Participación del cliente** <br> |
|:-----|:-----|:-----|:-----|:-----|
|**Access**|Sí|Sí|Sí|Sí|
|**Excel**|Sí|Sí|Sí|Sí|
|**Office.com**|Próximamente|Próximamente|Próximamente|Próximamente|
|**OneNote**|Sí|Sí|Sí|Sí|
|**OneDrive**|[Algunas opciones de configuración administradas actualmente por otros controles.](/onedrive/disable-contact-support-send-feedback)||||
|**Outlook**|Próximamente|Próximamente|Próximamente|Próximamente|
|**PowerPoint**|Sí|Sí|Sí|Sí|
|**Project**|Próximamente|Próximamente|Próximamente|Próximamente|
|**Publicador**|Sí|Sí|Sí|Sí|
|**SharePoint**|[Algunas opciones de configuración administradas actualmente por otros controles.](/powershell/module/sharepoint-online/set-spotenant)||||
|**Teams**|[Algunas opciones de configuración administradas actualmente por otros controles.](/microsoftteams/manage-feedback-policies-in-teams)||||
|**Word**|Sí|Sí|Sí|Sí|
|**Visio**|Sí|Sí|Sí|Sí|
|**Yammer**|Sí|Sí|Sí|Sí|

[Vea aquí algunos ejemplos de encuestas y comentarios dentro del producto.](/microsoft-365/admin/misc/feedback-user-control#in-product-surveys)

**Colección Metadata**

:::image type="content" source="../../media/feedback-metadata2.png" alt-text="Captura de pantalla: página de comentarios que muestra un ejemplo de metadatos":::

**Participación del cliente**

:::image type="content" source="../../media/feedback-in-product-customer-engagement.png" alt-text="Captura de pantalla: ejemplo de pregunta de investigación de clientes en el producto":::

## <a name="before-you-begin"></a>Antes de empezar

Los dispositivos deben tener un número de compilación mínimo para usar estas directivas. Vea la tabla siguiente para obtener más información.

|**Compilación #**|**Win32**|**iOS**|**Android**|**Mac**|**Web**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Comentarios en el producto|Al menos 16.0.13328|Al menos 2,42|Al menos 16.0.13328|Al menos 16,42|Disponible públicamente|
|Encuestas desde el producto|Al menos 16.0.13328|Al menos 2,42|Al menos 16.0.13426|Al menos 16,42|Implementación pendiente|
|Colección Metadata|Al menos 16.0.13328|Al menos 2,42|Al menos 16.0.13328|Al menos 16,42|Disponible públicamente|
|Participación del cliente|Al menos 16.0.13328|Al menos 2,42|Al menos 16.0.13426|Al menos 16,42|Implementación pendiente|

## <a name="specific-policies-you-can-configure"></a>Directivas específicas que puede configurar

### <a name="feedback-policies"></a>Directivas de comentarios

|**Nombre de la directiva**|**Estado predeterminado**|**Resumen de control**|
|:-----|:-----|:-----|
|Permitir a los usuarios enviar comentarios a Microsoft|Activado|Controla los puntos de entrada de comentarios en todas las aplicaciones|
|Permitir que los usuarios reciban y respondan a encuestas en el producto de Microsoft|Activado|Controles de mensajes de encuesta dentro del producto|
|Permitir que los usuarios incluyan capturas de pantalla y datos adjuntos cuando envíen comentarios a Microsoft|Desactivado|Determina qué metadatos puede enviar el usuario con comentarios o encuestas|
|Permitir que Microsoft realice un seguimiento de los comentarios enviados por los usuarios|Desactivado|Determina si el usuario puede compartir información de contacto con comentarios/encuestas|
|Permitir a los usuarios incluir archivos de registro y ejemplos de contenido cuando se envían comentarios a Microsoft|Desactivado|Determina los metadatos que el usuario puede decidir enviar con comentarios o encuestas|

## <a name="configure-policies"></a>Configurar directivas

1. Vaya a [https://config.office.com](https://config.office.com) e inicie sesión como usuario con permisos de administrador global.
1. Seleccione **Personalización** y **administración de directivas.**
1. Seleccione **Crear**.
1. Escriba **el nombre** y la **descripción**.
1. Elija los grupos de Azure Active Directory que desea configurar.
1. Buscar comentarios **y** **encuestas**.
1. Para cada directiva enumerada, establezca el valor que desee.

Para obtener más información, vea [Overview of the Office cloud policy service](/deployoffice/overview-office-cloud-policy-service).

Esta configuración de directiva también está disponible si usa la directiva de grupo. Para usar esta configuración de directiva, descargue al menos la versión 5146.1000 de los archivos de plantilla administrativa [(ADMX/ADML),](https://www.microsoft.com/download/details.aspx?id=49030)publicado el 22 de marzo de 2021.

Puede encontrar esta configuración de directiva en Configuración de usuario -> Directivas -> Plantillas administrativas -> Microsoft Office 2016 -> Privacidad -> Confianza.

> [!NOTE]
> Las aplicaciones cliente tardan unas horas en actualizarse.
