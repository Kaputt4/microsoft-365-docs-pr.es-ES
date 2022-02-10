---
title: Trabajar con los servicios de consultoría de Microsoft
description: Preparación y pasos a seguir para trabajar con MCS para empaquetar tus aplicaciones
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 5dd6bf62625d6b22a0585645abbeb24dabd6c9fd
ms.sourcegitcommit: cafca45069819a44c7cf8c67f6c1e105de1b3393
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2022
ms.locfileid: "62520456"
---
# <a name="working-with-microsoft-consulting-services"></a>Trabajar con los servicios de consultoría de Microsoft

Puedes interactuar con Microsoft Consulting Services (MCS) para empaquetar tus aplicaciones para usarlas con Microsoft Managed Desktop. Para obtener más información, trabaje con el representante de la cuenta para ponerse en contacto con MCS para revisar el proyecto de empaquetado de aplicaciones específico.

## <a name="roles-and-responsibilities"></a>Roles y responsabilidades

| Función | Responsabilidad |
| ------ | ------ |
| You | Para trabajar con el empaquetado de la aplicación MCS, **debes proporcionar los siguientes elementos**: <ul><li> Los archivos del instalador de origen (por ejemplo, setup.exe o .msi).</li><li>Instrucciones de instalación que especifican detalles sobre el aspecto de la instalación final. Por ejemplo, ¿debería haber un acceso directo de escritorio a la aplicación? ¿Cuál debe ser la visibilidad de la aplicación? ¿La aplicación debe conectarse a un servidor y, si es así, cuál? Para obtener más información, vea la plantilla [de solicitud de empaquetado de aplicaciones](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx).</li><li>Debes realizar tus propias pruebas de aceptación para comprobar que la aplicación funciona según lo esperado en el entorno.</li><ul> |
| Servicios de consultoría de Microsoft (MCS) | **MCS se ocupará de las siguientes acciones:** <ul><li>Comprueba si la aplicación está prohibida o restringida en el entorno de Escritorio administrado de Microsoft.</li><li>Pruebe la instalación, el inicio y la desinstalación de la aplicación para garantizar la compatibilidad con Windows 10. Si MCS detecta un problema de compatibilidad, la entregará al programa [App Assure](/fasttrack/products-and-capabilities#app-assure) para su corrección.</li><li>Empaqueta la aplicación según tus especificaciones y prueba la implementación de aplicaciones mediante Microsoft Intune.</li><ul>

## <a name="app-delivery-schedule"></a>Programación de entrega de aplicaciones

Inicie el proceso de empaquetado cargando la información de la aplicación en el portal de Escritorio administrado de Microsoft. El equipo de empaquetado revisa los nuevos envíos cada jueves. Después de revisar y empaquetar, las aplicaciones empaquetadas se entregan el viernes siguiente. Se pueden empaquetar hasta cinco aplicaciones por semana para iniciarse, pero el servicio puede escalar para satisfacer sus necesidades.

![calendario que muestra la entrada de aplicaciones un jueves (el día 21 en este ejemplo), validación de medios al día siguiente, empaquetado el lunes siguiente (día 25) y entrega de aplicaciones el viernes siguiente (el día 29).](../../media/MCS-cal.png)

Se te notificará una vez que se haya entregado la aplicación. En ese momento, tiene 21 días para realizar pruebas de aceptación y aprobar el trabajo en el portal de Escritorio administrado de Microsoft. Si descubres un problema con la aplicación durante las pruebas de aceptación, rechaza la aplicación en el portal de Escritorio administrado de Microsoft. Se conectará por correo electrónico con un empaquetador de Servicios de consultoría de Microsoft (MCS) para comprender y resolver el problema.

## <a name="testing-accounts-and-environment"></a>Probar cuentas y entorno

Para que el equipo de empaquetado complete la migración a Microsoft Intune, se recomienda proporcionar ciertos permisos:

- Acceso a Microsoft Intune de implementación de aplicaciones para que el empaquetador agregue y asigne la aplicación.
- Grupos de prueba, cuentas de usuario y licencias para que los empaquetadores puedan probar las aplicaciones.

MCS usará esos permisos para realizar las siguientes acciones:

- Asegúrese de que la aplicación funciona en una máquina virtual configurada para El escritorio administrado de Microsoft.
- Upload la aplicación para Microsoft Intune para la implementación a los usuarios.

Sin estos permisos, es posible que MCS avance, pero no podrán cargar las aplicaciones en el entorno.
