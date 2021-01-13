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
ms.openlocfilehash: f8c4e427c536577ea2fc768d4930b9d4db6ac697
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841428"
---
# <a name="working-with-microsoft-consulting-services"></a>Trabajar con los servicios de consultoría de Microsoft

Puede interactuar con los Servicios de consultoría de Microsoft (MCS) para empaquetar las aplicaciones para su uso con escritorio administrado de Microsoft. Para obtener información exacta, trabaje con el representante de su cuenta para ponerse en contacto con MCS y el ámbito de su proyecto de empaquetado de aplicaciones específico.

## <a name="roles-and-responsibilities"></a>Roles y responsabilidades

Para trabajar con el empaquetado de aplicaciones de MCS, **debes proporcionar estos elementos:**

- Los archivos del instalador de origen (por ejemplo, setup.exe o .msi).
- Las instrucciones de instalación, especificando detalles sobre el aspecto de la instalación final. Por ejemplo, ¿debería haber un acceso directo de escritorio a la aplicación? ¿Cuál debe ser la visibilidad de la aplicación? ¿La aplicación debe conectarse a un servidor y, si es así, cuál? Para obtener más información, consulte la [plantilla de solicitud de empaquetado de aplicaciones.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)
- Debes realizar tus propias pruebas de aceptación para comprobar que la aplicación funciona según lo necesites en tu entorno.

**MCS se ocupará de estas acciones:**

- Comprobar si la aplicación está prohibida o restringida en el entorno de Escritorio administrado de Microsoft.
- Pruebas de instalación, inicio y desinstalación de la aplicación para garantizar la compatibilidad con Windows 10. Si MCS detecta un problema de compatibilidad, pasará la aplicación al programa [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) para su corrección.
- Empaquetar la aplicación en la especificación y, a continuación, probar la implementación de la aplicación mediante Microsoft Intune.

## <a name="app-delivery-schedule"></a>Programación de entrega de aplicaciones

Inicie el proceso de empaquetado cargando la información de la aplicación en el portal de Escritorio administrado de Microsoft. El equipo de empaquetado revisa los nuevos envíos cada jueves. Después de revisar y empaquetar, las aplicaciones empaquetadas se entregan el siguiente viernes. Se pueden empaquetar hasta cinco aplicaciones por semana para que se inicien, pero el servicio se puede escalar para satisfacer sus necesidades.

![calendario que muestra la entrada de la aplicación un jueves (el día 21 en este ejemplo), validación multimedia al día siguiente, empaquetado el lunes siguiente (día 25) y entrega de la aplicación el viernes siguiente (el día 29)](../../media/MCS-cal.png)

Se te notificará una vez que se haya entregado la aplicación. En ese momento, tiene 21 días para realizar pruebas de aceptación y aprobar el trabajo en el portal de Escritorio administrado de Microsoft. Si detecta algún problema con la aplicación durante las pruebas de aceptación, rechace la aplicación en el portal de Escritorio administrado de Microsoft y se le conectará por correo electrónico con un empaquetador de MCS para comprender y resolver el problema.

## <a name="testing-accounts-and-environment"></a>Entorno y cuentas de prueba

Para que el equipo de empaquetado complete la migración a Microsoft Intune, le recomendamos que proporcione ciertos permisos:
 
-   Acceso a las funcionalidades de implementación de aplicaciones de Microsoft Intune para que el empaquetador agregue y asigne la aplicación 
-   Grupos de prueba, cuentas de usuario y licencias para que los empaquetadores puedan probar las aplicaciones

MCS usará esos permisos para realizar las siguientes acciones:
 
-   Asegurarse de que la aplicación funciona en una máquina virtual configurada para escritorio administrado de Microsoft
-   Cargar la aplicación en Microsoft Intune para su implementación a los usuarios

Sin estos permisos, es posible que MCS avance, pero no podrán cargar las aplicaciones en su entorno.


