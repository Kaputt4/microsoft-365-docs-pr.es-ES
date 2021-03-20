---
title: Trabajar con los servicios de consultoría de Microsoft
description: preparación y pasos a seguir para trabajar con MCS para empaquetar las aplicaciones
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación, aplicaciones, MCS, empaquetado
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 04b0c7905c83be2afa46abcfb2d4bb5cd9735e06
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909231"
---
# <a name="working-with-microsoft-consulting-services"></a>Trabajar con los servicios de consultoría de Microsoft

Puedes interactuar con Microsoft Consulting Services (MCS) para empaquetar tus aplicaciones para usarlas con Microsoft Managed Desktop. Para obtener detalles exactos, trabaje con el representante de la cuenta para ponerse en contacto con MCS y ámbito de su proyecto de empaquetado de aplicaciones específico.

## <a name="roles-and-responsibilities"></a>Roles y responsabilidades

Para trabajar con el empaquetado de la aplicación MCS, **debes proporcionar estos elementos:**

- Los archivos del instalador de origen (por ejemplo, setup.exe o .msi).
- Las instrucciones de instalación, especificando detalles sobre cómo debe ser la instalación final. Por ejemplo, ¿debería haber un acceso directo de escritorio a la aplicación? ¿Cuál debe ser la visibilidad de la aplicación? ¿La aplicación debe conectarse a un servidor y, si es así, cuál? Para obtener más información, vea la [plantilla de solicitud de empaquetado de aplicaciones](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).
- Debes realizar tus propias pruebas de aceptación para comprobar que la aplicación funciona según lo necesites en tu entorno.

**MCS se ocupará de estas acciones:**

- Comprobar si la aplicación está prohibida o restringida en el entorno de Escritorio administrado de Microsoft.
- Pruebas de instalación, inicio y desinstalación de la aplicación para garantizar la compatibilidad con Windows 10. Si MCS detecta un problema de compatibilidad, la entregarán al programa [Desktop App Assure](/fasttrack/win-10-desktop-app-assure) para su corrección.
- Empaquetar la aplicación en la especificación y, a continuación, probar la implementación de aplicaciones mediante Microsoft Intune.

## <a name="app-delivery-schedule"></a>Programación de entrega de aplicaciones

Inicie el proceso de empaquetado cargando la información de la aplicación en el portal de Escritorio administrado de Microsoft. El equipo de empaquetado revisa los nuevos envíos cada jueves. Después de revisar y empaquetar, las aplicaciones empaquetadas se entregan el viernes siguiente. Se pueden empaquetar hasta cinco aplicaciones por semana para iniciarse, pero el servicio puede escalar para satisfacer sus necesidades.

![calendario que muestra la entrada de aplicaciones en un jueves (el día 21 en este ejemplo), validación de medios al día siguiente, empaquetado el lunes siguiente (día 25) y entrega de aplicaciones el viernes siguiente (el día 29)](../../media/MCS-cal.png)

Se te notificará una vez que se haya entregado la aplicación. En ese momento, tiene 21 días para realizar pruebas de aceptación y aprobar el trabajo en el portal de Escritorio administrado de Microsoft. Si descubre algún problema con la aplicación durante las pruebas de aceptación, rechace la aplicación en el portal de Escritorio administrado de Microsoft y se conectará por correo electrónico con un empaquetador de MCS para comprender y resolver el problema.

## <a name="testing-accounts-and-environment"></a>Probar cuentas y entorno

Para que el equipo de empaquetado complete la migración a Microsoft Intune, se recomienda proporcionar ciertos permisos:
 
-   Acceso a las funcionalidades de implementación de aplicaciones de Microsoft Intune para que el empaquetador agregue y asigne la aplicación 
-   Grupos de prueba, cuentas de usuario y licencias para que los empaquetadores puedan probar las aplicaciones

MCS usará esos permisos para realizar las siguientes acciones:
 
-   Asegurarse de que la aplicación funciona en una máquina virtual configurada para Microsoft Managed Desktop
-   Cargar la aplicación en Microsoft Intune para su implementación a los usuarios

Sin estos permisos, es posible que MCS avance, pero no podrán cargar las aplicaciones en el entorno.