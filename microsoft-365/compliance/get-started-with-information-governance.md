---
title: Introducción al gobierno de la información en Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-compliance
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MOE150
- MET150
description: ¿Está listo para empezar a controlar los datos de su organización, pero no está seguro de por dónde empezar? Lea algunas instrucciones prescriptivas para empezar.
ms.openlocfilehash: 5b30dc870389c06bd006a056127439f1ec18ac65
ms.sourcegitcommit: 400ef9ac34247978e3de7ecc0b376c4abb6c99d8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2022
ms.locfileid: "62242183"
---
# <a name="get-started-with-information-governance"></a>Introducción al gobierno de la información

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

¿Preparado para empezar a controlar los datos de su organización, conservando el contenido que necesita mantener y eliminando el que ya no necesita? Use las siguientes instrucciones para comenzar:

1. **Comprenda cómo funcionan la retención y la eliminación** en Microsoft 365, y luego identifique las cargas de trabajo que necesitan una política de retención y si necesita crear etiquetas de retención para las excepciones: [Obtenga información sobre la retención](retention.md)
    
    > [!NOTE]
    > Si necesita la administración del ciclo de vida de los elementos de gran valor para los requisitos de mantenimiento de registros empresariales, legales o normativos: use etiquetas de retención con [administre de registros](records-management.md) en lugar de la gobernanza de la información.

2. **Crear directivas de retención** para las cargas de trabajo identificadas, especificando la configuración de retención y las acciones que requieren las directivas de su organización o normativas del sector: [Crear directivas de retención](create-retention-policies.md)
    
    Si es necesario, [crear y aplicar etiquetas de retención para las excepciones](create-retention-labels-information-governance.md).

3. **Archivo de buzones de correo** disponible para proporcionar a los usuarios espacio de almacenamiento adicional en el buzón: [Enable archive mailboxes en el centro de cumplimiento](enable-archive-mailboxes.md)
    
    Si es necesario para admitir buzones de archivo:
    
    - [Habilite el archivado de expansión automática](enable-autoexpanding-archiving.md) para buzones que necesitan más de 100 GB de almacenamiento.
    
    - Utilice [etiquetas de retención con una política de retención de la administración de registros de mensajería (MRM)](set-up-an-archive-and-deletion-policy-for-mailboxes.md) si necesita personalizar la forma en que los correos electrónicos se mueven automáticamente desde el buzón principal de un usuario a su buzón de archivo, o si necesita especificar la configuración de retención y eliminación para carpetas específicas en lugar de las buzón completo.

4. **Entender y administrar buzones inactivos** que conservan el contenido del buzón después de que los empleados abandonen la organización: [Conozca sobre los buzones inactivos](inactive-mailboxes-in-office-365.md)

5. Si tiene archivos PST que contienen datos que desea controlar:**importar archivos PST a buzones en línea** mediante la carga de red o el envío de unidades: [Consulte la importación de archivos PST de su organización](importing-pst-files-to-office-365.md)

Independientemente de estos pasos, **Use conectores para importar y archivar datos de terceros** que incluyan datos de plataformas de redes sociales, plataformas de mensajería instantánea y plataformas de colaboración de documentos. Cuando estos datos se importan a buzones en línea, no solo admite la gobernanza de la información desde Microsoft 365 Cumplimiento, sino también otras soluciones de cumplimiento, como el cumplimiento de comunicaciones, la administración de riesgos internos y la exhibición de documentos electrónicos. Para obtener más información, vea [Learn acerca de los conectores para datos de terceros](archiving-third-party-data.md).

## <a name="subscription-and-licensing-requirements"></a>Requisitos de suscripción y licencias

Varias suscripciones diferentes admiten funcionalidades de gobernanza de la información.

