---
title: Trabajar con los Servicios de Consultoría de Microsoft
description: preparación y pasos a seguir para trabajar con MCS para empaquetar las aplicaciones
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentation, apps, MCS, Packaging
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 4491504616eb4bb447f12d08dddb12c73c2a88ac
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962627"
---
# <a name="working-with-microsoft-consulting-services"></a>Trabajar con los Servicios de Consultoría de Microsoft

Puede participar con los servicios de consultoría de Microsoft (MCS) para empaquetar las aplicaciones para usarlas con el escritorio administrado de Microsoft. Para obtener detalles exactos, trabaje con su representante de cuenta para ponerse en contacto con MCS y alcance su proyecto de empaquetado de aplicaciones específico.

## <a name="roles-and-responsibilities"></a>Roles y responsabilidades

Para trabajar con el empaquetado de la aplicación de MCS, **debe proporcionar estos elementos**:

- Los archivos del instalador de origen (por ejemplo, setup. exe o. msi).
- Las instrucciones de instalación, que especifican los detalles sobre el aspecto de la instalación final. Por ejemplo, ¿debería haber un acceso directo de escritorio a la aplicación? ¿Qué debería tener la visibilidad de la aplicación? ¿La aplicación debe conectarse a un servidor y, si es así, ¿cuál? Para obtener más información, consulte la [plantilla solicitud de empaquetado de aplicaciones](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).
- Debe realizar sus propias pruebas de aceptación para comprobar que la aplicación funciona según la necesite en su entorno.

**MCS se ocupará de estas acciones:**

- Comprobar si la aplicación está prohibida o restringida en el entorno de escritorio administrado por Microsoft.
- Probar la instalación, iniciar y desinstalar la aplicación para garantizar la compatibilidad con Windows 10. Si MCS detecta un problema de compatibilidad, entregará la aplicación al programa de [aseguramiento](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) de la aplicación de escritorio para la corrección.
- Empaquete la aplicación en la especificación y, a continuación, pruebe la implementación de aplicaciones con Microsoft Intune.

## <a name="app-delivery-schedule"></a>Programación de entrega de aplicaciones

Inicie el proceso de empaquetado cargando la información de la aplicación en el portal de escritorio administrado de Microsoft. El equipo de empaquetado revisa los nuevos envíos cada jueves. Después de la revisión y el empaquetado, las aplicaciones empaquetadas se entregan el viernes siguiente. Se pueden empaquetar hasta cinco aplicaciones por semana para comenzar, pero el servicio se puede escalar para satisfacer sus necesidades.

![calendario que muestra la entrada de la aplicación en un jueves (el 21 de este ejemplo), validación de medios al día siguiente, empaquetado el lunes siguiente (el 25) y entrega de la aplicación en el viernes posterior (el 29)](images/MCS-cal.png)

Recibirá una notificación una vez que se haya entregado la aplicación. En ese momento, dispone de 21 días para realizar las pruebas de aceptación y cerrar la sesión en el trabajo en el portal de escritorio administrado de Microsoft. Si detecta algún problema con la aplicación durante las pruebas de aceptación, rechace la aplicación en el portal de escritorio administrado de Microsoft y se conectará a través del correo electrónico con un empaquetador de MCS para comprender y resolver el problema.

## <a name="testing-accounts-and-environment"></a>Pruebas de entorno y cuentas

Para que el equipo de empaquetado complete la migración a Microsoft Intune, le recomendamos que proporcione determinados permisos:
 
-   Acceso a las funcionalidades de implementación de aplicaciones de Microsoft Intune para que el empaquetador agregue y asigne la aplicación 
-   Grupos de prueba, cuentas de usuario y licencias de los paquetes para poder probar las aplicaciones

MCS usará esos permisos para realizar las siguientes acciones:
 
-   Asegurarse de que la aplicación funciona en una máquina virtual configurada para el escritorio administrado de Microsoft
-   Carga de la aplicación en Microsoft Intune para su implementación a los usuarios

Sin estos permisos, es posible que MCS se mueva hacia delante, pero no podrá cargar las aplicaciones en su entorno.


