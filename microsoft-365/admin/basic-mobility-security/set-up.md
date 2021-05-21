---
title: Configurar Movilidad y seguridad básicas
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Configura Movilidad y seguridad básicas para proteger y administrar los dispositivos móviles de los usuarios mediante acciones como limpiar un dispositivo de forma remota.
ms.openlocfilehash: 830baa79838818501101c0c4f2d3163f57d47611
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593422"
---
# <a name="set-up-basic-mobility-and-security"></a>Configurar Movilidad y seguridad básicas

La movilidad y seguridad básicas integradas para Microsoft 365 le ayuda a proteger y administrar los dispositivos móviles de los usuarios, como iPhones, iPads, Androides y Windows teléfonos móviles. Puede crear y administrar directivas de seguridad de dispositivo, borrar un dispositivo de forma remota y ver informes detallados del dispositivo.

¿Tiene preguntas? Para obtener preguntas más frecuentes para ayudar a resolver preguntas comunes, consulte [Basic Mobility and Security Frequently-asked questions (FAQ).](frequently-asked-questions.md) Tenga en cuenta que no puede usar una cuenta de administrador delegada para administrar la movilidad y la seguridad básicas. Para obtener más información, consulta [Partners: Offer delegated administration](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e). 

La administración de dispositivos forma parte del Centro de seguridad & cumplimiento, por lo que tendrás que ir allí para iniciar la configuración básica de movilidad y seguridad.

## <a name="activate-the-basic-mobility-and-security-service"></a>Activar el servicio básico de movilidad y seguridad

1. Inicie sesión en Microsoft 365 con su cuenta de administrador global.

2. Vaya a [Activar movilidad y seguridad básicas.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)

   Puede tardar algún tiempo en activar La movilidad y la seguridad básicas. Cuando finalice, recibirá un correo electrónico que explica los siguientes pasos a seguir.

## <a name="set-up-mobile-device-management"></a>Configurar la administración de dispositivos móviles

Cuando el servicio esté listo, siga estos pasos para finalizar la instalación.

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a>Paso 1: (obligatorio) Configurar dominios para movilidad básica y seguridad

Si no tienes un dominio personalizado asociado a Microsoft 365 o si no estás administrando Windows dispositivos, puedes omitir esta sección. De lo contrario, deberá agregar registros DNS para el dominio en el host DNS. Si ya ha agregado los registros, como parte de la configuración del dominio con Microsoft 365, está todo establecido. Después de agregar los registros, Microsoft 365 usuarios de la organización que inician sesión en su dispositivo Windows con una dirección de correo electrónico que usa el dominio personalizado se redirigen para inscribirse en Movilidad y seguridad básicas.

¿Necesita ayuda para configurar los registros? Busque el registrador de dominios y seleccione el nombre del registrador para ir a la ayuda paso a paso para crear un registro DNS en la lista proporcionada en Agregar registros DNS para conectar [su dominio.](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) Use estas instrucciones para crear registros CNAME descritos en [Simplificar Windows inscripción sin Azure AD Premium](/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium).

Después de agregar los dos registros CNAME, vuelva al Centro de seguridad & cumplimiento y vaya a Prevención de pérdida de datos Administración de **dispositivos** para completar  >     el siguiente paso.

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>Paso 2: (obligatorio) Configurar un certificado apns para dispositivos iOS

Para administrar dispositivos iOS como iPad y iPhones, debes crear un certificado APNs.

1. Inicie sesión en Microsoft 365 con su cuenta de administrador global.

