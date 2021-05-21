---
title: Habilitar análisis de uso de Microsoft 365
f1.keywords:
- CSH
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
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Obtén información sobre cómo empezar a recopilar datos para el inquilino mediante la aplicación de plantilla Microsoft 365 de análisis de uso en Power BI.
ms.openlocfilehash: 329878365aa07da4615a849ad04cde7f75a07872
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593374"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Habilitar análisis de uso de Microsoft 365

Microsoft 365 análisis de uso aún no está disponible para Microsoft 365 us government Community.
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>Pasos para habilitar el análisis de uso de Microsoft 365

Para empezar con el Microsoft 365 de uso, primero debes hacer que los datos estén disponibles en el Centro de administración de Microsoft 365 e iniciar la aplicación de plantilla en Power BI.
  
### <a name="get-power-bi"></a>Obtener Power BI

Si aún no tiene Power BI, puede [registrarse](https://go.microsoft.com/fwlink/p/?linkid=845347)para obtener Power BI Pro . Selecciona **Probar gratis** para suscribirte a una prueba o Comprar **ahora** para obtener Power BI Pro.
  
  
También puede expandir la sección **Productos** para comprar una versión de Power BI. 

> [!NOTE]
> Necesitas una licencia Power BI Pro para instalar, personalizar y distribuir una aplicación de plantilla. Para obtener más información, consulte [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).

Para compartir los datos, tanto usted como las personas con las que comparte los datos, necesitan una licencia de Power BI Pro o el contenido debe estar en un área de trabajo en un servicio [Power BI premium](/power-bi/service-premium-what-is). 
  
### <a name="enable-the-template-app"></a>Habilitar la aplicación de plantilla

Para habilitar la aplicación de plantilla, debes ser administrador **global.**
  
Vea [acerca de los roles de administrador](../add-users/about-admin-roles.md) para obtener más información. 
  
1. En el Centro de administración, vaya a la **Configuración** configuración de la \>  \> **organización.** 
    
2. En la **pestaña Servicios,** seleccione  **Informes**.
    
3. En el panel Informes que se abre, establezca Hacer que los datos del informe estén **disponibles para** Microsoft 365 análisis de uso para Power BI en **Al** \> **guardar**. 
  
El proceso de recopilación de datos se completará en dos o 48 horas según el tamaño del espacio empresarial. El **botón Ir a Power BI** se habilitará (ya no es gris) cuando se complete la recopilación de datos. 
    
### <a name="start-the-template-app"></a>Iniciar la aplicación de plantilla

Para iniciar la aplicación de plantilla, debe ser un administrador **global,** un lector de **informes,** un **Exchange,** un Skype Empresarial **o** **un SharePoint.** 
  
1. Copie el identificador de inquilino y **seleccione Ir a Power BI**.
    
2.  Cuando llegue a Power BI, inicie sesión. A **continuación, selecciona Aplicaciones** Obtener -> **aplicaciones** en el menú de navegación.    
  
3. En la **pestaña** Aplicaciones, escriba Microsoft 365 en el cuadro de búsqueda y, a continuación, **seleccione Microsoft 365 análisis de** uso Obtener \> **ahora**.

    [![Seleccione Obtener ahora](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  Una vez instalada la aplicación. Seleccione el icono para abrirlo.

5.  Selecciona **Explorar aplicación** para ver la aplicación con datos de ejemplo. Elige **Conectar** para conectar la aplicación a los datos de tu organización.

6.  Elija **Conectar**, en la pantalla Conectar para Microsoft 365 análisis de uso, **escriba** el identificador de inquilino (sin guiones) que copió en el paso (1) y seleccione **Siguiente**.
    
7. En la siguiente pantalla, seleccione **OAuth2** como el **método de autenticación** \> **Iniciar sesión**. Si eliges cualquier otro método de autenticación, se producirá un error en la conexión a la aplicación de plantilla.
    
    ![Elegir cuenta de Microsoft como método de autenticación](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. Después de crear una instancia de la aplicación de plantilla, Microsoft 365 panel de análisis de uso estará disponible en Power BI en la web. La carga inicial del panel llevará entre 2 y 30 minutos.
  
Los agregados de nivel de inquilino estarán disponibles en todos los informes después de participar. **Los detalles de nivel de usuario solo estarán** disponibles alrededor del 5 del mes calendario siguiente después de participar en . Esto afectará a todos los informes en Actividad del usuario (consulte Navegar y usar los informes en análisis de uso de [Microsoft 365](navigate-and-utilize-reports.md) para obtener sugerencias sobre cómo ver y usar estos informes).
    
## <a name="make-the-collected-data-anonymous"></a>Establecer que los datos recopilados sean anónimos

Para establecer que los datos que se recopilen para todos los informes sean anónimos, debe ser administrador global. Esto ocultará información identificable como los nombres de usuario, grupo y sitio en informes y en la aplicación de plantilla.
  
1. En el Centro de  administración, vaya a la Configuración org Configuración y, en la pestaña \> Servicios, elija **Informes**. 
    
2. Seleccione **Informes** y, a continuación, **elija Mostrar identificadores anónimos**. Esta configuración se aplica tanto a los informes de uso como a la aplicación de plantilla.
  
3. Seleccione **Guardar cambios**.

## <a name="related-content"></a>Contenido relacionado

[Acerca del análisis de uso](usage-analytics.md) (artículo)

[Obtener la versión más reciente de análisis de uso](get-the-latest-version-of-usage-analytics.md) (artículo)

[Navegar y usar los informes de Microsoft 365 análisis de uso](navigate-and-utilize-reports.md) (artículo)