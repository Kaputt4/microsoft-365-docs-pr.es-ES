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
description: Obtenga información sobre cómo empezar a recopilar datos para su inquilino mediante la aplicación de plantilla análisis de uso de Microsoft 365 en Power BI.
ms.openlocfilehash: d9cadcc8258478fd1d5dbc0d9ae6bf4e814a8435
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2021
ms.locfileid: "51957520"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Habilitar análisis de uso de Microsoft 365

El análisis de uso de Microsoft 365 aún no está disponible para la Comunidad gubernamental de Estados Unidos de Microsoft 365.
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>Pasos para habilitar el análisis de uso de Microsoft 365

Para empezar con el análisis de uso de Microsoft 365, primero debe hacer que los datos estén disponibles en el Centro de administración de Microsoft 365 y, a continuación, iniciar la aplicación de plantilla en Power BI.
  
### <a name="get-power-bi"></a>Obtener Power BI

Si aún no tiene Power BI, puede registrarse [en Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347). Seleccione **Probar gratis** para registrarse en una versión de prueba o Comprar **ahora** para obtener Power BI Pro.
  
  
También puede expandir la sección **Productos** para comprar una versión de Power BI. 

> [!NOTE]
> Necesita una licencia de Power BI Pro para instalar, personalizar y distribuir una aplicación de plantilla. Para obtener más información, consulte [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).

Para compartir los datos, tanto usted como las personas con las que comparte los datos, necesitan una licencia de Power BI Pro o el contenido debe estar en un área de trabajo en un servicio premium de [Power BI.](/power-bi/service-premium-what-is) 
  
### <a name="enable-the-template-app"></a>Habilitar la aplicación de plantilla

Para habilitar la aplicación de plantilla, debes ser administrador **global.**
  
Vea [acerca de los roles de administrador](../add-users/about-admin-roles.md) para obtener más información. 
  
1. En el Centro de administración, vaya a la pestaña **Configuración** de configuración de la organización \>  \> **Servicios.** 
    
2. En la **pestaña Servicios,** seleccione  **Informes**.
    
3. En el panel Informes que se abre, establezca Hacer que los datos de informe estén disponibles para análisis de uso de **Microsoft 365** para Power BI en **Al** \> **guardar**. 
  
El proceso de recopilación de datos se completará en dos o 48 horas según el tamaño del espacio empresarial. El **botón Ir a Power BI** se habilitará (ya no será gris) cuando se complete la recopilación de datos. 
    
### <a name="start-the-template-app"></a>Iniciar la aplicación de plantilla

Para iniciar la aplicación de plantilla, debe ser administrador **global,** lector de **informes,** administrador de **Exchange,** administrador de **Skype Empresarial** o administrador **de SharePoint.** 
  
1. Copie el identificador de inquilino y **seleccione Ir a Power BI**.
    
2.  Cuando llegue a Power BI, inicie sesión. A **continuación, selecciona Aplicaciones** Obtener -> **aplicaciones** en el menú de navegación.    
  
3. En la **pestaña Aplicaciones,** escriba Microsoft 365 en el cuadro de búsqueda y, a continuación, seleccione Análisis de uso de **Microsoft 365** \> **Obtenga ahora**.

    [![Seleccione Obtener ahora](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  Una vez instalada la aplicación. Seleccione el icono para abrirlo.

5.  Selecciona **Explorar aplicación** para ver la aplicación con datos de ejemplo. Elige **Conectar** para conectar la aplicación a los datos de tu organización.

6.  Elija **Conectar**, en la pantalla Conectarse a **Microsoft 365 usage analytics,** escriba el identificador de inquilino (sin guiones) que copió en el paso (1) y seleccione **Siguiente**.
    
7. En la siguiente pantalla, seleccione **OAuth2** como el **método de autenticación** \> **Iniciar sesión**. Si eliges cualquier otro método de autenticación, se producirá un error en la conexión a la aplicación de plantilla.
    
    ![Elegir cuenta de Microsoft como método de autenticación](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. Después de crear una instancia de la aplicación de plantilla, el panel de análisis de uso de Microsoft 365 estará disponible en Power BI en la web. La carga inicial del panel llevará entre 2 y 30 minutos.
  
Los agregados de nivel de inquilino estarán disponibles en todos los informes después de participar. **Los detalles de nivel de usuario solo estarán** disponibles alrededor del 5 del mes calendario siguiente después de participar en . Esto afectará a todos los informes de Actividad de usuario (consulte Navegar y usar los informes de análisis de uso de [Microsoft 365](navigate-and-utilize-reports.md) para obtener sugerencias sobre cómo ver y usar estos informes).
    
## <a name="make-the-collected-data-anonymous"></a>Establecer que los datos recopilados sean anónimos

Para establecer que los datos que se recopilen para todos los informes sean anónimos, debe ser administrador global. Esto ocultará información identificable como los nombres de usuario, grupo y sitio en informes y en la aplicación de plantilla.
  
1. En el Centro de administración, vaya a **Configuración** de la organización y, en la pestaña \> Servicios, elija  **Informes**.
    
2. Seleccione **Informes** y, a continuación, **elija Mostrar identificadores anónimos**. Esta configuración se aplica tanto a los informes de uso como a la aplicación de plantilla.
  
3. Seleccione **Guardar cambios**.
