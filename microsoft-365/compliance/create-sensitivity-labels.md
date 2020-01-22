---
title: Crear y administrar etiquetado de confidencialidad
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Instrucciones para crear, configurar y publicar etiquetas de confidencialidad para clasificar y proteger los documentos y correos electrónicos de su organización.
ms.openlocfilehash: 964fd20d6ada935d2a76ca0bffccc5bf46161c58
ms.sourcegitcommit: ce0651075aa7e3e1b189437f1990207dd10374b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2020
ms.locfileid: "41247463"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a>Crear y configurar etiquetas de confidencialidad y sus directivas

Para crear y publicar las [ etiquetas de confidencialidad ](sensitivity-labels.md), vaya al centro de administración de etiquetas, como la del [ Centro de cumplimiento de Microsoft 365 ](https://compliance.microsoft.com/). También puede usar el Centro de seguridad de Microsoft 365 o el Centro de seguridad y cumplimiento de Office 365.

En primer lugar, cree y configure las etiquetas de confidencialidad que quiera que estén disponibles en las aplicaciones de Office y para servicios. A continuación, cree una o varias directivas de etiqueta que contengan las etiquetas y las configuraciones de directiva que configure. La directiva de etiquetas se encarga de publicar las etiquetas y la configuración de los usuarios y las ubicaciones que elija.

## <a name="create-and-configure-sensitivity-labels"></a>Crear y configurar etiquetas de confidencialidad

1. En el centro de administración de etiquetas, desplácese hasta etiquetas de confidencialidad:
    
    - Centro de cumplimiento de Microsoft 365: 
        - **Soluciones** > **Protección de la información (versión preliminar)**
        
        Si no ve esta opción inmediatamente, primero seleccione **Mostrar todo**. 
    
    - Centro de seguridad de Microsoft 365: 
        - **Clasificación** > **Etiquetas de confidencialidad**
    
    - Centro de seguridad y cumplimiento de Office 365:
        - **Clasificación** > **Etiquetas de confidencialidad**

2. En la pestaña **Etiquetas**, seleccione **+Crear una etiqueta** para iniciar el asistente de ** Nueva etiqueta de confidencialidad**.

3. Siga los mensajes para la configuración de etiquetas.
    
    Para obtener más información acerca de la configuración de las etiquetas, consulte [Lo que pueden realizar las etiquetas de confidencialidad ](sensitivity-labels.md#what-sensitivity-labels-can-do) en la parte de información general.

4. Repita estos pasos para crear más etiquetas. Sin embargo, si desea crear una subetiqueta, seleccione la etiqueta principal primero y luego **...** para **Más acciones**y, a continuación, seleccione **Agregar subetiqueta**.

5. Cuando haya creado todas las etiquetas que necesita, revise el pedido y, si es necesario, muévalos hacia arriba o hacia abajo. Para cambiar el orden de una etiqueta, seleccione **...** para **Más acciones**y, a continuación, seleccione **Subir** o **Bajar**. Para obtener más información, consulte [Prioridad de etiquetas (el orden importa)](sensitivity-labels.md#label-priority-order-matters) en la parte de información general.

Para editar una etiqueta existente, selecciónela y, a continuación, seleccione **Editar etiqueta**. Se iniciará el asistente para **Editar etiquetas de confidencialidad**, lo que le permite cambiar todas las configuraciones de la etiqueta en el paso 3. 

> [!NOTE]
> Si edita una etiqueta ya publicada con una directiva de etiqueta, no necesita realizar pasos adicionales cuando finalice el asistente. Por ejemplo, no es necesario agregarla a una nueva Directiva de etiqueta. Sin embargo, sí debe dar un margen de 24 horas para que los cambios realizados se apliquen a los usuarios y servicios.

Hasta que publique las etiquetas, no estarán disponibles para seleccionarlas en aplicaciones o en servicios. Para publicar las etiquetas, deben agregarse a una directiva de etiqueta.

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a>Configuración adicional de etiquetas con PowerShell del Centro de seguridad y cumplimiento de Office 365

La configuración adicional de las etiquetas está disponible con el cmdlet de [ Set-Label ](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) desde [ PowerShell del Centro de seguridad y cumplimiento de Office 365 ](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).

Por ejemplo, utilice el parámetro *LocaleSettings* para especificar diferentes idiomas para los nombres de las etiquetas y la información sobre herramientas. 

Con este cmdlet, también puede especificar [ opciones avanzadas ](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) para el cliente de etiquetado unificado de Azure Information Protection. Estas opciones avanzadas incluyen establecer un color de etiqueta y aplicar una propiedad personalizada cuando se aplica una etiqueta. Para obtener la lista completa, consulte [ Configuración avanzada disponible para las directivas de etiqueta ](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies). 

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a>Publicar etiquetas de sensibilidad mediante la creación de una directiva de etiqueta

1. En el centro de administración de etiquetas, desplácese hasta etiquetas de confidencialidad:
    
    - Centro de cumplimiento de Microsoft 365: 
        - **Soluciones** > **Protección de la información (versión preliminar)**
        
        Si no ve esta opción inmediatamente, primero seleccione **Mostrar todo**. 
    
    - Centro de seguridad de Microsoft 365: 
        - **Clasificación** > **Etiquetas de confidencialidad**
    
    - Centro de seguridad y cumplimiento de Office 365:
        - **Clasificación** > **Etiquetas de confidencialidad**

2. Seleccione la pestaña ** Directiva de etiquetas **.

3. Seleccione ** Publicar etiquetas ** para iniciar el ** Asistente para crear directivas**.

4. Seleccione ** Elegir etiquetas de confidencialidad para publicar **. Seleccione las etiquetas que quiera que estén disponibles en aplicaciones y para servicios, a continuación, seleccione ** Agregar **.

5. Revise las etiquetas seleccionadas y para realizar cualquier cambio, seleccione ** Editar **. De lo contrario, seleccione **Siguiente**.

6. Siga las indicaciones para configurar las configuraciones de la directiva.
    
    Para obtener más información acerca de la configuración, consulte [Lo que pueden realizar las directivas de etiquetas ](sensitivity-labels.md#what-label-policies-can-do) en la parte de información general.

7. Repita estos pasos si necesita distintas configuraciones de directiva para diferentes usuarios o ubicaciones. Por ejemplo, puede que desee usar etiquetas adicionales para un grupo de usuarios, u otra etiqueta predeterminada para un subconjunto de usuarios.

8. Si crea más de una directiva de etiqueta que pueda resultar en conflicto para un usuario o una ubicación, revise el orden de las directivas y, si es necesario, muévalos hacia arriba o hacia abajo. Para cambiar el orden de una directiva de etiquetas, seleccione **...** para **Más acciones**y, a continuación, seleccione **Subir** o **Bajar**. Para obtener más información, consulte [Prioridad de las directivas de etiquetas (el orden importa)](sensitivity-labels.md#label-policy-priority-order-matters) en la parte de información general.

Al completar el asistente, se publica automáticamente la directiva de etiqueta. Para realizar cambios en una directiva publicada, solo tiene que editarla. No es necesario que seleccione una acción específica para publicar o volver a publicar.

Para editar una directiva de etiquetas existente, selecciónela y, a continuación, seleccione **Editar directiva **. Se iniciará el asistente para ** Crear directivas **, que le permite editar las etiquetas que se incluirán y su configuración. Cuando finalice el asistente, todos los cambios se aplicarán automáticamente a los usuarios y servicios seleccionados.

Normalmente, los usuarios pueden ver las etiquetas en las aplicaciones de Office en un par de horas. Sin embargo, dé un margen de hasta 24 horas para que las directivas de etiqueta y los cambios que se realicen en ellas se apliquen a todos los usuarios y servicios.

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a>Configuración adicional de las directivas de etiquetas con PowerShell del Centro de seguridad y cumplimiento de Office 365

La configuración adicional de las directivas de etiquetas está disponible con el cmdlet de [ Set-Label ](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) desde [ PowerShell del Centro de seguridad y cumplimiento de Office 365 ](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).

Con este cmdlet, puede especificar [ opciones avanzadas ](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) para el cliente de etiquetado unificado de Azure Information Protection. Entre estas opciones avanzadas, se incluye la configuración de una etiqueta predeterminada diferente para Outlook y la implementación de mensajes emergentes en Outlook que avisen, justifiquen o bloqueen los correos electrónicos que se envíen. Para obtener la lista completa, consulte [ Configuración avanzada disponible para las etiquetas ](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels). 

También puede usar este cmdlet para agregar o quitar etiquetas a una directiva de etiquetas, o hacerlo desde la misma.


## <a name="next-steps"></a>Pasos siguientes

Para configurar y usar las etiquetas de confidencialidad en escenarios específicos, use los artículos siguientes:

- [Restringir el acceso al contenido mediante el cifrado en las etiquetas de confidencialidad](encryption-sensitivity-labels.md)

- [Aplicar una etiqueta de confidencialidad automáticamente al contenido](apply-sensitivity-label-automatically.md)

- [Usar etiquetas de confidencialidad en equipos, grupos y sitios](sensitivity-labels-teams-groups-sites.md)

- [Habilitar etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md)

Para supervisar cómo se usan las etiquetas, consulte [Ver el uso de etiquetas con el análisis de etiquetas](label-analytics.md).