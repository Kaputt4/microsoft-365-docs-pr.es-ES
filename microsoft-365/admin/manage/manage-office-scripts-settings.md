---
title: Administrar la configuración de scripts de Office
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
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
search.appverid: MET150
description: Obtenga información sobre cómo administrar la configuración de scripts de Office para los usuarios de su organización.
ms.openlocfilehash: 12a80f277f6d17a8e7f5228f6948e70b7a93be11
ms.sourcegitcommit: 97ef8f846939c3d31bb0638edf07bb89463ace0b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2020
ms.locfileid: "47300843"
---
# <a name="manage-office-scripts-settings"></a>Administrar la configuración de scripts de Office

Scripts de Office permite a los usuarios automatizar tareas mediante la grabación, la edición y la ejecución de scripts en Excel en la Web. Los scripts de Office funcionan con Power Automates y los usuarios ejecutan scripts en libros mediante el conector de Excel online (Business). Los administradores de Microsoft 365 pueden administrar la configuración de las secuencias de comandos de Office desde el centro de administración de Microsoft 365.

## <a name="before-you-begin"></a>Antes de empezar

- Para administrar la configuración de las secuencias de comandos de Office, debe ser un administrador global. Para obtener más información, vea [acerca de los roles de administrador](../add-users/about-admin-roles.md).

- Asegúrese de que los usuarios de la organización tengan una licencia válida para un plan comercial o EDU de Microsoft 365 u Office 365 que incluya acceso a las aplicaciones de escritorio de Office, como uno de los siguientes planes:

    - Microsoft 365 Empresa Estándar
    - Aplicaciones de Microsoft 365 para negocios
    - Aplicaciones de Microsoft 365 para empresas
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Administrar la disponibilidad de scripts de Office y el uso compartido de scripts

1. En el centro de administración de Microsoft 365, vaya a la pestaña **configuración** \> **org Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> .

2. Seleccione **scripts de Office**.

3. Los scripts de Office están activados de forma predeterminada y todos los usuarios de la organización pueden obtener acceso y usar la característica y compartir scripts. Para desactivar los scripts de Office para su organización, desactive la casilla de verificación **permitir que los usuarios automaticen sus tareas en Excel en la web** .

4. Si ha desactivado anteriormente scripts de Office para su organización y desea volver a activarlo, seleccione **permitir a los usuarios automatizar sus tareas en Excel en la web**y, a continuación, especifique quién puede tener acceso a la característica y usarla:

    - Para permitir que todos los usuarios de su organización puedan tener acceso y usar scripts de Office, deje seleccionada la opción **todos** (el valor predeterminado). 

    - Para permitir que solo los miembros de un grupo específico tengan acceso y usen scripts de Office, seleccione **grupo específico**y, a continuación, escriba el nombre o el alias de correo electrónico del grupo para agregarlo a la lista de permitidos. Solo puede Agregar un grupo a la lista de permitidos y debe ser de uno de los siguientes tipos:
        - Grupo 365 de Microsoft
        - Grupo de distribución
        - Grupo de seguridad
        - Grupo de seguridad habilitado para correo
    
        Para obtener más información acerca de los distintos tipos de grupos, vea [comparar grupos](../create-groups/compare-groups.md).

5. Para permitir que los usuarios con acceso a los scripts de Office compartan sus scripts con otras personas de la organización, seleccione **permitir a los usuarios tener acceso a los scripts de Office que comparten sus scripts con otros miembros de la organización**. No se permite compartir scripts fuera de una organización.
 
    > [!NOTE]
    > Si más tarde desactiva el uso compartido de scripts para su organización, los usuarios podrán seguir ejecutando scripts previamente compartidos.
 
6. Especifique qué usuarios con acceso a los scripts de Office pueden compartir sus scripts:
    
    - Para permitir que todos los usuarios con acceso a los scripts de Office compartan sus scripts, deje seleccionada la opción **todos** (el valor predeterminado).

    - Para permitir que solo los miembros de un grupo específico tengan acceso a los scripts de Office para compartir sus scripts, seleccione **grupo específico**y, a continuación, escriba el nombre o el alias de correo electrónico del grupo para agregarlo a la lista de permitidos. Solo puede Agregar un grupo a la lista de permitidos y debe ser de uno de los siguientes tipos:
        - Grupo 365 de Microsoft
        - Grupo de distribución
        - Grupo de seguridad
        - Grupo de seguridad habilitado para correo
    
        Para obtener más información acerca de los distintos tipos de grupos, vea [comparar grupos](../create-groups/compare-groups.md).

7. Haga clic en **Guardar**.

    Los cambios en la configuración de script de Office pueden tardar hasta 48 horas en aplicarse.

## <a name="next-steps"></a>Pasos siguientes

Como los scripts de Office funcionan con la automatización de la alimentación, le recomendamos que revise las directivas existentes de prevención de pérdida de datos (DLP) para asegurarse de que los datos de la organización sigan protegidos mientras los usuarios usan scripts de Office. Para obtener más información, consulte [directivas de prevención de pérdida de datos (DLP)](/power-automate/prevent-data-loss).

## <a name="related-content"></a>Contenido relacionado

[Documentación técnica de scripts de Office](/office/dev/scripts/) (página vínculo) \
[Introducción a los scripts de Office en Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artículo) \
[Uso compartido de scripts de Office en Excel para la web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artículo) \
[Registro, edición y creación de scripts de Office en Excel en la web](/office/dev/scripts/tutorials/excel-tutorial) (artículo)