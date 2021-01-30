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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Obtenga información sobre cómo administrar la configuración de scripts de Office para los usuarios de su organización.
ms.openlocfilehash: 75d0a9d9e98652fc11eab7e8a7d6c826be031f6e
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058428"
---
# <a name="manage-office-scripts-settings"></a>Administrar la configuración de los Scripts de Office

Los scripts de Office permiten a los usuarios automatizar tareas grabando, editando y ejecutando scripts en Excel en la Web. Scripts de Office funciona con Power Automate y los usuarios ejecutan scripts en libros mediante el conector de Excel Online (Empresa). Los administradores de Microsoft 365 pueden administrar la configuración de scripts de Office desde el Centro de administración de Microsoft 365.

## <a name="before-you-begin"></a>Antes de empezar

- Para administrar la configuración de scripts de Office, debe ser administrador global. Para obtener más información, vea [Acerca de los roles de administrador.](../add-users/about-admin-roles.md)

- Asegúrese de que los usuarios de su organización tienen una licencia válida para un plan comercial o EDU de Microsoft 365 u Office 365 que incluya acceso a aplicaciones de escritorio de Office, como uno de los siguientes planes:

    - Microsoft 365 Empresa Estándar
    - Aplicaciones de Microsoft 365 para negocios
    - Aplicaciones de Microsoft 365 para empresas
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Administrar la disponibilidad de los scripts de Office y el uso compartido de scripts

1. En el Centro de administración de Microsoft 365, vaya a la **pestaña** Configuración de servicios de \> **configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">de la</a> organización.

2. Seleccione **Scripts de Office**.

3. Los scripts de Office están activados de forma predeterminada y todos los usuarios de su organización pueden tener acceso a la característica y usarla y compartir scripts. Para desactivar scripts de Office para su organización, desactive la casilla Permitir a los usuarios automatizar sus tareas **en Excel en la web.**

4. Si anteriormente desactivaba los scripts de Office para su organización y desea volver a activarlo, seleccione Permitir a los usuarios automatizar sus tareas en **Excel en la Web** y, a continuación, especifique quién puede tener acceso a la característica y usarla:

    - Para permitir que todos los usuarios de su organización accedan y usen scripts de Office, **deje** todos (el valor predeterminado) seleccionados.

    - Para permitir que solo los miembros de un grupo específico accedan y usen scripts de Office, seleccione Grupo específico y, a continuación, escriba el nombre o el alias de correo electrónico del grupo para agregarlo a la lista de permitidos. Puede agregar un solo grupo a la lista de permitidos y debe ser uno de los siguientes tipos:
        - Grupo de Microsoft 365
        - Grupo de distribución
        - Grupo de seguridad
        - Grupo de seguridad habilitado para correo
    
        Para obtener más información sobre los distintos tipos de grupos, vea [Comparar grupos.](../create-groups/compare-groups.md)

5. Para permitir que los usuarios con acceso a scripts de Office compartan sus scripts con otros usuarios de su organización, seleccione Permitir que los usuarios con acceso a scripts de Office compartan sus scripts con otros usuarios de **la organización.** No se permite el uso compartido de scripts fuera de una organización.
 
    > [!NOTE]
    > Si más adelante desactiva el uso compartido de scripts para su organización, los usuarios seguirán siendo capaces de ejecutar scripts compartidos anteriormente.
 
6. Especifique qué usuarios con acceso a scripts de Office pueden compartir sus scripts:
    
    - Para permitir que todos los usuarios con acceso a scripts de Office compartan sus scripts, **deje** todos (el valor predeterminado) seleccionados.

    - Para permitir que solo los miembros de un grupo específico con acceso a scripts de Office compartan sus scripts, seleccione Grupo específico y, a continuación, escriba el nombre o el alias de correo electrónico del grupo para agregarlo a la lista de permitidos. Puede agregar un solo grupo a la lista de permitidos y debe ser uno de los siguientes tipos:
        - Grupo de Microsoft 365
        - Grupo de distribución
        - Grupo de seguridad
        - Grupo de seguridad habilitado para correo
    
        Para obtener más información sobre los distintos tipos de grupos, vea [Comparar grupos.](../create-groups/compare-groups.md)

7. Para permitir que los usuarios ejecuten sus scripts de Office dentro de los flujos de Power Automate, seleccione Permitir que los usuarios con acceso a scripts de Office ejecuten sus **scripts con Power Automate.** Esto permite a los usuarios agregar pasos de flujo con la opción de **script** Ejecutar del conector de [Excel Online (Empresa).](/connectors/excelonlinebusiness)

    - Para permitir que todos los usuarios con acceso a scripts de Office usen sus scripts en flujos, **deje** todos (el valor predeterminado) seleccionados.

    - Para permitir que solo los miembros de un grupo específico con acceso a scripts de Office usen sus scripts en flujos, seleccione Grupo específico y, a continuación, escriba el nombre o el alias de correo electrónico del grupo para agregarlo a la lista de permitidos. Puede agregar un solo grupo a la lista de permitidos y debe ser uno de los siguientes tipos:
        - Grupo de Microsoft 365
        - Grupo de distribución
        - Grupo de seguridad
        - Grupo de seguridad habilitado para correo

        Para obtener más información sobre los distintos tipos de grupos, vea [Comparar grupos.](../create-groups/compare-groups.md)

    - Para obtener más información sobre el uso de scripts de Office con Power Automate, incluido cómo se pueden ver afectadas las directivas de prevención de pérdida de datos, vea Ejecutar scripts de [Office con Power Automate.](/office/dev/scripts/develop/power-automate-integration)

8. Seleccione **Guardar**.

    Los cambios en la configuración de scripts de Office pueden tardar hasta 48 horas en tener efecto.

## <a name="next-steps"></a>Pasos siguientes

Dado que los scripts de Office funcionan con Power Automate, le recomendamos que revise las directivas de prevención de pérdida de datos (DLP) existentes para asegurarse de que los datos de su organización permanecen protegidos mientras los usuarios usan scripts de Office. Para obtener más información, vea directivas de prevención de pérdida de [datos (DLP).](/power-automate/prevent-data-loss)

## <a name="related-content"></a>Contenido relacionado

[Documentación técnica de scripts de Office](/office/dev/scripts/) (página de vínculos)\
[Introducción a los scripts de Office en Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artículo)\
[Uso compartido de scripts de Office en Excel para la Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artículo)\
[Registro, edición y creación de scripts de Office en Excel en la Web](/office/dev/scripts/tutorials/excel-tutorial) (artículo)
