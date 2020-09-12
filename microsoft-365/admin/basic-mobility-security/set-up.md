---
title: Configurar la Seguridad de Movilidad Básica
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
description: Configurar la movilidad y la seguridad básicas para proteger y administrar los dispositivos móviles de los usuarios.
ms.openlocfilehash: 079593381d6395c18cd80f3eeab2e16837a2d27a
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545813"
---
# <a name="set-up-basic-mobility-and-security"></a>Configurar la Seguridad de Movilidad Básica

La tecnología integrada de movilidad y seguridad básica de Microsoft 365 ayuda a proteger y administrar los dispositivos móviles de los usuarios, como iPhone, iPad, Androids y Windows Phone. Puede crear y administrar directivas de seguridad de dispositivo, borrar un dispositivo de forma remota y ver informes detallados del dispositivo.

¿Tiene preguntas? Para obtener preguntas más frecuentes que ayuden a resolver preguntas comunes, vea preguntas más frecuentes sobre [seguridad y movilidad básicas (FAQ)](frequently-asked-questions.md). Tenga en cuenta que no puede usar una cuenta de administrador delegada para administrar la seguridad y la movilidad básicas. Para obtener más información, consulte [Partners: oferta de administración delegada](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e). 

La administración de dispositivos forma parte del centro de seguridad & cumplimiento, por lo que tendrá que ir allí para iniciar la instalación de MDM.

## <a name="activate-the-basic-mobility-and-security-service"></a>Activación del servicio básico de movilidad y seguridad

1. Inicie sesión en Microsoft 365 con su cuenta de administrador global.

2. Vaya a [activar la movilidad y la seguridad básicas](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).

   Puede tardar algún tiempo en activar la movilidad y la seguridad básicas. Cuando termine, recibirá un correo electrónico en el que se explican los siguientes pasos que debe seguir.

## <a name="set-up-mobile-device-management"></a>Configurar la administración de dispositivos móviles

Cuando el servicio esté listo, complete los siguientes pasos para finalizar la instalación.

### <a name="step-1-required-configure-domains-for-mdm"></a>Paso 1: (obligatorio) configurar dominios para MDM

Si no tiene un dominio personalizado asociado con Microsoft 365 o si no está administrando dispositivos Windows, puede omitir esta sección. De lo contrario, tendrá que agregar registros DNS para el dominio en su host DNS. Si ya ha agregado los registros, como parte de la configuración de su dominio con Microsoft 365, ya está todo configurado. Después de agregar los registros, los usuarios de Microsoft 365 de la organización que inician sesión en su dispositivo de Windows con una dirección de correo electrónico que usa su dominio personalizado se redirigen para inscribirse en la movilidad y la seguridad básicas.

¿Necesita ayuda para configurar los registros? Busque el registrador de dominios y seleccione el nombre del registrador para ir a la ayuda paso a paso para crear un registro DNS en la lista que se proporciona en [agregar registros DNS para conectar el dominio](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider). Use esas instrucciones para crear registros CNAME descritos en [simplificar la inscripción de Windows sin Azure ad Premium](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium).

Después de agregar los dos registros CNAME, vuelva al centro de seguridad & cumplimiento y vaya a administración de dispositivos de **prevención de pérdida de datos**  >  **Device management**   para completar el paso siguiente.

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>Paso 2: (obligatorio) configurar un certificado de APNs para dispositivos iOS

Para administrar dispositivos iOS como iPad y iPhone, debe crear un certificado de APNs.

1. Inicie sesión en Microsoft 365 con su cuenta de administrador global.

