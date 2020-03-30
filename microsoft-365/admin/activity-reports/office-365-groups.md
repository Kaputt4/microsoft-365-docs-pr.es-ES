---
title: Informes de Microsoft 365 en el centro de administración (grupos de Microsoft 365)
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: a27f1a99-3557-4f85-9560-a28e3d822a40
description: Obtenga un informe de grupos de Microsoft 365 para conocer los grupos y sus actividades.
ms.openlocfilehash: 23b72d960a693ddeb8b05d261bd90f180b7c731d
ms.sourcegitcommit: 2b626a7924b4be08f6eb21181453b778e6fde418
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2020
ms.locfileid: "43047136"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-groups"></a>Informes de Microsoft 365 en el centro de administración (grupos de Microsoft 365)

El panel de **informes** de Microsoft 365 muestra la información general de la actividad en todos los productos de la organización. Le permite explorar informes individuales de nivel de producto para proporcionarle información más pormenorizada sobre la actividad dentro de cada producto. Consulte [el tema de información general sobre los informes](activity-reports.md). En el informe de grupos de 365 de Microsoft, puede obtener información sobre la actividad de los grupos de su organización y ver cuántos grupos se crean y se usan.
  
> [!NOTE]
> Debe ser administrador global, lector global o lector de informes en Microsoft 365 o un administrador de Exchange, SharePoint, Teams, Team Communications o Skype empresarial para ver los informes.  
  
## <a name="how-to-get-to-the-groups-report"></a>Cómo obtener el informe de grupos

1. En el centro de administración de, vaya a **Informes** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">página</a> uso.

    
2. En la lista desplegable **seleccionar un informe** , seleccione **Office 365** \> **Groups Activity**.
  
## <a name="interpret-the-groups-report"></a>Interpretar el informe de grupos

Puede obtener una vista de la actividad de grupos consultando los gráficos **grupos**, **actividad**, **archivos**y **almacenamiento** . 
  
![Informes de Microsoft 365: actividades de grupos](../../media/852027a4-8eab-47d1-b770-2bb874bdc403.png)
  
