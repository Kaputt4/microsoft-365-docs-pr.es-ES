---
title: Habilitar análisis de uso de Microsoft 365
f1.keywords:
- CSH
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
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Obtenga información sobre cómo empezar a recopilar datos para su inquilino con la aplicación de plantilla de análisis de uso de Microsoft 365 en Power BI.
ms.openlocfilehash: cda5931e81f7ea13208825afa658f1c672a2f326
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071460"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Habilitar análisis de uso de Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

El análisis de uso de Microsoft 365 todavía no está disponible para la comunidad de Microsoft 365 US Government.
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>Pasos para habilitar el análisis de uso de Microsoft 365

Para empezar con los análisis de uso de Microsoft 365, primero debe hacer que los datos estén disponibles en el centro de administración de Microsoft 365 y, a continuación, iniciar la aplicación de plantilla en Power BI.
  
### <a name="get-power-bi"></a>Obtener Power BI

Si aún no tiene Power BI, puede [registrarse en Power Bi Pro](https://go.microsoft.com/fwlink/p/?linkid=845347). Seleccione **probar gratis** para suscribirse a una versión de prueba o **comprar ahora** para obtener Power Bi Pro.
  
  
También puede expandir la sección **Productos** para comprar una versión de Power BI. 

> [!NOTE]
> Necesita una licencia de Power BI Pro para instalar, personalizar y distribuir una aplicación de plantilla. Para obtener más información, vea [requisitos previos](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).

Para compartir sus datos, usted y las personas con las que comparte los datos necesitan una licencia de Power BI Pro o el contenido debe estar en un área de trabajo en un [servicio Premium de Power BI](https://docs.microsoft.com/power-bi/service-premium-what-is). 
  
### <a name="enable-the-template-app"></a>Habilitar la aplicación de plantilla

Para habilitar la aplicación de plantilla, debe ser **administrador global**.
  
Para obtener más información, vea acerca de los [roles de administrador](../add-users/about-admin-roles.md) . 
  
1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso. 
    
2. En la página **uso** , busque la tarjeta de **análisis de uso de Microsoft 365** y **Seleccione introducción**.
    
3. En el panel de informes que se abre, establezca hacer que los **datos estén disponibles para el análisis de uso de Microsoft 365 para Power BI** **en el** \> **almacenamiento**. 
  
El proceso de recopilación de datos se completará en dos a 48 horas, según el tamaño del espacio empresarial. El botón **ir a Power BI** estará habilitado (no estará en gris) cuando se complete la recopilación de datos. 
    
### <a name="start-the-template-app"></a>Iniciar la aplicación de plantilla

Para iniciar la aplicación de plantilla, debe ser **administrador global** , **lector de informes** , administrador de **Exchange** , **Administrador de Skype empresarial** o administrador de **SharePoint**. 
  
1. Copie el identificador de inquilino y seleccione **ir a Power BI**.
    
2.  Cuando llegue a Power BI, inicie sesión. A continuación, **Seleccione aplicaciones** -> **obtener aplicaciones** en el menú de navegación.    
  
3. En la pestaña **apps** , escriba Microsoft 365 en el cuadro de búsqueda y, a continuación, seleccione **Microsoft 365 Usage Analytics** \> **ahora**.

    [![Seleccionar obtener ahora](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  Una vez instalada la aplicación. Seleccione el icono para abrirlo.

5.  Seleccione **explorar aplicación** para ver la aplicación con los datos de ejemplo. Elija **conectar** para conectar la aplicación con los datos de la organización.

6.  Elija **conectar** , en la pantalla **conectar con el análisis de uso de Microsoft 365** , escriba el identificador de inquilino (sin guiones) que copió en el paso (1) y seleccione **siguiente**.
    
7. En la siguiente pantalla, seleccione **OAuth2** como el **método de autenticación** , \> **inicie sesión**. Si elige cualquier otro método de autenticación, se producirá un error en la conexión con la aplicación de plantilla.
    
    ![Elegir la cuenta Microsoft como método de autenticación](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. Una vez que se crea una instancia de la aplicación de plantilla, el panel de análisis de uso de Microsoft 365 estará disponible en Power BI en la Web. La carga inicial del panel tardará entre 2 y 30 minutos.
  
Los agregados a nivel de inquilino estarán disponibles en todos los informes después de optar por. **Los detalles en el nivel de usuario solo estarán disponibles alrededor del quinto del siguiente mes del calendario tras optar por**. Esto afectará a todos los informes de actividad de usuario (consulte [navegación y uso de los informes en Microsoft 365 Usage Analytics](navigate-and-utilize-reports.md) para obtener sugerencias sobre cómo ver y usar estos informes).
    
## <a name="make-the-collected-data-anonymous"></a>Establecer que los datos recopilados sean anónimos

Para establecer que los datos que se recopilen para todos los informes sean anónimos, debe ser administrador global. Esto ocultará la información identificable como nombres de usuario, grupo y sitio en los informes y en la aplicación de plantilla.
  
1. En el centro de administración, vaya a configuración **de la** \> **organización** y, en la ficha **servicios** , elija **informes**.
    
2. Seleccione **informes** y, a continuación, elija para **Mostrar identificadores anónimos**. Esta configuración se aplica tanto a los informes de uso como a la aplicación de plantilla.
  
3. Seleccione **Guardar cambios**.
