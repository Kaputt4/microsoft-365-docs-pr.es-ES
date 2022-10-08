---
title: Solución de problemas de análisis de uso de Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Obtenga información sobre cómo solucionar problemas con la aplicación de plantilla Análisis de uso de Microsoft 365.
ms.openlocfilehash: 6b6a293d1627ca4fc91836c0ae9a503903186330
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68165853"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Solución de problemas de análisis de uso de Microsoft 365

Explore la siguiente lista de mensajes de error para obtener ayuda con los problemas más comunes con el análisis de uso de Microsoft 365.
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>No podemos procesar su solicitud. Primero debe suscribirse a estos datos desde el Centro de administración de Microsoft 365

 **Código de error:** 422 
  
 **Donde verá este mensaje:** En Power BI al conectarse a la aplicación de plantilla análisis de uso de Microsoft 365 o al llamar directamente a las API de informes de Microsoft 365. 
  
 **Causa:** Para poder conectarse a la aplicación, debe suscribirse a los datos de la Centro de administración de Microsoft 365. Si este paso no se realiza primero, no podrá conectarse a la aplicación de plantilla, incluso si proporciona el identificador de inquilino de Microsoft 365. 
  
 **Para corregir este error:** Para suscribirse a los datos, vaya al Centro \> de administración **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">de uso</a> y busque el icono análisis de uso de Microsoft 365 en la página principal del panel. Seleccione el botón **Introducción** y, a continuación, en el panel **Informes** que se abre, active y **guarde** los **datos disponibles para análisis de uso de Microsoft 365 para Power BI**.
  
## <a name="we-are-processing-your-data"></a>Estamos procesando sus datos

 **Donde verá este mensaje:** En el icono **Análisis de uso de Microsoft 365** en el panel **Uso** de la Centro de administración de Microsoft 365. 
  
 **Causa:** Al [participar en la visualización de datos en la aplicación de plantilla](enable-usage-analytics.md) desde el Centro de administración de Microsoft 365, el sistema de Microsoft 365 comienza a generar datos de uso históricos para su organización. Según el tamaño del espacio empresarial, puede que este paso tarde en completarse de 2 a 48 horas. 
  
 **Para corregir esto:** Solo tenga paciencia, pero si el mensaje no cambia a **Sus datos está listo** después de 3 días, [póngase en contacto con El soporte técnico empresarial de Microsoft 365](Obtener soporte técnico](.. /get-help-support.md).
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>No podemos procesar su solicitud en este momento. Aún estamos preparando los datos para su organización

 **Código de error:** 423 
  
 **Donde verá este mensaje:** En Power BI, al conectarse a la aplicación de plantilla Análisis de uso de Microsoft 365 o al llamar directamente a las API de informes de Microsoft 365. 
  
 **Causa:** Al [participar en la visualización de datos en la aplicación de plantilla](enable-usage-analytics.md) desde el centro de administración, el sistema de Microsoft 365 comienza a generar datos de uso históricos para su organización. En función del tamaño del inquilino, este paso podría tardar entre dos horas y 48 horas. 
  
 **Para corregir esto:** Solo tenga paciencia, pero si el mensaje no cambia a **Sus datos está listo** incluso 3 días después del inicio, [póngase en contacto con Microsoft 365 para obtener soporte técnico empresarial](../../business-video/get-help-support.md).
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>El id. de espacio empresarial que especificó no tiene el formato correcto

 **Código de error:** 400 
  
 **Donde verá este mensaje:** En Power BI, al conectarse a la aplicación de plantilla Análisis de uso de Microsoft 365 o al llamar directamente a las API de informes de Microsoft 365. 
  
 **Causa:** El identificador de inquilino es un guid y tiene que tener el formato xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. Si escribe cualquier otra cadena en el cuadro de entrada del inquilino, obtendrá este error. 
  
 **Para corregir este error:** Vaya al Centro \> de administración **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">de uso</a> y busque el icono análisis de uso de Microsoft 365 en la página principal del panel. El identificador de inquilino aparece en el icono. Puede copiarlo desde aquí y pegarlo en el cuadro de diálogo para conectarse a la aplicación de plantilla. 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>El sistema no reconoce el id. de espacio empresarial que especificó

 **Código de error:** 404 
  
 **Donde verá este mensaje:** En Power BI al conectarse a la aplicación de plantilla análisis de uso de Microsoft 365 o al llamar directamente a las API de informes de Microsoft 365. 
  
 **Causa:** El identificador de inquilino proporcionado no es válido o no existe. 
  
 **Para corregir este error:** Vaya al Centro \> de administración **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">de uso</a> y busque el icono análisis de uso de Microsoft 365 en la página principal del panel. El identificador de inquilino aparece en el icono. Puede copiarlo desde aquí y pegarlo en el cuadro de diálogo para conectarse a la aplicación de plantilla. 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>Vuelva a escribir las credenciales para volver a iniciar sesión en Power BI

Código de error: 302
  
 **Donde verá este mensaje:** En Power BI al conectarse a la aplicación de plantilla análisis de uso de Microsoft 365 o al llamar directamente a las API de informes de Microsoft 365. 
  
 **Causa:** el código de autorización produjo errores y es posible que tenga que volver a escribir sus credenciales. 
  
 **Para solucionar este error:** cierre la sesión de Power BI y, después, vuelva a iniciarla. 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>You do not have the right authorization to access to this data. To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins

 **Código de error:** 403 
  
 **Donde verá este mensaje:** En Power BI al conectarse a la aplicación de plantilla análisis de uso de Microsoft 365 o al llamar directamente a las API de informes de Microsoft 365. 
  
 **Causa:** Error en el código de autorización porque el usuario que intentó conectarse a la aplicación de plantilla no tiene el nivel correcto de autorización para acceder a estos datos. 
  
 **Para corregir este error:** Proporcione las credenciales de un usuario que sea **administrador global**, **administrador de Exchange**, **administrador de Skype Empresarial**, **administrador de SharePoint**, **lector global** o **lector de** informes para conectarse a la aplicación de plantilla. Consulte [Acerca de los roles de administrador](../add-users/about-admin-roles.md) para obtener más información. 
  
## <a name="refresh-failed"></a>No se pudo actualizar

 **Donde verá este mensaje:** correo electrónico de Power BI o estado de error en el historial de actualizaciones. 
  
 **Causa:** En ocasiones, las credenciales del usuario que se ha conectado a la aplicación de plantilla se restablecen y no se actualizan en la configuración de conexión de la aplicación de plantilla, lo que provoca que el usuario vea errores de actualización. 
  
 **Para corregir este error:** En Power BI, busque el conjunto de datos correspondiente a la aplicación de plantilla Análisis de uso de Microsoft 365, seleccione **Programar actualización** y proporcione sus credenciales de administrador. 
  
Si no funciona, borre la memoria caché y vuelva a crear la aplicación de plantilla.
  
  