2. En el tipo de explorador:  [https://protection.office.com](https://protection.office.com/) .

3. Seleccione  **Prevención de pérdida de** datos Administración   >  **de** dispositivos y elija Certificado **apns para dispositivos iOS.**

4. En la página Certificado de notificación de inserción Configuración Apple, elija **Siguiente**.

5. Selecciona **Descargar el archivo CSR y** guarda la solicitud de firma de certificado en algún lugar del equipo que   recuerdes. Seleccione **Siguiente**.

6. En la página Crear un certificado de APNs:

   - Selecciona Apple APNS Portal para abrir el Portal de certificados de inserción de Apple.
   - Sign in with an Apple ID.

     > [!IMPORTANT]
     > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

   - Seleccione Crear un certificado y acepte los Términos de uso.
   - Vaya a la solicitud de firma de certificado que descargó en el equipo desde Microsoft 365 y seleccioneUpload.
   - Download the APN certificate created by the Apple Push Certificate Portal to your computer.

     > [!TIP]
     > If you're having trouble downloading the certificate, refresh your browser.

7. Vuelva a Microsoft 365 y seleccione **Siguiente**.

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. Seleccione  **Finalizar**.

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>Paso 3: (recomendado) Configurar la autenticación multifactor

MFA ayuda a proteger el inicio de sesión Microsoft 365 para la inscripción de dispositivos móviles al requerir una segunda forma de autenticación. Los usuarios deben confirmar una llamada telefónica, un mensaje de texto o una notificación de aplicación en su dispositivo móvil después de escribir correctamente la contraseña de su cuenta de trabajo. Solo pueden inscribir su dispositivo una vez completada esta segunda forma de autenticación. Después de que los dispositivos de usuario se inscriban en Movilidad y seguridad básicas, los usuarios pueden acceder a Microsoft 365 recursos con solo su cuenta profesional.

Para obtener información sobre cómo activar MFA en Azure AD Portal, consulte [Configurar la autenticación multifactor](../security-and-compliance/set-up-multi-factor-authentication.md).

Después de configurar MFA, vuelve al Centro de seguridad & cumplimiento y ve a Prevención de pérdida de datos Directivas de **dispositivos** para   >     >  ****   completar el siguiente paso.

### <a name="step-4-recommended-manage-device-security-policies"></a>Paso 4: (recomendado) Administrar directivas de seguridad de dispositivos

El siguiente paso es crear e implementar directivas de seguridad de dispositivos para ayudar a proteger los Microsoft 365 de la organización. Por ejemplo, puedes ayudar a evitar la pérdida de datos si un usuario pierde su dispositivo mediante la creación de una directiva para bloquear dispositivos después de cinco minutos de inactividad y borrar dispositivos después de tres errores de inicio de sesión.

1. Inicie sesión en Microsoft 365 con su cuenta de administrador global.

2. Seleccione [Activar administración de dispositivos móviles](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx). Si el servicio está activado, en su lugar, los pasos de activación verás un vínculo a [Administrar dispositivos](https://admin.microsoft.com/adminportal/home#/MifoDevices)   .

3. Vaya a **Directivas de dispositivo**.

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Configuración básica de la directiva de seguridad y movilidad":::

4. Cree e implemente directivas de seguridad de dispositivos adecuadas para su organización siguiendo los pasos descritos en Crear directivas de seguridad de [dispositivos en Basic Mobility and Security](create-device-security-policies.md).

> [!TIP]
>
> - Al crear una nueva directiva, es posible que quieras establecer la directiva para permitir el acceso y notificar la infracción de la directiva cuando un dispositivo de usuario no es compatible con la directiva. Esto te permite ver cuántos dispositivos móviles se ven afectados por la directiva sin bloquear el acceso a Microsoft 365.
>
> - Antes de implementar una nueva directiva para todos los usuarios de la organización, se recomienda probarla en los dispositivos usados por un pequeño número de usuarios.
>
> - Además, antes de implementar directivas, haga que su organización conozca los posibles impactos de inscribir un dispositivo en Movilidad y seguridad básicas. Dependiendo de cómo configure las directivas, los dispositivos que no cumplan con las directivas (dispositivos no compatibles) podrían bloquearse para obtener acceso a Microsoft 365. Los dispositivos no compatibles también pueden tener aplicaciones instaladas, fotos y otra información personal que, en un dispositivo inscrito, podría eliminarse si se elimina el dispositivo. Para obtener más información, [consulta Borrar un dispositivo móvil en Basic Mobility and Security](wipe-mobile-device.md).

## <a name="make-sure-users-enroll-their-devices"></a>Asegurarse de que los usuarios inscriban sus dispositivos

Después de crear e implementar una directiva de administración de dispositivos móviles, cada usuario de Microsoft 365 con licencia de la organización que aplica la directiva de dispositivo recibe un mensaje de inscripción la próxima vez que inicie sesión Microsoft 365 desde su dispositivo móvil. Deben completar los pasos de inscripción y activación para poder acceder a Microsoft 365 correo electrónico y documentos. Para obtener más información, consulta [Inscribir el dispositivo móvil con Movilidad y seguridad básicas.](enroll-your-mobile-device.md)

> [!IMPORTANT]
> Si el proceso de inscripción no admite el idioma preferido de un usuario, es posible que los usuarios reciban notificaciones de inscripción y pasos en sus dispositivos móviles en otro idioma. No todos los idiomas admitidos en Microsoft 365 se admiten actualmente para el proceso de inscripción en dispositivos móviles.

Los usuarios con dispositivos Android o iOS deben instalar la Portal de empresa como parte del proceso de inscripción.

## <a name="related-content"></a>Contenido relacionado

[Capacidades de movilidad y seguridad básicas](capabilities.md) (artículo)

[Crear directivas de seguridad de dispositivos en Movilidad básica y seguridad](create-device-security-policies.md) (artículo)