Para ver las opciones para que los usuarios puedan beneficiarse de las características de cumplimiento de Microsoft 365, consulte la [Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance). Para ver las características que se enumeran en esta página, consulte la sección [Información de gobernanza](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) y [PDF relacionados para descargar](https://go.microsoft.com/fwlink/?linkid=2139145) para conocer los requisitos de licencia de nivel de característica.

## <a name="permissions"></a>Permisos

Consulte la sección siguiente para obtener información sobre roles y grupos de roles para administrar la retención de Microsoft 365.

Para los permisos para administrar buzones de correo para archivado, buzones inactivos e importar, normalmente requieren permisos de Exchange, como el rol Destinatarios de correo. De forma predeterminada, este rol se asigna a los grupos de roles de administración de la organización y administración de destinatarios. Para conocer el requisito exacto de permisos para cada tarea de administración, consulte la documentación que acompaña a las instrucciones de administración.

### <a name="permissions-for-retention-policies-and-retention-labels"></a>Permisos para directivas de retención y etiquetas de retención

Los miembros del equipo de cumplimiento que crearán y administrarán directivas de retención y etiquetas de retención necesitan permisos para el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Centro de cumplimiento de Microsoft 365</a>. De forma predeterminada, el administrador de inquilinos (administrador global) tiene acceso a esta ubicación y puede conceder acceso a los responsables de cumplimiento y a otras personas sin concederles todos los permisos de un administrador de inquilinos. Para conceder permisos para esta administración limitada, se recomienda agregar usuarios al grupo de roles de **Administrador de compatibilidad**.

Como alternativa al uso de este rol predeterminado, puede crear un nuevo grupo de roles y agregar el rol **Administración de Retención** a este grupo. Para un rol de solo lectura, use **Administración de retención de solo vista**. 

Para obtener instrucciones sobre cómo agregar usuarios a los roles predeterminados o crear sus propios grupos de roles, consulte [Permisos en el Centro de cumplimiento de Microsoft 365](microsoft-365-compliance-center-permissions.md).

Estos permisos son necesarios solo para crear, configurar y aplicar etiquetas y directivas de retención. La persona que configura estas etiquetas y directivas no requiere acceso al contenido.

## <a name="common-scenarios"></a>Escenarios comunes

Use la tabla siguiente para ayudarle a asignar los requisitos empresariales a los escenarios más comunes para la gobernanza de la información.

|Quiero...|Documentación|
|----------------|---------------|
|Conserve o elimine datos de forma eficaz para los servicios de Microsoft 365: <br />- Exchange  <br />- SharePoint  <br />- OneDrive  <br />- Grupos de Microsoft 365 <br />- Teams <br />- Yammer <br />- Skype Empresarial |[Crear y configurar directivas de retención](create-retention-policies.md)|
|Proporcionar a los usuarios almacenamiento adicional en el buzón |[Habilitar los buzones de archivo en el centro de cumplimiento](enable-archive-mailboxes.md)|
|Retener el contenido del buzón después de que los empleados dejen la organización |[Crear y administrar buzones inactivos](create-and-manage-inactive-mailboxes.md)|
|Cargar datos de buzón de correo desde archivos PST |[Usar la carga en la red para importar archivos PST](use-network-upload-to-import-pst-files.md)|


Si tiene un escenario que requiere administración del ciclo de vida para elementos individuales, consulte los escenarios [common para la administración de registros](get-started-with-records-management.md#common-scenarios) 

## <a name="end-user-documentation"></a>Documentación para el usuario final

Consulte la sección siguiente para obtener información sobre la documentación del usuario final para admitir la retención de Microsoft 365.

Las funcionalidades de gobierno de la información que admiten la administración de buzones (archivado, buzones inactivos e importación) normalmente no requieren documentación del usuario final.

### <a name="end-user-documentation-for-retention-and-deletion"></a>Documentación del usuario final para la retención y eliminación

La mayoría de las directivas de retención funcionan de forma discreta en segundo plano y no requieren interacción del usuario. Por ello, los usuarios no necesitan apenas documentación. Las directivas de retención de Teams informan a los usuarios cuando se han eliminado sus mensajes con un vínculo a los mensajes de [Teams sobre las directivas de retención](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).

Sin embargo, si complementa las directivas de retención con etiquetas de retención, estas etiquetas tienen una presencia de interfaz de usuario en Microsoft 365 aplicaciones. Antes de implementar estas etiquetas en la red de producción, asegúrese de proporcionar información e instrucciones para los usuarios finales y el departamento de soporte técnico. Para ayudar a los usuarios a aplicar etiquetas de retención en SharePoint y OneDrive, vea [Aplicar etiquetas de retención a archivos en SharePoint o OneDrive](https://support.microsoft.com/office/apply-retention-labels-to-files-in-sharepoint-or-onedrive-11a6835b-ec9f-40db-8aca-6f5ef18132df).

La documentación más eficaz para los usuarios finales serán las instrucciones personalizadas que proporcione para los nombres de etiquetas de retención y para las configuraciones que elija. Consulte la siguiente página y descargas que puede usar para formar a los usuarios: [Aprendizaje para el usuario final sobre las etiquetas de retención](https://microsoft.github.io/ComplianceCxE/enduser/retention/).

