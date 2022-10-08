---
title: Administrar la configuración de los Scripts de Office
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
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
search.appverid: MET150
description: Obtenga información sobre cómo administrar la configuración de scripts de Office para los usuarios de su organización.
ms.openlocfilehash: 9a26aeb3854971b35cebb18f785c1a0d6f174eea
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68178128"
---
# <a name="manage-office-scripts-settings"></a>Administrar la configuración de los Scripts de Office

[Los scripts de Office](/office/dev/scripts) permiten a los usuarios automatizar las tareas grabando, editando y ejecutando scripts en Excel en la Web. Los scripts de Office funcionan con Power Automate y los usuarios ejecutan scripts en libros mediante el conector de Excel Online (empresa). Los administradores de Microsoft 365 pueden administrar la configuración de scripts de Office desde la Centro de administración de Microsoft 365.

## <a name="before-you-begin"></a>Antes de empezar

- Para administrar la configuración de scripts de Office, debe ser un administrador global. Para obtener más información, consulte [Acerca de los roles de administrador](../add-users/about-admin-roles.md).

- Asegúrese de que los usuarios de su organización tienen una licencia válida para un plan de Microsoft 365 o Office 365 comercial o EDU que incluye acceso a aplicaciones de escritorio de Office, como uno de los siguientes planes:

- Microsoft 365 Empresa Estándar
- Aplicaciones de Microsoft 365 para negocios
- Aplicaciones de Microsoft 365 para empresas
- Office 365 E3
- Office 365 E5
- Office 365 A3
- Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Administrar la disponibilidad de scripts de Office y el uso compartido de scripts

1. En el Centro de administración de Microsoft 365, vaya a **[la pestaña](https://go.microsoft.com/fwlink/p/?linkid=2053743)** **Configuración** \> **Servicios de configuración de** \> la organización.

2. Seleccione **Scripts de Office**.

3. Los scripts de Office están activados de forma predeterminada y todos los usuarios de la organización pueden acceder y usar los scripts de características y recursos compartidos. Para desactivar los scripts de Office para su organización, desactive la casilla **Permitir a los usuarios automatizar sus tareas en Excel en la Web**.

4. Si anteriormente ha desactivado scripts de Office para su organización y desea volver a activarlo, seleccione **Permitir que los usuarios automaticen sus tareas en Excel en la Web** y, a continuación, especifique quién puede acceder a la característica y usarla:

    - Para permitir que todos los usuarios de su organización accedan a scripts de Office y los usen, deje **todos** (el valor predeterminado) seleccionado.

    - Para permitir que solo los miembros de un grupo específico accedan y usen scripts de Office, seleccione **Grupo específico** y, a continuación, escriba el nombre o el alias de correo electrónico del grupo para agregarlo a la lista de permitidos. Solo puede agregar un grupo a la lista de permitidos y debe ser uno de los siguientes tipos:
        - Grupo de Microsoft 365
        - Grupo de distribución
        - Grupo de seguridad
        - Grupo de seguridad habilitado para correo

        Para obtener más información sobre los diferentes tipos de grupos, consulte [Comparación de grupos](../create-groups/compare-groups.md).

5. Para permitir que los usuarios con acceso a scripts de Office compartan sus scripts con otros usuarios de la organización, seleccione **Permitir que los usuarios con acceso a scripts de Office compartan sus scripts con otros usuarios de la organización**. No se permite compartir scripts fuera de una organización.

    > [!NOTE]
    > Si más adelante desactiva el uso compartido de scripts para su organización, los usuarios podrán ejecutar scripts previamente compartidos.

6. Especifique qué usuarios con acceso a scripts de Office pueden compartir sus scripts:

    - Para permitir que todos los usuarios con acceso a scripts de Office compartan sus scripts, deje **todos** (el valor predeterminado) seleccionado.

    - Para permitir que solo los miembros de un grupo específico con acceso a scripts de Office compartan sus scripts, seleccione **Grupo específico** y escriba el nombre o el alias de correo electrónico del grupo para agregarlo a la lista de permitidos. Solo puede agregar un grupo a la lista de permitidos y debe ser uno de los siguientes tipos:
        - Grupo de Microsoft 365
        - Grupo de distribución
        - Grupo de seguridad
        - Grupo de seguridad habilitado para correo

        Para obtener más información sobre los diferentes tipos de grupos, consulte [Comparación de grupos](../create-groups/compare-groups.md).

7. Para permitir que los usuarios ejecuten sus scripts de Office dentro de flujos de Power Automate, seleccione **Permitir que los usuarios con acceso a scripts de Office ejecuten sus scripts con Power Automate**. Esto permite a los usuarios agregar pasos de flujo con la opción **Ejecutar script** [del conector de Excel Online (Empresa](/connectors/excelonlinebusiness)).

    - Para permitir que todos los usuarios con acceso a scripts de Office usen sus scripts en flujos, deje **todos** (el valor predeterminado) seleccionado.

    - Para permitir que solo los miembros de un grupo específico con acceso a scripts de Office usen sus scripts en flujos, seleccione **Grupo específico** y, a continuación, escriba el nombre o el alias de correo electrónico del grupo para agregarlo a la lista de permitidos. Solo puede agregar un grupo a la lista de permitidos y debe ser uno de los siguientes tipos:
        - Grupo de Microsoft 365
        - Grupo de distribución
        - Grupo de seguridad
        - Grupo de seguridad habilitado para correo

        Para obtener más información sobre los diferentes tipos de grupos, consulte [Comparación de grupos](../create-groups/compare-groups.md).

    - Para más información sobre el uso de scripts de Office con Power Automate, consulte [Ejecución de scripts de Office con Power Automate](/office/dev/scripts/develop/power-automate-integration).

8. Seleccione **Guardar**.

    Puede que los cambios en la configuración de Scripts de Office tarden hasta 48 horas en surtir efecto.

## <a name="next-steps"></a>Pasos siguientes

Dado que Los scripts de Office funcionan con Power Automate, se recomienda revisar las directivas de Prevención de pérdida de datos de Microsoft Purview (DLP) existentes para asegurarse de que los datos de la organización permanecen protegidos mientras los usuarios usan scripts de Office. Para obtener más información, consulte [Directivas de prevención de pérdida de datos (DLP)](/power-automate/prevent-data-loss).

## <a name="related-content"></a>Contenido relacionado

[Documentación técnica de Office Scripts](/office/dev/scripts/) (página de vínculos)\
[Introducción a los scripts de Office en Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artículo)\
[Uso compartido de scripts de Office en Excel para la Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artículo)\
[Registro, edición y creación de scripts de Office en Excel en la Web](/office/dev/scripts/tutorials/excel-tutorial) (artículo)
