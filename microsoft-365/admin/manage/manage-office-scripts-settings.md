---
title: Administrar la configuración de los Scripts de Office
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid: MET150
description: Obtenga información sobre cómo administrar la configuración de scripts de Office para los usuarios de su organización.
ms.openlocfilehash: fdc9c947ee7f12e284fd215f05f8b5c3dcb127eb
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64941157"
---
# <a name="manage-office-scripts-settings"></a>Administrar la configuración de los Scripts de Office

[Office Scripts](/office/dev/scripts) permite a los usuarios automatizar tareas grabando, editando y ejecutando scripts en Excel en la Web. Office Scripts funciona con Power Automate y los usuarios ejecutan scripts en libros mediante el conector Excel Online (Empresa). Microsoft 365 los administradores pueden administrar la configuración de scripts de Office desde el Centro de administración de Microsoft 365.

## <a name="before-you-begin"></a>Antes de empezar

- Para administrar Office configuración de scripts, debe ser administrador global. Para obtener más información, consulte [Acerca de los roles de administrador](../add-users/about-admin-roles.md).

- Asegúrese de que los usuarios de su organización tienen una licencia válida para un plan Microsoft 365 o Office 365 comercial o EDU que incluye acceso a Office aplicaciones de escritorio, como uno de los siguientes planes:

- Microsoft 365 Empresa Estándar
- Aplicaciones de Microsoft 365 para negocios
- Aplicaciones de Microsoft 365 para empresas
- Office 365 E3
- Office 365 E5
- Office 365 A3
- Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Administración de la disponibilidad de scripts de Office y uso compartido de scripts

1. En el Centro de administración de Microsoft 365, vaya a la pestaña **[Servicios](https://go.microsoft.com/fwlink/p/?linkid=2053743)** de **configuración** \> de **Configuración** \> Organización.

2. Seleccione **scripts de Office**.

3. Office Scripts está activado de forma predeterminada y todos los usuarios de la organización pueden acceder a los scripts de características y compartir y usarlos. Para desactivar Office scripts para su organización, desactive la casilla **Permitir a los usuarios automatizar sus tareas en Excel en la Web**.

4. Si anteriormente ha desactivado Office scripts para su organización y desea volver a activarlo, seleccione **Permitir que los usuarios automaticen sus tareas en Excel en la Web** y, a continuación, especifique quién puede acceder a la característica y usarla:

    - Para permitir que todos los usuarios de su organización accedan a scripts de Office y los usen, deje **seleccionado Todos** (el valor predeterminado).

    - Para permitir que solo los miembros de un grupo específico accedan a scripts de Office y los usen, seleccione **Grupo específico** y escriba el nombre o el alias de correo electrónico del grupo para agregarlo a la lista de permitidos. Solo puede agregar un grupo a la lista de permitidos y debe ser uno de los siguientes tipos:
        - grupo de Microsoft 365
        - Grupo de distribución
        - Grupo de seguridad
        - Grupo de seguridad habilitado para correo

        Para obtener más información sobre los diferentes tipos de grupos, consulte [Comparación de grupos](../create-groups/compare-groups.md).

5. Para permitir que los usuarios con acceso a scripts de Office compartan sus scripts con otros usuarios de la organización, seleccione **Permitir que los usuarios con acceso a Office Scripts compartan sus scripts con otros usuarios de la organización**. No se permite compartir scripts fuera de una organización.

    > [!NOTE]
    > Si más adelante desactiva el uso compartido de scripts para su organización, los usuarios podrán ejecutar scripts previamente compartidos.

6. Especifique qué usuarios con acceso a Office Scripts pueden compartir sus scripts:

    - Para permitir que todos los usuarios con acceso a Office scripts compartan sus scripts, deje **todos** (el valor predeterminado) seleccionado.

    - Para permitir que solo los miembros de un grupo específico con acceso a Office Scripts compartan sus scripts, seleccione **Grupo específico** y, a continuación, escriba el nombre o el alias de correo electrónico del grupo para agregarlo a la lista de permitidos. Solo puede agregar un grupo a la lista de permitidos y debe ser uno de los siguientes tipos:
        - grupo de Microsoft 365
        - Grupo de distribución
        - Grupo de seguridad
        - Grupo de seguridad habilitado para correo

        Para obtener más información sobre los diferentes tipos de grupos, consulte [Comparación de grupos](../create-groups/compare-groups.md).

7. Para permitir que los usuarios ejecuten sus scripts de Office dentro de flujos de Power Automate, seleccione **Permitir que los usuarios con acceso a Office Scripts ejecuten sus scripts con Power Automate**. Esto permite a los usuarios agregar pasos de flujo con la opción **Ejecutar script** [de Excel Online (Business) Connector](/connectors/excelonlinebusiness).

    - Para permitir que todos los usuarios con acceso a Office scripts usen sus scripts en flujos, deje **todos (** el valor predeterminado) seleccionado.

    - Para permitir que solo los miembros de un grupo específico con acceso a scripts de Office usen sus scripts en flujos, seleccione **Grupo específico** y, a continuación, escriba el nombre o el alias de correo electrónico del grupo para agregarlo a la lista de permitidos. Solo puede agregar un grupo a la lista de permitidos y debe ser uno de los siguientes tipos:
        - grupo de Microsoft 365
        - Grupo de distribución
        - Grupo de seguridad
        - Grupo de seguridad habilitado para correo

        Para obtener más información sobre los diferentes tipos de grupos, consulte [Comparación de grupos](../create-groups/compare-groups.md).

    - Para más información sobre el uso de scripts de Office con Power Automate, consulte [Ejecución de scripts Office con Power Automate](/office/dev/scripts/develop/power-automate-integration).

8. Seleccione **Guardar**.

    Puede que los cambios en la configuración de Scripts de Office tarden hasta 48 horas en surtir efecto.

## <a name="next-steps"></a>Siguientes pasos

Dado que Office Scripts funciona con Power Automate, se recomienda revisar las directivas existentes de Prevención de pérdida de datos (DLP) de Microsoft Purview para asegurarse de que los datos de la organización permanecen protegidos mientras los usuarios usan scripts de Office. Para obtener más información, consulte [Directivas de prevención de pérdida de datos (DLP)](/power-automate/prevent-data-loss).

## <a name="related-content"></a>Contenido relacionado

[documentación técnica de Office Scripts](/office/dev/scripts/) (página de vínculo)\
[Introducción a los scripts de Office en Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artículo)\
[Uso compartido de scripts de Office en Excel para web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artículo)\
[Grabar, editar y crear scripts de Office en Excel en la Web](/office/dev/scripts/tutorials/excel-tutorial) (artículo)
