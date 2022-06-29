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
ms.openlocfilehash: 2a4cd72cdb173afcce95250f8aa2916c8064cd26
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "66486500"
---
# <a name="trial-playbook-microsoft-business-premium"></a>Cuaderno de estrategias de prueba: Microsoft Business Premium

Le damos la bienvenida al cuaderno de estrategias de prueba de Microsoft Empresa Premium. Este cuaderno de estrategias le ayudará a sacar el máximo partido a la prueba gratuita de 30 días brindándole la experiencia acerca de cómo Microsoft 365 Empresa Premium aumenta la productividad y ayuda a proteger a la organización con funcionalidades de seguridad avanzadas. Con las recomendaciones de Microsoft, obtenga información sobre cómo configurar las características de protección contra amenazas, analizar las amenazas detectadas y responder a los ciberataques.

## <a name="set-up-the-microsoft-365-business-premium-trial"></a>Configuración de la prueba de Microsoft 365 Empresa Premium

Después de [iniciar una prueba o comprar Microsoft 365 Empresa Premium](get-microsoft-365-business-premium.md), el siguiente paso es configurarlo todo.

> [!Tip]
> Si los vínculos del cuaderno de estrategias le alejan de esta ubicación, simplemente vuelva a este cuaderno de estrategias para continuar.

En primer lugar, [configure la prueba](../business-premium/m365bp-setup.md).

Después de iniciar la prueba y completar el proceso de configuración, los cambios pueden tardar hasta dos horas en surtir efecto.

Microsoft 365 Empresa Premium incluye [directivas de seguridad preestablecidas](/security/office-365-security/preset-security-policies.md) que puede usar en su entorno. Estas directivas representan un perfil de protección de línea base adecuado para la mayoría de los usuarios. La protección estándar incluye:

- [Vínculos seguros](../security/office-365-security/safe-links.md), [datos adjuntos seguros](../security/office-365-security/safe-attachments.md) y [directivas contra la suplantación de identidad](../security/office-365-security/anti-phishing-protection.md) que engloban todo el espacio empresarial o el subconjunto de usuarios que haya elegido durante el proceso de configuración de prueba. (La suscripción de prueba es para un máximo de 25 usuarios).

- Protección para aplicaciones de productividad, como [SharePoint](/sharepoint/introduction), [OneDrive](/onedrive/one-drive-quickstart-small-business), [aplicaciones de Office](/deployoffice/about-microsoft-365-apps)y [Microsoft Teams](/microsoftteams/teams-overview).

## <a name="add-a-domain"></a>Agregar un dominio

Al probar o comprar Microsoft 365 Empresa Premium, tiene la opción de usar un dominio de su propiedad o comprar uno durante el proceso de registro.

> [!NOTE]
> Si compró uno nuevo cuando se registró, el dominio estará configurado y podrá proceder a Agregar usuarios y asignar licencias. Vaya al centro de administración ([https://admin.microsoft.com](https://admin.microsoft.com)).

1. En el menú del centro de administración, elija **Configuración** para iniciar el asistente.

2. Seleccione **Configurar el correo electrónico con un dominio personalizado** y, a continuación, **use un dominio que ya sea suyo**, como `contoso.com`.

3. Siga el resto de los pasos del asistente para completar el proceso.

   > [!Important]
   > Si ha comprado un dominio durante el registro, no verá el paso **Agregar un dominio** aquí. Vaya a **Agregar usuarios** en su lugar.

4. Siga los pasos del asistente para [crear registros DNS en cualquier proveedor de hospedaje DNS para Office 365](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) a fin de verificar que es el propietario del dominio. Si conoce el host de dominio, consulte [Agregar un dominio a Microsoft 365](/microsoft-365/admin/setup/add-domain).

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