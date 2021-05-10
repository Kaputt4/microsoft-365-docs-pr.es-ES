---
title: Solución de problemas Microsoft 365 análisis de uso
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Obtén información sobre cómo solucionar problemas con la Microsoft 365 de plantilla análisis de uso.
ms.openlocfilehash: 74ee32ae015421a2352474daefa0eaa0a53fbbc9
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52293740"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Solución de problemas Microsoft 365 análisis de uso

Explore la siguiente lista de mensajes de error para obtener ayuda con los problemas más comunes con Microsoft 365 análisis de uso.
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>No podemos procesar su solicitud. Primero debe suscribirse a estos datos desde el centro de administración Microsoft 365 de administración

 **Código de error:** 422 
  
 **Donde verá este mensaje:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting API. 
  
 **Causa:** Antes de conectarte a la aplicación, tienes que suscribirte a los datos del centro Microsoft 365 administración. Si este paso no se realiza en primer lugar, no podrás conectarte a la aplicación de plantilla, incluso si proporcionas tu identificador Microsoft 365 inquilino. 
  
 **Para corregir este error:** Para suscribirse a los datos, vaya al Centro de administración Informes de uso y busque el icono Microsoft 365 análisis de uso en \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> la página del panel principal. Seleccione el **botón** Introducción y, a continuación, en el panel Informes que se abre, active la opción Hacer que los datos estén **disponibles** para Microsoft 365 análisis de uso para Power BI y **Guardar**. 
  
## <a name="we-are-processing-your-data"></a>Estamos procesando sus datos

 **Donde verá este mensaje:** En el **icono Microsoft 365 análisis de** uso en el panel De uso del Centro Microsoft 365 administración.  
  
 **Causa:** Cuando [optas por ver](enable-usage-analytics.md) datos en la aplicación de plantilla desde el centro de administración de Microsoft 365, el sistema Microsoft 365 empieza a generar datos de uso histórico para tu organización. Según el tamaño del espacio empresarial, puede que este paso tarde en completarse de 2 a 48 horas. 
  
 **Para corregir esto:** Solo tenga paciencia, pero si el mensaje no cambia a **Sus** datos está listo después de 3 días, póngase en contacto Microsoft 365 soporte técnico [para empresas](../../business-video/get-help-support.md).
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>No podemos procesar su solicitud en este momento. Aún estamos preparando los datos para su organización

 **Código de error:** 423 
  
 **Donde verá este mensaje:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting API. 
  
 **Causa:** Cuando [optas por ver](enable-usage-analytics.md) datos en la aplicación de plantilla desde el centro de administración, el sistema Microsoft 365 empieza a generar datos de uso histórico para tu organización. Según el tamaño del espacio empresarial, este paso podría tardar entre dos horas y 48 horas. 
  
 **Para corregir esto:** Solo tenga paciencia, pero si  el mensaje no cambia a Sus datos está listo incluso 3 días desde el inicio, póngase en contacto Microsoft 365 soporte técnico para [empresas](../../business-video/get-help-support.md).
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>El id. de espacio empresarial que especificó no tiene el formato correcto

 **Código de error:** 400 
  
 **Donde verá este mensaje:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting API. 
  
 **Causa:** El identificador de inquilino es un guid y debe tener el formato de xxxxxxxx-xxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. Si escribe cualquier otra cadena en el cuadro de entrada del espacio empresarial, recibirá este error. 
  
 **Para corregir este error:** Vaya al Centro de administración Informes de uso y busque el icono Microsoft 365 análisis de \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> uso en la página principal del panel. El identificador de inquilino aparece en el icono. Puedes copiarlo desde aquí y pegarlo en el cuadro de diálogo para conectarte a la aplicación de plantilla. 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>El sistema no reconoce el id. de espacio empresarial que especificó

 **Código de error:** 404 
  
 **Donde verá este mensaje:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting API. 
  
 **Causa:** El identificador de inquilino que proporcionó no es válido o no existe. 
  
 **Para corregir este error:** Vaya al Centro de administración Informes de uso y busque el icono Microsoft 365 análisis de \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> uso en la página principal del panel. El identificador de inquilino aparece en el icono. Puedes copiarlo desde aquí y pegarlo en el cuadro de diálogo para conectarte a la aplicación de plantilla. 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>Vuelva a escribir las credenciales para volver a iniciar sesión en Power BI

Código de error: 302
  
 **Donde verá este mensaje:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting API. 
  
 **Causa:** el código de autorización produjo errores y es posible que tenga que volver a escribir sus credenciales. 
  
 **Para solucionar este error:** cierre la sesión de Power BI y, después, vuelva a iniciarla. 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>No tiene la autorización correcta para obtener acceso estos datos. Para obtener acceso a los datos desde este servicio, necesita ser administrador global o uno de los administradores del producto

 **Código de error:** 403 
  
 **Donde verá este mensaje:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting API. 
  
 **Causa:** Error en el código de autorización porque el usuario que intentó conectarse a la aplicación de plantilla no tiene el nivel adecuado de autorización para acceder a estos datos. 
  
 **Para corregir este error:** Proporcione las credenciales de un usuario que sea un  administrador **global**, un administrador de **Exchange**, un administrador Skype Empresarial , un administrador **SharePoint,** un lector **global** o un lector de informes para conectarse a la aplicación de plantilla.  Consulta [Acerca de los roles de administrador](../add-users/about-admin-roles.md) para obtener más información. 
  
## <a name="refresh-failed"></a>No se pudo actualizar

 **Donde verá este mensaje:** correo electrónico de Power BI o estado de error en el historial de actualizaciones. 
  
 **Causa:** A veces, las credenciales del usuario que se ha conectado a la aplicación de plantilla se restablecen y no se actualizan en la configuración de conexión de la aplicación de plantilla, lo que hace que el usuario vea errores de actualización. 
  
 **Para corregir este error:** En Power BI, busque el conjunto de datos correspondiente a la aplicación  de plantilla Microsoft 365 Análisis de uso, seleccione Programar actualización y proporcione sus credenciales de administrador. 
  
Si eso no funciona, borra la caché y vuelve a crear la aplicación de plantilla.
  
  
