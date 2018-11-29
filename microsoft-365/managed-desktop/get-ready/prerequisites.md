---
title: Requisitos previos del Escritorio administrado de Microsoft
description: ''
keywords: Servicio de escritorio administrado de Microsoft, Microsoft 365, documentación
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 11/1/2018
ms.openlocfilehash: a7e82c0f4301b00e3d9e923dca10d1630744b8c0
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871671"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Requisitos previos del Escritorio administrado de Microsoft

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

Éxito con Microsoft Managed Desktop comienza con requisitos Well-known, documentados y acordados para la infraestructura del cliente. En esta sección se describe los requisitos previos. 

Microsoft FastTrack está disponible para ayudar a los clientes cumplir estos requisitos y le ayudará a prepararse para participar en lugar de trabajo moderno como un servicio. Para obtener más información, vea [Microsoft FastTrack](https://fasttrack.microsoft.com/about). 

Área | Detalles de requisitos previos
--- | ---
Concesión de licencias | Se requiere una licencia de Microsoft 365 E5 o licencias equivalentes.<br><br>Esta licencia incluye E5 de Office 365, Windows 10 Enterprise E5 & Enterprise movilidad + E5 de seguridad (EMS). Para obtener más información, vea [Microsoft 365 licencias](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).
Conectividad |  Todos los dispositivos de escritorio administrado de Microsoft requieren conectividad a numerosas extremos de servicio de Microsoft desde la red interna de la organización, incluidos:<br>-Windows Update<br>-Almacenamiento de Microsoft para la empresa<br>-Azure Active Directory<br>: Informe de errores de Windows<br>-Análisis de bloqueos en línea<br>-Conectados Telemetry y experiencia del usuario<br>-App OneDrive para Windows 10<br><br>La lista completa de necesarios del IP y las direcciones URL pueden encontrarse en la [Configuración de Proxy](../get-ready/network.md). 
Azure Active Directory |    Azure Active Directory (AD Azure) debe ser el origen de autoridad para todas las cuentas de usuario, o se deben sincronizar las cuentas de usuario de Active Directory local con Azure AD conectar, versión 1.1.654.0 o posterior. Para obtener más información, vea [Azure Connect de AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).
Autenticación |    Si Azure AD no es el origen de autoridad para las cuentas de usuario, debe configurar uno de ellos en Azure conectar AD:<br>-Sincronización de Hash de contraseña (recomendada)<br>: Autenticación de paso a través de<br>-Federación con ADFS<br><br>Cuando también es necesario establecer las opciones de autenticación con reescritura de contraseña de conexión de Azure AD. Para obtener más información, vea [reescritura de contraseña](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).<br><br>Para obtener más información sobre las opciones de autenticación con Azure AD, vea [Opciones de inicio de sesión de usuario de Azure Connect de AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin).
Office 365 |    Es absolutamente recomendable que los siguientes servicios se migran a la nube:<br>-Correo electrónico: migrar a los buzones basados en la nube, Exchange online o configurarse con Exchange Online híbrida con Exchange 2013 o posterior, local.<br>-Los archivos y carpetas: migran a SharePoint Online y Office 365.<br>-Skype para la empresa – migrar a Skype para la empresa en línea.<br>-Administración de dispositivos - Microsoft Intune A solo en nube MDM solution (que no sean de híbrido) es necesario, lo que permite que los administradores de TI a administrar dispositivos de escritorio de Microsoft administrado con una consola web que se pueda acceder desde cualquier lugar en el mundo. Microsoft Intune es la solución MDM necesaria.<br><br>Para obtener más información, vea [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Datos de copia de seguridad y recuperación | Microsoft Managed Desktop requiere archivos para sincronizar con OneDrive para la empresa para protección. Todos los archivos no sincronizados con OneDrive para la empresa no están disponibles por Microsoft Desktop administrados y se pueden perder durante los intercambios del dispositivo o las llamadas de soporte técnico que requieren un restablecimiento de dispositivo. Microsoft Managed Desktop no es compatible con unidades de red asignadas.  

[Obtenga información sobre cómo cumplir los requisitos previos para la inscripción de escritorio administrado de Microsoft.](../get-ready/index.md)

Cuando esté listo para empezar a trabajar con escritorio administrado de Microsoft, póngase en contacto con su administrador de cuentas de Microsoft. 