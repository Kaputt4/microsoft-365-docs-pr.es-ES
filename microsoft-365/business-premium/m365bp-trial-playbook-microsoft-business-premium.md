---
title: Cuaderno de estrategias de prueba de Microsoft Defender para Empresas Premium
f1.keywords:
- NOCSH
ms.author: v-kcirillo
author: cirilk
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.collection: m365-security-compliance
ms.localizationpriority: high
ms.prod: m365-security
search.appverid:
- MOE150
- MET150
description: Sacar el máximo partido de la prueba de Microsoft 365 Empresa Premium. Pruebe algunas de las funcionalidades clave de productividad y seguridad.
ms.openlocfilehash: 740d0b394148a84434c13fd4a3fcd38e8c617c03
ms.sourcegitcommit: 66228a5506fdceb4cbf0d55b9de3f2943740134f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "66089781"
---
# <a name="trial-playbook-microsoft-business-premium"></a>Cuaderno de estrategias de prueba: Microsoft Business Premium

Le damos la bienvenida al cuaderno de estrategias de prueba de Microsoft Empresa Premium. Este cuaderno de estrategias le ayudará a sacar el máximo partido a la prueba gratuita de 30 días enseñándole cómo Microsoft 365 Empresa Premium aumenta la productividad y ayuda a proteger a la organización con Defender para Empresas. Con las recomendaciones de Microsoft, obtendrá información sobre cómo Defender puede ayudarle a definir directivas de protección, analizar amenazas para la organización y responder a ciberataques.

## <a name="set-up-the-microsoft-365-business-premium-trial"></a>Configuración de la prueba de Microsoft 365 Empresa Premium

Después de [iniciar una prueba o comprar Microsoft 365 Empresa Premium](get-microsoft-365-business-premium.md), el siguiente paso es configurarlo todo.

> [!Tip]
> Si los vínculos del cuaderno de estrategias le alejan de esta ubicación, simplemente vuelva a este cuaderno de estrategias para continuar.

En primer lugar, [configure la prueba](../business-premium/m365bp-setup.md).

Después de iniciar la prueba y completar el proceso de configuración, los cambios pueden tardar hasta dos horas en surtir efecto.

Hemos configurado automáticamente las [Directivas de seguridad preestablecidas](/security/office-365-security/preset-security-policies.md) en tu entorno. Estas directivas representan un perfil de protección de línea base adecuado para la mayoría de los usuarios. La protección estándar incluye:

- Vínculos seguros, datos adjuntos seguros y directivas contra la suplantación de identidad que engloban a todo el espacio empresarial o al subconjunto de usuarios que hayas elegido durante el proceso de configuración de prueba.

- Protección para todas las características de Microsoft 365 Empresa Premium, como SharePoint, OneDrive, aplicaciones de Office y Microsoft Teams.

## <a name="add-a-domain"></a>Agregar un dominio

Al comprar la prueba de Microsoft 365 Empresa Premium, tiene la opción de usar un dominio de su propiedad o comprar uno durante el registro.

> [!Note]
> Si compró uno nuevo cuando se registró, el dominio estará configurado y podrá proceder a Agregar usuarios y asignar licencias. Vaya al centro de administración ([https://admin.microsoft.com](https://admin.microsoft.com)).

1. En el menú del centro de administración, elija **Configuración** para iniciar el asistente.

2. Seleccione **Configurar el correo electrónico con un dominio personalizado** y, a continuación, **use un dominio que ya sea suyo**, como contoso.com.

3. Siga el resto de los pasos del asistente para completar el proceso.

   > [!Important]
   > Si compró un dominio durante el registro, no verá el paso Agregar un dominio aquí. Vaya a Agregar usuarios en su lugar.

4. Siga los pasos del asistente para Crear registros DNS en cualquier proveedor de hospedaje DNS para Office 365 a fin de verificar que es el propietario del dominio. Si conoce el host de dominio, consulte Agregar un dominio a Microsoft 365.

5. Si su proveedor de hospedaje es GoDaddy u otro host habilitado con conexión de dominio, el proceso es sencillo y se le pedirá automáticamente que inicie sesión y que permita que Microsoft autentique en su nombre.

## <a name="onboard-and-protect-devices"></a>Incorporación y protección de dispositivos

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. Ejecute el [asistente para la instalación](../security/defender-business/mdb-use-wizard.md).

3. [Incorporar dispositivos](../security/defender-business/mdb-onboard-devices.md).

4. [Revisar las directivas de seguridad](../security/defender-business/mdb-configure-security-settings.md).

## <a name="use-office-apps-on-devices"></a>Usar aplicaciones de Office en dispositivos

1. En primer lugar, tendrá que [instalar Office](m365bp-install-office-apps.md).

2. Vaya a office.com e [inicie sesión](https://support.microsoft.com/office/get-started-at-office-com-91a4ec74-67fe-4a84-a268-f6bdf3da1804).

3. Crear un documento de Office, como un [documento de Word](https://support.microsoft.com/office/basic-tasks-in-word-87b3243c-b0bf-4a29-82aa-09a681999fdc).

4. [Compartir un documento](https://support.microsoft.com/office/share-your-documents-651e1cb9-9a51-46dc-8d32-bdb7d928eedd) con un miembro del equipo.

## <a name="start-using-the-microsoft-365-defender-portal"></a>Empezar a usar el portal de Microsoft 365 Defender 

1. Acceder al portal de Microsoft 365 Defender en [https://security.microsoft.com](https://security.microsoft.com).

2. Dedique algo de tiempo a [familiarizarse con el portal](../security/defender-business/mdb-get-started.md).

3. Ahora, [evalúe su posición de seguridad](../security/defender/microsoft-secure-score.md).

4. Familiarícese con [cómo responder ante un incidente de seguridad](../security/defender-business/mdb-respond-mitigate-threats.md).

5. Por último, [revise las acciones de corrección](../security/defender-business/mdb-review-remediation-actions.md).

## <a name="see-also"></a>Consulte también

- [Microsoft 365 Empresa Premium &mdash;, ciberseguridad para pequeñas empresas](index.md)