2. En el explorador, escriba:  [https://protection.office.com](https://protection.office.com/) .

3. Seleccione **Data loss prevention**   >  **Administración de dispositivos**de prevención de pérdida de datos y elija **certificado de APNs para dispositivos iOS**.

4. En la página Configuración del certificado de notificación de inserción de Apple, elija **siguiente**.

5. Seleccione **descargar el archivo CSR**   y guardar la solicitud de firma de certificado en algún lugar del equipo que recuerde. Seleccione **siguiente**.

6. En la página crear un certificado de APNs:

   - Seleccione portal de APNS de Apple para abrir el portal de certificados push de Apple.
   - Sign in with an Apple ID.

     > [!IMPORTANT]
     > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

   - Seleccione crear un certificado y acepte los términos de uso.
   - Vaya a la solicitud de firma de certificado que descargó en el equipo de Microsoft 365 y selectUpload.
   - Download the APN certificate created by the Apple Push Certificate Portal to your computer.

     > [!TIP]
     > If you're having trouble downloading the certificate, refresh your browser.

7. Vuelva a Microsoft 365 y seleccione **siguiente**.

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. Seleccione  **Finalizar**.

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>Paso 3: (recomendado) configurar la autenticación multifactor

MFA ayuda a proteger el inicio de sesión en Microsoft 365 para la inscripción de dispositivos móviles requiriendo una segunda forma de autenticación. Los usuarios deben confirmar una llamada telefónica, mensaje de texto o notificación de la aplicación en el dispositivo móvil después de escribir correctamente su contraseña de cuenta de trabajo. Pueden inscribir su dispositivo solo después de que se complete esta segunda forma de autenticación. Una vez inscritos los dispositivos de usuario en la movilidad y la seguridad básica, los usuarios pueden tener acceso a los recursos de 365 de Microsoft con su cuenta profesional.

Para obtener información sobre cómo activar la MFA en el portal de Azure AD, vea [set up multi-factor Authentication](https://go.microsoft.com/fwlink/p/?LinkId=519255).

Una vez configurada la MFA, vuelva al centro de cumplimiento de & de seguridad y navegue a directivas de dispositivos de administración de dispositivos de **prevención de pérdida de datos**   >  **Device management**   >  **Device policies**   para completar el paso siguiente.

### <a name="step-4-recommended-manage-device-security-policies"></a>Paso 4: (recomendado) administrar directivas de seguridad de dispositivos

El siguiente paso es crear e implementar directivas de seguridad de dispositivo para ayudar a proteger los datos de la organización 365 de Microsoft. Por ejemplo, puede ayudar a evitar la pérdida de datos si un usuario pierde su dispositivo mediante la creación de una directiva para bloquear dispositivos tras cinco minutos de inactividad y borrar los dispositivos después de tres errores de inicio de sesión.

1. Inicie sesión en Microsoft 365 con su cuenta de administrador global.

2. Seleccione [activar la administración de dispositivos móviles](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx). Si el servicio está activado, en lugar de los pasos de activación, verá un vínculo para [administrar dispositivos](https://admin.microsoft.com/adminportal/home#/MifoDevices)   .

3. Vaya a **directivas de dispositivo**.

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Configuración básica de la Directiva de seguridad y movilidad":::

4. Cree e implemente directivas de seguridad de dispositivos adecuadas para su organización siguiendo los pasos descritos en [Create Device Security policies in Basic Mobility and Security](create-device-security-policies.md).

> [!TIP]
>
> - Al crear una nueva Directiva, es posible que desee establecer la Directiva para permitir la infracción del acceso y de la Directiva de informes en la que un dispositivo de usuario no es compatible con la Directiva. Esto le permite ver cuántos dispositivos móviles se ven afectados por la Directiva sin bloquear el acceso a Microsoft 365.
>
> - Antes de implementar una nueva Directiva para todos los usuarios de la organización, le recomendamos que la pruebe en los dispositivos usados por un pequeño número de usuarios.
>
> - Además, antes de implementar directivas, permita a su organización saber los posibles impactos de inscribir un dispositivo en la movilidad y la seguridad básicas. En función de cómo configure las directivas, se podría bloquear el acceso a Microsoft 365 a los dispositivos que no se ajustan a las directivas (dispositivos no compatibles). Los dispositivos no compatibles también pueden tener aplicaciones instaladas, fotos y otra información personal que, en un dispositivo inscrito, podría eliminarse si el dispositivo se ha borrado. Para obtener más información, consulte [borrar un dispositivo móvil en Basic Mobility and Security](wipe-mobile-device.md).

## <a name="make-sure-users-enroll-their-devices"></a>Asegurarse de que los usuarios inscriban sus dispositivos

Después de crear e implementar una directiva de administración de dispositivos móviles, todos los usuarios de Microsoft 365 con licencia de la organización a los que se aplica la Directiva de dispositivo reciben un mensaje de inscripción la próxima vez que inicien sesión en Microsoft 365 desde su dispositivo móvil. Deben completar los pasos de inscripción y activación para poder acceder a correo electrónico y documentos de Microsoft 365. Para obtener más información, vea [inscribir un dispositivo móvil con la seguridad y la movilidad básicos](enroll-your-mobile-device.md).

> [!IMPORTANT]
> Si el proceso de inscripción no admite el idioma preferido de un usuario, es posible que los usuarios reciban notificaciones de inscripción y los pasos en sus dispositivos móviles en otro idioma. Actualmente no se admiten todos los idiomas admitidos en Microsoft 365 para el proceso de inscripción en dispositivos móviles.

Los usuarios con dispositivos Android o iOS son necesarios para instalar la aplicación portal de empresa como parte del proceso de inscripción.

## <a name="related-topics"></a>Temas relacionados

[Capacidades de movilidad y seguridad básicas](capabilities.md)<br/>
[Crear directivas de seguridad de dispositivos en la movilidad y la seguridad básicas](create-device-security-policies.md)