|||
|:-----|:-----|
|1.  <br/> |El informe de **grupos de 365 de Microsoft** puede visualizarse para las tendencias de los últimos 7 días, 30 días, 90 días o 180 días. Sin embargo, si selecciona un día concreto en el informe, la tabla (7) mostrará los datos de hasta 28 días a partir de la fecha actual (no la fecha en que se generó el informe).  <br/> |
|2.  <br/> |Los datos de cada informe normalmente cubren hasta las últimas 24 a 48 horas.  <br/> |
|3.  <br/> |La vista **grupos** muestra un número total de grupos que existían en un día determinado y grupos activos en ese día en función de las conversaciones de correo electrónico, las publicaciones de Yammer y las actividades de archivo de SharePoint y las páginas de SharePoint vistas.  <br/> |
|4.  <br/> |La vista **Actividad** muestra el número de actividades de grupo a lo largo de las cargas de trabajo de grupo. Puede ver los mensajes de Exchange que recibieron los buzones de grupo en todos los grupos, en cualquier día durante el período de notificación. También puede ver los mensajes publicados, leídos y que le gustan los grupos de Yammer asociados a un grupo. <br/> |
|5.  <br/> |La vista **archivos** muestra el número de archivos totales y activos en todos los sitios de grupo asociados a un grupo.  <br/> |
|6.  <br/> |La vista **Almacenamiento** muestra el total de almacenamiento usado entre todos los buzones y sitios de grupo.  <br/> |
|7.  <br/> | En el gráfico **Grupos**, el eje Y es el número de grupos (que puede verse como totales o activos).  <br/>  En el gráfico **actividad** , el eje Y es el número de veces que se ha realizado una actividad en grupos.  <br/>  En el gráfico **Archivos**, el eje Y es el número de archivos totales o activos.  <br/>  En el gráfico **Almacenamiento**, el eje Y es el almacenamiento total usado por el sitio o buzón de grupo.  <br/>  En los tres gráficos, el eje X es el intervalo de fechas seleccionado para el informe específico.  <br/> |
|8.  <br/> |Puede filtrar la serie que ve en el gráfico seleccionando un elemento de la leyenda. Por ejemplo, en el gráfico **grupos** **, seleccione total o total** **activo** ![y número de grupos](../../media/8eebd496-5955-4419-8d53-5f3ba1ad1c88.png) activo para ver solo la información relacionada con cada uno de ellos. Si cambia esta selección, no cambiará la información en la tabla de cuadrícula.  <br/> |
|9.  <br/> | La lista de los grupos mostrados depende de la configuración de todos los grupos que existieron (y que no se eliminaron) a lo largo del plazo para la creación de informes más extenso (180 días). El recuento de actividades (conversaciones de correo electrónico, publicaciones de Yammer y actividades de archivos de SharePoint) variará según la selección de fecha.  <br/> Nota: es posible que no vea todos los elementos de la lista siguiente en las columnas hasta que los agregue.<br/>**Nombre del grupo** es el nombre del grupo.  <br/> **Eliminados** es el número de grupos eliminados. Si el grupo se elimina, pero tuvo actividad durante el período de presentación de informes, se mostrará en la cuadrícula con esta marca establecida en true.  <br/> **Propietario del grupo** es el nombre del propietario del grupo.  <br/> **Fecha de la última actividad** es la última fecha en la que el grupo recibió un mensaje. Es la última fecha en que hubo actividad en una conversación de correo electrónico, Yammer o el sitio.  <br/> **Tipo** es el tipo de grupo. Puede ser un grupo público o privado.  <br/> **Miembros** es el número de miembros del grupo.  <br/> **Miembros externos** es el número de usuarios externos en el grupo.  <br/> **Exchange** <br/> **Correos electrónicos recibidos** es el número de mensajes que ha recibido el grupo.  <br/> **Elementos totales del buzón** es el número total de elementos en el buzón del grupo.  <br/> **Almacenamiento de buzón usado** es el almacenamiento utilizado en el buzón del grupo.  <br/> **Archivos de SharePoint** <br/> **Total de archivos** es el número de archivos almacenados en los sitios del grupo de SharePoint.  <br/> **Archivos activos** es el número de archivos en el sitio del grupo de SharePoint (vistos o modificados, sincronizados, compartidos internamente o externamente) que se hayan comprendidos en el período de notificación.  <br/> **Almacenamiento usado (MB) del sitio** es la cantidad de almacenamiento en MB que se ha usado durante el período de notificación.  <br/> **Mensajes de Yammer** <br/> **Publicados** es el número de mensajes publicados en el grupo de Yammer durante el período de creación de informes.  <br/> **Leídos** es el número de conversaciones leídas en el grupo de Yammer durante el período de creación de informes.  <br/> **Lo que gusta** es el número de mensajes que han gustado en el grupo de Yammer durante el período de creación de informes.  <br/>  Si las directivas de la organización le impiden ver los informes en los que la información del usuario es identificable, puede cambiar la configuración de privacidad de todos estos informes. Consulte la sección **cómo ocultar los detalles del nivel de usuario** en los [informes de actividades del centro de administración de Microsoft 365](activity-reports.md).  <br/> |
|metros  <br/> |Seleccionar o pulsar **más acciones** botón ![más acciones OWA para](../../media/80044eef-2368-4c7e-8d31-7155b029e0cf.png) móviles más acciones junto a un encabezado de columna para agregar o quitar columnas del informe.  <br/> ![Informe de grupos: elegir columnas](../../media/d7fb95d6-2a2e-4144-b80d-581223e48043.png)|
|12  <br/> |También puede exportar los datos del informe a un archivo. csv de Excel; para ello, seleccione el vínculo **exportar** . Se exportarán los datos de todos los usuarios y podrá efectuar una ordenación y un filtrado sencillos para un análisis más detallado. Si tiene menos de 2000 usuarios, puede ordenar y filtrar en la tabla en el propio informe. Si tiene más de 2000 usuarios, para poder filtrar y ordenar, tendrá que exportar los datos.  <br/> |
|||
   

