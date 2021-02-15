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
description: Obtenga información sobre cómo empezar a recopilar datos para su espacio empresarial mediante la aplicación de plantilla análisis de uso de Microsoft 365 en Power BI.
ms.openlocfilehash: 98ae107b6777ac97d0be3b37847117c6e20be63d
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114242"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Habilitar análisis de uso de Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

El análisis de uso de Microsoft 365 aún no está disponible para Microsoft 365 US Government Community.
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>Pasos para habilitar el análisis de uso de Microsoft 365

Para empezar con el análisis de uso de Microsoft 365, primero debe hacer que los datos estén disponibles en el Centro de administración de Microsoft 365 y, a continuación, iniciar la aplicación de plantilla en Power BI.
  
### <a name="get-power-bi"></a>Obtener Power BI

Si aún no tiene Power BI, puede registrarse [en Power BI Pro.](https://go.microsoft.com/fwlink/p/?linkid=845347) Selecciona **Probar gratis** para registrarte en una versión de prueba o Comprar **ahora** para obtener Power BI Pro.
  
  
También puede expandir la sección **Productos** para comprar una versión de Power BI. 

> [!NOTE]
> Necesita una licencia de Power BI Pro para instalar, personalizar y distribuir una aplicación de plantilla. Para obtener más información, consulte [Requisitos previos.](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)

Para compartir los datos, tanto usted como las personas con las que comparte los datos, necesitan una licencia de Power BI Pro o el contenido debe estar en un área de trabajo en un servicio [Power BI Premium.](https://docs.microsoft.com/power-bi/service-premium-what-is) 
  
### <a name="enable-the-template-app"></a>Habilitar la aplicación de plantilla

Para habilitar la aplicación de plantilla, debe ser administrador **global.**
  
Para [obtener más información, vea los roles](../add-users/about-admin-roles.md) de administrador. 
  
1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso. 
    
2. En la **página** Uso, busque la tarjeta de análisis de uso de **Microsoft 365** y seleccione **Introducción.**
    
3. En el panel Informes que se abre, establezca Hacer que los datos estén disponibles para el análisis de uso de **Microsoft 365** para Power BI en **Al** \> **guardar.** 
  
El proceso de recopilación de datos se completará en dos o 48 horas, dependiendo del tamaño del espacio empresarial. El **botón Ir a Power BI** se habilitará (ya no será gris) cuando se complete la recopilación de datos. 
    
### <a name="start-the-template-app"></a>Iniciar la aplicación de plantilla

Para iniciar la aplicación de plantilla, debe ser administrador **global,** lector de **informes,** administrador de **Exchange,** administrador de **Skype** Empresarial o administrador **de SharePoint.** 
  
1. Copie el id. de inquilino y seleccione **Ir a Power BI.**
    
2.  Cuando llegue a Power BI, inicie sesión. A **continuación, selecciona Aplicaciones** Obtener -> **aplicaciones** en el menú de navegación.    
  
3. En la **pestaña** Aplicaciones, escriba Microsoft 365 en el cuadro de búsqueda y, a continuación, seleccione Análisis de uso de **Microsoft 365** \> **Obtenerlo ahora.**

    [![Seleccione Obtener ahora](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  Una vez instalada la aplicación. Selecciona el icono para abrirlo.

5.  Selecciona **Explorar aplicación para** ver la aplicación con datos de ejemplo. Elija **Conectar** para conectar la aplicación a los datos de su organización.

6.  Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.
    
7. En la siguiente pantalla, seleccione **OAuth2** como el método **de autenticación** \> **Iniciar sesión.** Si eliges cualquier otro método de autenticación, se producirá un error en la conexión a la aplicación de plantilla.
    
    ![Elegir la cuenta Microsoft como método de autenticación](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. Después de crear una instancia de la aplicación de plantilla, el panel de análisis de uso de Microsoft 365 estará disponible en Power BI en la Web. La carga inicial del panel llevará entre 2 y 30 minutos.
  
Los agregados de nivel de inquilino estarán disponibles en todos los informes después de participar. **Los detalles de nivel de usuario solo estarán** disponibles el día 5 del próximo mes natural después de participar. Esto afectará a todos los informes de actividad de usuario (vea Navegar y usar los informes de análisis de uso de [Microsoft 365](navigate-and-utilize-reports.md) para obtener sugerencias sobre cómo ver y usar estos informes).
    
## <a name="make-the-collected-data-anonymous"></a>Establecer que los datos recopilados sean anónimos

Para establecer que los datos que se recopilen para todos los informes sean anónimos, debe ser administrador global. Esto ocultará información identificable como los nombres de usuario, grupo y sitio en informes y en la aplicación de plantilla.
  
1. En el centro de  administración, vaya a Configuración de la organización y, en la pestaña \> Servicios, elija **Informes.** 
    
2. Seleccione **Informes** y, a continuación, **elija Mostrar identificadores anónimos.** Esta configuración se aplica tanto a los informes de uso como a la aplicación de plantilla.
  
3. Seleccione **Guardar cambios**.
