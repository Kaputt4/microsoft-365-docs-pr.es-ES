---
title: Solución de problemas de análisis de uso de Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Obtenga información sobre cómo solucionar problemas relacionados con la aplicación de plantilla de análisis de uso de Microsoft 365.
ms.openlocfilehash: 4696dd0c5140cdc110781c226819fc64a90fae1b
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402039"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Solución de problemas de análisis de uso de Microsoft 365

Explore la siguiente lista de mensajes de error para obtener ayuda con los problemas más comunes con el análisis de uso de Microsoft 365.
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>No podemos procesar su solicitud. Primero tiene que suscribirse a estos datos desde el centro de administración de Microsoft 365

 **Código de error:** 422 
  
 **Donde verá este mensaje:** En Power BI cuando se conecta a la aplicación de plantilla de análisis de uso de Microsoft 365 o al llamar directamente a las API de informes de Microsoft 365. 
  
 **Causa:** Antes de poder conectarse a la aplicación, tiene que suscribirse a los datos desde el centro de administración de 365 de Microsoft. Si este paso no se realiza primero, no podrás conectar con la aplicación de plantilla, incluso si proporcionas tu identificador de inquilino de 365 de Microsoft. 
  
 **Para solucionar este error:** Para suscribirse a los datos, vaya al centro de administración \> **informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">uso</a> y busque el icono de análisis de uso de Microsoft 365 en la Página principal del panel. Seleccione el botón **Introducción** y, a continuación, en el panel de **informes** que se abre, active la opción hacer que los **datos estén disponibles en análisis de uso de Microsoft 365 para Power BI** en y **guarde**.
  
## <a name="we-are-processing-your-data"></a>Estamos procesando sus datos

 **Donde verá este mensaje:** En el mosaico de **análisis de uso de microsoft 365** , en el panel de **uso** del centro de administración de Microsoft 365. 
  
 **Causa:** Cuando se [opta por ver los datos en la aplicación de plantilla](enable-usage-analytics.md) desde el centro de administración de Microsoft 365, el sistema Microsoft 365 comienza a generar datos de uso históricos para la organización. Según el tamaño del espacio empresarial, puede que este paso tarde en completarse de 2 a 48 horas. 
  
 **Para solucionar esto:** Solo es paciente, pero si el mensaje no cambia a **sus datos están listos** después de tres días, [póngase en contacto con el soporte técnico de 365 para empresas de Microsoft](../contact-support-for-business-products.md).
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>No podemos procesar su solicitud en este momento. Aún estamos preparando los datos para su organización

 **Código de error:** 423 
  
 **Donde verá este mensaje:** En Power BI cuando se conecta a la aplicación de plantilla de análisis de uso de Microsoft 365 o al llamar directamente a las API de informes de Microsoft 365. 
  
 **Causa:** Cuando se [opta por ver los datos en la aplicación de plantilla](enable-usage-analytics.md) desde el centro de administración, el sistema Microsoft 365 comienza a generar datos de uso históricos para la organización. Según el tamaño del espacio empresarial, puede que este paso tarde en completarse de 2 a 48 horas. 
  
 **Para solucionar esto:** Solo es paciente, pero si el mensaje no cambia a **sus datos está listo** incluso durante 3 días desde el inicio, [póngase en contacto con el soporte técnico de Microsoft 365 para empresas](../contact-support-for-business-products.md).
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>El id. de espacio empresarial que especificó no tiene el formato correcto

 **Código de error:** 400 
  
 **Donde verá este mensaje:** En Power BI cuando se conecta a la aplicación de plantilla de análisis de uso de Microsoft 365 o al llamar directamente a las API de informes de Microsoft 365. 
  
 **Causa:** el id. de espacio empresarial es un GUID y necesita estar en el formato xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. Si escribe cualquier otra cadena en el cuadro de entrada del espacio empresarial, obtendrá este error. 
  
 **Para solucionar este error:** Vaya al centro de administración de \> **informes** de \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">uso</a> y busque el icono de análisis de uso de Microsoft 365 en la página del panel principal. El identificador de inquilino aparece en el icono. Puede copiarla desde aquí y pegarla en el cuadro de diálogo para conectarse a la aplicación de plantilla. 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>El sistema no reconoce el id. de espacio empresarial que especificó

 **Código de error:** 404 
  
 **Donde verá este mensaje:** En Power BI cuando se conecta a la aplicación de plantilla de análisis de uso de Microsoft 365 o al llamar directamente a las API de informes de Microsoft 365. 
  
 **Causa:** el id. de espacio empresarial que especificó no es válido o no existe. 
  
 **Para solucionar este error:** Vaya al centro de administración de \> **informes** de \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">uso</a> y busque el icono de análisis de uso de Microsoft 365 en la página del panel principal. El identificador de inquilino aparece en el icono. Puede copiarla desde aquí y pegarla en el cuadro de diálogo para conectarse a la aplicación de plantilla. 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>Vuelva a escribir las credenciales para volver a iniciar sesión en Power BI

Código de error: 302
  
 **Donde verá este mensaje:** En Power BI cuando se conecta a la aplicación de plantilla de análisis de uso de Microsoft 365 o al llamar directamente a las API de informes de Microsoft 365. 
  
 **Causa:** el código de autorización produjo errores y es posible que tenga que volver a escribir sus credenciales. 
  
 **Para solucionar este error:** cierre la sesión de Power BI y, después, vuelva a iniciarla. 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>No tiene la autorización correcta para obtener acceso estos datos. Para obtener acceso a los datos desde este servicio, necesita ser administrador global o uno de los administradores del producto

 **Código de error:** 403 
  
 **Donde verá este mensaje:** En Power BI cuando se conecta a la aplicación de plantilla de análisis de uso de Microsoft 365 o al llamar directamente a las API de informes de Microsoft 365. 
  
 **Causa:** El código de autorización falló porque el usuario que intentó conectarse a la aplicación de plantilla no tiene el nivel correcto de autorización para obtener acceso a estos datos. 
  
 **Para solucionar este error:** Proporcione las credenciales de un usuario que sea un **administrador global**, el administrador de **Exchange**, el **Administrador de Skype empresarial**, el **Administrador de SharePoint**, el lector **global** o el **lector de informes** para conectarse a la aplicación de plantilla. Para obtener más información, vea acerca de los [roles de administrador](../add-users/about-admin-roles.md) . 
  
## <a name="refresh-failed"></a>No se pudo actualizar

 **Donde verá este mensaje:** correo electrónico de Power BI o estado de error en el historial de actualizaciones. 
  
 **Causa:** A veces, las credenciales del usuario que se conectó a la aplicación de plantilla se restablecen y no se actualizan en la configuración de conexión de la aplicación de plantilla, lo que hace que el usuario vea errores de actualización. 
  
 **Para solucionar este error:** En Power BI, busque el conjunto de aplicaciones correspondiente a la aplicación de plantilla de análisis de uso de Microsoft 365, seleccione **programar actualización** y proporcione sus credenciales de administrador. 
  
Si esto no funciona, borra la memoria caché y vuelve a crear la aplicación de plantilla.
  
  
