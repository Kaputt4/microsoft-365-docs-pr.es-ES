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
description: Obtenga información sobre cómo administrar Office configuración de scripts para usuarios de su organización.
ms.openlocfilehash: e0cb52c4a8f48ff2310c83ffce61e08a0236ed59
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572314"
---
# <a name="manage-office-scripts-settings"></a>Administrar la configuración de los Scripts de Office

[Office Scripts](/office/dev/scripts)permite a los usuarios automatizar tareas grabando, editando y ejecutando scripts en Excel en la web. Office Scripts funciona con Power Automate y los usuarios ejecutan scripts en libros de trabajo mediante el conector Excel online (business). Microsoft 365 administradores pueden administrar la configuración de scripts de Office desde el centro de administración de Microsoft 365.

## <a name="before-you-begin"></a>Antes de empezar

- Para administrar Office configuración de scripts, debe ser administrador global. Para obtener más información, consulte [Acerca de los roles de administrador.](../add-users/about-admin-roles.md)

- Asegúrese de que los usuarios de su organización tengan una licencia válida para un plan comercial o EDU Microsoft 365 o Office 365 que incluya acceso a aplicaciones de escritorio Office, como uno de los siguientes planes:

    - Microsoft 365 Empresa Estándar
    - Aplicaciones de Microsoft 365 para negocios
    - Aplicaciones de Microsoft 365 para empresas
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>Administrar la disponibilidad de scripts de Office y compartir scripts

1. En el Centro de administración de Microsoft 365, vaya a la pestaña Servicios de configuración **de Configuración** \> **org.** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank"></a>

2. Seleccione **Office Scripts**.

3. Office Los scripts están activados de forma predeterminada y todos los miembros de su organización pueden acceder y usar la característica y compartir scripts. Para desactivar Office scripts para su organización, desactive la casilla **Permitir que los usuarios automaticen sus tareas en Excel en la Web.**

4. Si previamente desactive Office Scripts para su organización y desea volver a activarlo, seleccione Permitir que **los usuarios automaticen sus tareas en Excel en la Web** y, a continuación, especifique quién puede acceder y usar la característica:

    - Para permitir que todos los usuarios de su organización tengan acceso y usen scripts Office, deje seleccionados **Todos** (el valor predeterminado).

    - Para permitir que solo los miembros de un grupo específico tengan acceso y utilicen scripts Office, seleccione **Grupo específico** y, a continuación, escriba el nombre o el alias de correo electrónico del grupo para agregarlo a la lista de permitidos. Puede agregar solo un grupo a la lista allow y debe ser uno de los siguientes tipos:
        - grupo Microsoft 365
        - Grupo de distribución
        - Grupo de seguridad
        - Grupo de seguridad habilitado para correo
    
        Para obtener más información sobre los diferentes tipos de grupos, consulte [Comparar grupos](../create-groups/compare-groups.md).

5. Para permitir que los usuarios con acceso a scripts de Office compartan sus scripts con otros usuarios de la organización, seleccione **Permitir que los usuarios con acceso a scripts Office compartan sus scripts con otros usuarios de la organización.** No se permite compartir scripts fuera de una organización.
 
    > [!NOTE]
    > Si posteriormente desactiva el uso compartido de scripts para su organización, los usuarios podrán ejecutar scripts compartidos anteriormente.
 
6. Especifique qué usuarios con acceso a Office Scripts pueden compartir sus scripts:
    
    - Para permitir que todos los usuarios con acceso a scripts de Office compartan sus scripts, **deje** todos (el valor predeterminado) seleccionados.

    - Para permitir que solo los miembros de un grupo específico con acceso a scripts de Office compartan sus scripts, seleccione **Grupo específico** y, a continuación, escriba el nombre o el alias de correo electrónico del grupo para agregarlo a la lista de permitidos. Puede agregar solo un grupo a la lista allow y debe ser uno de los siguientes tipos:
        - grupo Microsoft 365
        - Grupo de distribución
        - Grupo de seguridad
        - Grupo de seguridad habilitado para correo
    
        Para obtener más información sobre los diferentes tipos de grupos, consulte [Comparar grupos](../create-groups/compare-groups.md).

7. Para permitir a los usuarios ejecutar sus scripts de Office dentro de flujos de Power Automate, seleccione **Permitir a los usuarios con acceso a Office Scripts ejecutar sus scripts con Power Automate**. Esto permite a los usuarios agregar pasos de flujo con la opción **ejecutar script** [del conector en línea (empresarial) de Excel.](/connectors/excelonlinebusiness)

    - Para permitir que todos los usuarios con acceso a scripts Office utilicen sus scripts en flujos, **deje** todos (el valor predeterminado) seleccionados.

    - Para permitir que solo los miembros de un grupo específico con acceso a scripts de Office utilicen sus scripts en flujos, seleccione **Grupo específico** y, a continuación, escriba el nombre o el alias de correo electrónico del grupo para agregarlo a la lista de permitidos. Puede agregar solo un grupo a la lista allow y debe ser uno de los siguientes tipos:
        - grupo Microsoft 365
        - Grupo de distribución
        - Grupo de seguridad
        - Grupo de seguridad habilitado para correo

        Para obtener más información sobre los diferentes tipos de grupos, consulte [Comparar grupos](../create-groups/compare-groups.md).

    - Para obtener más información sobre el uso de scripts de Office con Power Automate, consulte [Ejecutar scripts de Office con Power Automate](/office/dev/scripts/develop/power-automate-integration).

8. Seleccione **Guardar**.

    Los cambios realizados en Office configuración de scripts pueden tardar hasta 48 horas en surtirse efecto.

## <a name="next-steps"></a>Pasos siguientes

Dado que Office scripts funciona con Power Automate, se recomienda revisar las directivas de prevención de pérdida de datos (DLP) existentes para asegurarse de que los datos de su organización permanecen protegidos mientras los usuarios usan scripts Office. Para obtener más información, consulte [Directivas de prevención de pérdida de datos (DLP).](/power-automate/prevent-data-loss)

## <a name="related-content"></a>Contenido relacionado

[Office Documentación técnica de scripts](/office/dev/scripts/) (página de enlace)\
[Introducción a Office Scripts en Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artículo)\
[Compartir scripts de Office en Excel para la Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artículo)\
[Grabar, editar y crear scripts Office en Excel en la Web](/office/dev/scripts/tutorials/excel-tutorial) (artículo)
