---
title: Configuración de Microsoft 365 Empresa Premium
description: Vea cómo configurar Microsoft 365 Empresa Premium
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/01/2022
ms.service: o365-administration
localization_priority: Normal
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 844dd03ae38eadaa86403b5ee7b2fc00a8840e17
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63319232"
---
# <a name="set-up-microsoft-365-business-premium"></a>Configuración de Microsoft 365 Empresa Premium

Tiene varias opciones para configurar y configurar Microsoft 365 Empresa Premium. Puede:

- [Usar una experiencia de configuración guiada para la configuración y configuración básicas](#guided-process-for-basic-setup)
- [Trabajar con un partner, como un Proveedor de soluciones en la nube de Microsoft (CSP)](#work-with-a-microsoft-partner)
- [Trabajar manualmente en el proceso de instalación](#manual-setup-and-configuration)


Use este artículo como guía.

## <a name="guided-process-for-basic-setup"></a>Proceso guiado para la configuración básica

Microsoft 365 Empresa Premium incluye un proceso guiado para la configuración básica. Las tareas incluyen conectarse a un dominio personalizado, agregar usuarios, asignar licencias, instalar Outlook en dispositivos móviles, revisar la configuración de protección de datos y aplicar una directiva de protección de aplicaciones móviles. 

Para ver cómo funciona la configuración guiada, vea el siguiente vídeo: <br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE471FJ?autoplay=false]

Una vez finalizada la configuración guiada, hay pasos adicionales que completar para garantizar que las capacidades de seguridad y cumplimiento se configuren y apliquen correctamente. Estos pasos incluyen:

- [Protección de Windows dispositivos](m365bp-secure-windows-devices.md)
- [Implementación de Microsoft 365 aplicaciones](../admin/setup/install-applications.md)
- [Configurar y configurar las nuevas funcionalidades de Defender para empresas](../security/defender-business/mdb-setup-configuration.md)

[Obtenga más información sobre las diferencias entre el proceso de configuración guiado y la página De instalación](../admin/setup/o365-setup-wizard-and-setup-page.md).

> [!TIP]
> Consulte la siguiente sección para obtener más información sobre cómo configurar y configurar Microsoft 365 Empresa Premium.


## <a name="work-with-a-microsoft-partner"></a>Trabajar con un partner de Microsoft

Microsoft tiene una lista de proveedores de soluciones que están autorizados a vender ofertas, incluidos Microsoft 365 Empresa Premium. 

Para encontrar un proveedor de soluciones en su área, siga estos pasos:

1. Vaya a la **página Proveedores de soluciones de Microsoft** ([https://www.microsoft.com/solution-providers](https://www.microsoft.com/solution-providers)).
 
2. En el cuadro de búsqueda, rellene la ubicación y el tamaño de la empresa. 

3. En el **cuadro Buscar productos, servicios, aptitudes, industrias** , ponga `Microsoft 365`y, a continuación, **seleccione Ir**.

4. Revise la lista de resultados. Seleccione un proveedor para obtener más información sobre su experiencia y los servicios que proporcionan.

Consulta también [Buscar a tu partner o revendedor](../admin/manage/find-your-partner-or-reseller.md).

## <a name="manual-setup-and-configuration"></a>Configuración y configuración manual

Si prefiere completar el proceso de configuración y configuración manualmente, use la siguiente tabla como guía:

| Fase  | Tarea  | Recursos para obtener más información  |
|---------|---------|---------|
| **Planeación**     | Planear el proceso de configuración y configuración  | [Planear la configuración de Microsoft 365 para empresas](../admin/setup/plan-your-setup.md)   |
|  | Revisar los requisitos | [Microsoft 365 Empresa Premium requisitos](https://www.microsoft.com/microsoft-365/business/microsoft-365-business-premium?activetab=pivot:overviewtab) |
| **Configuración básica**     | Usar un dominio personalizado como `rob@contoso.com` con Microsoft 365 | [Agregar un dominio a Microsoft 365](../admin/setup/add-domain.md) |
|      | Agregar usuarios y asignar licencias en Microsoft 365      | [Agregar usuarios y asignar licencias al mismo tiempo](../admin/add-users/add-users.md)        |
|  | Asigne roles de administrador a los usuarios que realizarán determinadas funciones, como: <br/>- Administración de características<br/>- Administración de cuentas de usuario<br/>- Administración de dispositivos<br/>- Visualización o administración de la información de seguridad y cumplimiento de la organización | [Más información sobre los roles de administrador](../admin/add-users/about-admin-roles.md) <br/><br/> [Asignar roles de administrador](../admin/add-users/assign-admin-roles.md)  |
|  | Instalar Aplicaciones Microsoft 365 (como Word, Excel, PowerPoint y más) | [Instalar aplicaciones de Office](../admin/setup/install-applications.md) |
| **Proteger la organización** | Consulte los 10 primeros días para proteger su Microsoft 365 suscripción |  [Principales 10 formas de proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md) |
|  | Requerir que todos usen un método de comprobación adicional cuando inicien sesión en Microsoft 365 | [Configurar la autenticación de varios factores](../admin/security-and-compliance/set-up-multi-factor-authentication.md) | 
| **Protección del correo electrónico y el contenido** |  Configurar la protección anti phishing avanzada para proteger contra ataques de suplantación de identidad malintencionados y otros ataques de suplantación de identidad | [Proteger el correo electrónico de ataques de suplantación de identidad](../admin/security-and-compliance/secure-your-business-data.md) |
|   | Configurar datos adjuntos Caja fuerte para proteger la organización de datos adjuntos de correo electrónico malintencionado | [Proteger contra datos adjuntos y archivos malintencionados con Caja fuerte adjuntos](../admin/security-and-compliance/secure-your-business-data.md) |
|  | Configurar vínculos Caja fuerte para proteger contra sitios web malintencionados (URL) en mensajes de correo electrónico y Office documentos | [Configurar vínculos Caja fuerte web](../admin/security-and-compliance/secure-your-business-data.md) |
|  | Configurar directivas de prevención de pérdida de datos para proteger la información confidencial de que no se comparta | [Configurar las características de cumplimiento](../admin/security-and-compliance/set-up-compliance.md) |
| **Administración y protección de dispositivos** | Proteger los dispositivos de Windows de la organización | [Dispositivos Windows seguros](m365bp-secure-windows-devices.md) <br/><br/>[Establecer o editar la configuración de protección de aplicaciones para Windows 10 dispositivos](../admin/devices/protection-settings-for-windows-10-devices.md) |
|   | Proteger Microsoft 365 aplicaciones en dispositivos móviles | [Establecer la configuración de protección de aplicaciones para dispositivos Android o iOS](../admin/devices/app-protection-settings-for-android-and-ios.md) |
|  | Configurar Microsoft Defender para empresas (cuando esté disponible para el inquilino) | [Información general sobre Microsoft Defender para empresas](../security/defender-business/mdb-overview.md)<br/><br/>[Usar el asistente para configurar Defender para empresas](../security/defender-business/mdb-use-wizard.md) |
| **Almacenamiento de archivos y migración de contenido** | Configurar el almacenamiento de archivos y cómo funcionará el uso compartido para su organización | [Configurar el almacenamiento y el uso compartido de archivos de Microsoft 365](../admin/setup/set-up-file-storage-and-sharing.md) |
| | Importar o migrar correo electrónico y contactos | [Migrar correo y contactos a Microsoft 365](../admin/setup/migrate-email-and-contacts-admin.md) |
|  | Mover los archivos de empresa a los que todos los usuarios deben tener acceso SharePoint (SharePoint suele reemplazar el uso de un recurso compartido de archivos o una unidad de red) | [Mover archivos a SharePoint](../admin/setup/files-to-sharepoint.md) |
|  | Mueva los archivos de trabajo existentes, como archivos de trabajo personales o archivos empresariales confidenciales, a OneDrive | [Mover archivos a OneDrive](../admin/setup/files-to-onedrive.md) |
| **Formación de los administradores y el equipo de seguridad** | Obtenga información sobre cómo usar el Centro de administración | [Información general del Centro de administración de Microsoft 365](../admin/admin-overview/admin-center-overview.md) |
|  | Usar la biblioteca de vídeos de aprendizaje gratuita para Microsoft 365 administradores | [Biblioteca de vídeos de aprendizaje de administración](../admin/admin-video-library.yml)  |
|  | Obtenga información sobre cómo usar el Microsoft 365 Defender web ([https://security.microsoft.com](https://security.microsoft.com)) | [Introducción al uso del portal Microsoft 365 Defender web](../security/defender-business/mdb-get-started.md) |

> [!TIP]
> ¿Necesita ayuda? Considere la posibilidad [de obtener ayuda empresarial para Microsoft 365](https://support.microsoft.com/en-us/office/business-assist-for-microsoft-365-37deb8fe-61cc-4cf9-9ad1-1c8d93475070)

## <a name="see-also"></a>Consulte también

- [Información general sobre Microsoft Defender para empresas](../security/defender-business/mdb-overview.md) (ahora incluida con Microsoft 365 Empresa Premium!)

- [Suscripciones de empresa y documentación de facturación](../commerce/index.yml)

- [Información general sobre Microsoft 365 Lighthouse](../lighthouse/m365-lighthouse-overview.md) (para MICROSOFT CSP)

- [Principales 10 formas de proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md)
