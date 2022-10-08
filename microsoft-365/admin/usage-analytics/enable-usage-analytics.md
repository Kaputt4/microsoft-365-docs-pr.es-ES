---
title: Habilitación del análisis de uso de Microsoft 365
f1.keywords:
- CSH
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Obtenga información sobre cómo empezar a recopilar datos para el inquilino mediante la aplicación de plantilla Análisis de uso de Microsoft 365 en Power BI.
ms.openlocfilehash: ff1bc0e30c2f9a79bbada94672315a14df6daae5
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68190185"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Habilitación del análisis de uso de Microsoft 365

Para habilitar el análisis de uso de Microsoft 365 en un inquilino de Microsoft 365 US Government Community Cloud (GCC), consulte [Conexión a los datos de Microsoft 365 Government Community Cloud (GCC) con Usage Analytics](connect-to-gcc-data-with-usage-analytics.md).

## <a name="before-you-begin"></a>Antes de empezar

Para empezar a trabajar con el análisis de uso de Microsoft 365, primero debe hacer que los datos estén disponibles en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a> y, a continuación, iniciar la aplicación de plantilla en Power BI.

## <a name="get-power-bi"></a>Obtener Power BI

Si aún no tiene Power BI, puede [registrarse para obtener Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347). Seleccione **Probar gratis** para registrarse para obtener una evaluación o **Comprar ahora** para obtener Power BI Pro.


También puede expandir la sección **Productos** para comprar una versión de Power BI.

> [!NOTE]
> Necesita una licencia de Power BI Pro para instalar, personalizar y distribuir una aplicación de plantilla. Para obtener más información, consulte [Requisitos previos](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).

Para compartir los datos, tanto usted como las personas con las que comparte los datos, necesitan una licencia de Power BI Pro o el contenido debe estar en un área de trabajo en un [servicio Power BI Premium](/power-bi/service-premium-what-is).

## <a name="enable-the-template-app"></a>Habilitación de la aplicación de plantilla

Para habilitar la aplicación de plantilla, debe ser un **Administrador global**.

Consulte [acerca de los roles de administrador](../add-users/about-admin-roles.md) para obtener más información.

1. En el centro de administración, vaya a la pestaña **Settings** \> Org settings **Services (Servicios** de **configuración de** \> la organización).

2. En la pestaña **Servicios** , seleccione  **Informes**.

3. En el panel Informes que se abre, establezca **Hacer que los datos del informe estén disponibles para análisis de uso de Microsoft 365 para Power BI** **en Al** \> **guardar**.

El proceso de recopilación de datos se completará en dos o 48 horas, dependiendo del tamaño del inquilino. El botón **Ir a Power BI** se habilitará (ya no estará gris) cuando se complete la recopilación de datos. Una vez hecho esto, la aplicación proporciona datos de uso históricos en el nivel de la organización. 

> [!NOTE]
> Los datos de la pestaña **"Actividad de usuario"** solo se actualizan después del decimoquinto día del mes actual y el primer día del mes siguiente, por lo que permanecerán vacíos inicialmente hasta que se complete la primera actualización.

## <a name="start-the-template-app"></a>Inicio de la aplicación de plantilla

Para iniciar la aplicación de plantilla, debe ser **administrador global**, **lector de informes**, **administrador de Exchange**, **administrador de Skype Empresarial** o **administrador de SharePoint**.

1. Copie el identificador de inquilino y seleccione **Ir a Power BI**.

2. Cuando llegue a Power BI, inicie sesión. A continuación, **seleccione Aplicaciones**->**Obtener aplicaciones** en el menú de navegación.

3. En la pestaña **Aplicaciones** , escriba Microsoft 365 en el cuadro de búsqueda y, a continuación, seleccione **Análisis** \> de uso de Microsoft 365 **Obtención ahora**.

    [![Seleccione Obtener ahora.](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)

4. Una vez instalada la aplicación. Seleccione el icono para abrirlo.

5. Seleccione **Explorar aplicación** para ver la aplicación con datos de ejemplo. Elija **Conectar** para conectar la aplicación a los datos de su organización.

6. Elija **Conectar**, en la pantalla **Conectarse a análisis de uso de Microsoft 365** , escriba el identificador de inquilino (sin guiones) que copió en el paso (1) y seleccione **Siguiente**.

7. En la siguiente pantalla, seleccione **OAuth2** como **método** \> de autenticación **Iniciar sesión**. Si elige cualquier otro método de autenticación, se producirá un error en la conexión a la aplicación de plantilla.

    ![Elija Cuenta microsoft como método de autenticación.](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)

8. Una vez creada la instancia de la aplicación de plantilla, el panel análisis de uso de Microsoft 365 estará disponible en Power BI en la web. La carga inicial del panel tardará entre 2 y 30 minutos.

Los agregados de nivel de inquilino estarán disponibles en todos los informes después de participar. **Los detalles de nivel de usuario solo estarán disponibles alrededor del 5 del próximo mes natural después de participar**. Esto afectará a todos los informes en Actividad del usuario (consulte [Navegación y uso de los informes en Análisis de uso de Microsoft 365](navigate-and-utilize-reports.md) para obtener sugerencias sobre cómo ver y usar estos informes).

## <a name="make-the-collected-data-anonymous"></a>Establecer que los datos recopilados sean anónimos

Los informes proporcionan información sobre los datos de uso de la organización. De forma predeterminada, los informes muestran información con nombres identificables para usuarios, grupos y sitios. A partir del 1 de septiembre de 2021, ocultamos información de usuario de forma predeterminada para todos los informes como parte de nuestro compromiso continuo de ayudar a las empresas a apoyar sus leyes de privacidad locales.
  
Los administradores globales pueden revertir este cambio para su inquilino y mostrar información de usuario identificable si las prácticas de privacidad de su organización lo permiten. Se puede lograr en el Centro de administración de Microsoft 365 siguiendo estos pasos:
  
1. En el Centro de administración, vaya a la página **Configuración** \> **Configuración de organización** \> **Servicios**.

2. Seleccione **Informes**. 
  
3. Desactive la instrucción **En todos los informes, mostrar nombres sin identificar para usuarios, grupos y sitios** y, a continuación, guarde los cambios.  
  
Estos cambios tardarán unos minutos en surtir efecto. Mostrar información de usuario identificable es un evento registrado en el registro de auditoría del portal de cumplimiento de Microsoft Purview.   

## <a name="related-content"></a>Contenido relacionado

[Acerca del análisis de uso](usage-analytics.md) (artículo)\
[Obtener la versión más reciente del análisis de uso](get-the-latest-version-of-usage-analytics.md) (artículo)\
[Navegar y usar los informes en análisis de uso de Microsoft 365](navigate-and-utilize-reports.md) (artículo)
