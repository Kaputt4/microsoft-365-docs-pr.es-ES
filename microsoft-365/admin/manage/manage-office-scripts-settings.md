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
description: Obtenga información sobre cómo administrar la configuración Office scripts para los usuarios de su organización.
ms.openlocfilehash: e0cb52c4a8f48ff2310c83ffce61e08a0236ed59
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572314"
---
# <a name="manage-office-scripts-settings"></a>Administrar la configuración de los Scripts de Office

[Office Scripts permite](/office/dev/scripts)a los usuarios automatizar las tareas grabando, editando y ejecutando scripts en Excel en la web. Office Los scripts funcionan Power Automate y los usuarios ejecutan scripts en libros mediante el conector Excel Online (empresa). Microsoft 365 administradores pueden administrar la configuración Office scripts desde el centro Microsoft 365 administración.

## <a name="before-you-begin"></a>Antes de empezar

- Para administrar Office de scripts, debe ser un administrador global. Para obtener más información, vea [About admin roles](../add-users/about-admin-roles.md).

- Asegúrese de que los usuarios de su organización tienen una licencia válida para un plan Microsoft 365 o Office 365 comercial o EDU que incluya acceso Office aplicaciones de escritorio, como uno de los siguientes planes:

    - Microsoft 365 Empresa Estándar
    - Aplicaciones de Microsoft 365 para negocios
    - Aplicaciones de Microsoft 365 para empresas
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Administrar la disponibilidad de Office scripts y el uso compartido de scripts

1. En el centro Microsoft 365 administración, vaya a la **pestaña Servicios** Configuración configuración de \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank"></a> la organización.

2. Seleccione **Office scripts**.

3. Office Los scripts están activados de forma predeterminada y todos los usuarios de la organización pueden acceder y usar la característica y compartir scripts. Para desactivar Office scripts de la organización, desactive la casilla Permitir a los usuarios automatizar sus tareas **en Excel en la Web.**

4. Si ha desactivado anteriormente Office Scripts para su organización y desea volver **a** activarlo, seleccione Permitir que los usuarios automaticen sus tareas en Excel en la Web y, a continuación, especifique quién puede acceder y usar la característica:

    - Para permitir que todos los usuarios de la organización accedan y usen Office scripts, **deje** todos (el valor predeterminado) seleccionado.

    - Para permitir que solo los miembros de un grupo específico accedan y usen scripts de Office, seleccione Grupo específico y, a continuación, escriba el nombre o el alias de correo electrónico del grupo para agregarlo a la lista de permitidos. Puede agregar solo un grupo a la lista de permitidos y debe ser uno de los siguientes tipos:
        - Microsoft 365 grupo
        - Grupo de distribución
        - Grupo de seguridad
        - Grupo de seguridad habilitado para correo
    
        Para obtener más información sobre los diferentes tipos de grupos, vea [Comparar grupos](../create-groups/compare-groups.md).

5. Para permitir que los usuarios con acceso a scripts de Office compartan sus scripts con otros usuarios de la organización, seleccione Permitir que los usuarios con acceso **a Office Scripts** compartan sus scripts con otros usuarios de la organización . No se permite el uso compartido de scripts fuera de una organización.
 
    > [!NOTE]
    > Si más adelante desactiva el uso compartido de scripts para su organización, los usuarios podrán ejecutar scripts compartidos previamente.
 
6. Especifica qué usuarios con acceso a Office scripts pueden compartir sus scripts:
    
    - Para permitir que todos los usuarios con acceso a Office scripts compartan sus scripts, deje **todos** (el valor predeterminado) seleccionado.

    - Para permitir que solo los miembros de un grupo específico con acceso a scripts de Office compartan sus scripts, seleccione Grupo específico y, a continuación, escriba el nombre o el alias de correo electrónico del grupo para agregarlo a la lista de permitidos. Puede agregar solo un grupo a la lista de permitidos y debe ser uno de los siguientes tipos:
        - Microsoft 365 grupo
        - Grupo de distribución
        - Grupo de seguridad
        - Grupo de seguridad habilitado para correo
    
        Para obtener más información sobre los diferentes tipos de grupos, vea [Comparar grupos](../create-groups/compare-groups.md).

7. Para permitir que los usuarios ejecuten sus scripts Office dentro de los flujos de Power Automate, seleccione Permitir que los usuarios con acceso a Office Scripts ejecuten sus **scripts con Power Automate**. Esto permite a los usuarios agregar pasos de flujo con la opción ejecutar del conector Excel línea [(empresa).](/connectors/excelonlinebusiness) 

    - Para permitir que todos los usuarios con acceso a Office scripts usen sus scripts en flujos, **deje** todos (el valor predeterminado) seleccionado.

    - Para permitir que solo los miembros de un grupo específico con acceso a scripts de Office usen sus scripts en flujos, seleccione Grupo específico y, a continuación, escriba el nombre o el alias de correo electrónico del grupo para agregarlo a la lista de permitidos. Puede agregar solo un grupo a la lista de permitidos y debe ser uno de los siguientes tipos:
        - Microsoft 365 grupo
        - Grupo de distribución
        - Grupo de seguridad
        - Grupo de seguridad habilitado para correo

        Para obtener más información sobre los diferentes tipos de grupos, vea [Comparar grupos](../create-groups/compare-groups.md).

    - Para obtener más información sobre cómo usar Office scripts con Power Automate, vea [Ejecutar Office scripts con Power Automate](/office/dev/scripts/develop/power-automate-integration).

8. Seleccione **Guardar**.

    Los cambios realizados en la configuración de scripts Office pueden tardar hasta 48 horas en tener efecto.

## <a name="next-steps"></a>Pasos siguientes

Dado que Office Scripts funciona con Power Automate, se recomienda revisar las directivas de prevención de pérdida de datos (DLP) existentes para garantizar que los datos de la organización permanecen protegidos mientras los usuarios usan Office scripts. Para obtener más información, vea [Directivas de prevención de pérdida de datos (DLP).](/power-automate/prevent-data-loss)

## <a name="related-content"></a>Contenido relacionado

[Office documentación técnica de scripts (página](/office/dev/scripts/) de vínculos)\
[Introducción a Office scripts en Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artículo)\
[Compartir Office scripts en Excel para web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artículo)\
[Grabar, editar y crear scripts Office en Excel en la Web](/office/dev/scripts/tutorials/excel-tutorial) (artículo)
