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
description: Configure la movilidad y la seguridad básicas para proteger y administrar los dispositivos móviles de los usuarios.
ms.openlocfilehash: 38f122141b370468bc591df49b3e1891a8a66a43
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876869"
---
# <a name="set-up-basic-mobility-and-security"></a>Configurar Movilidad y seguridad básicas

La movilidad y seguridad básica integrada para Microsoft 365 le ayuda a proteger y administrar los dispositivos móviles de los usuarios, como iPhone, iPad, Android y teléfonos Windows. Puede crear y administrar directivas de seguridad de dispositivo, borrar un dispositivo de forma remota y ver informes detallados del dispositivo.

¿Tiene preguntas? Para obtener preguntas más frecuentes para ayudar a resolver preguntas comunes, consulte preguntas más frecuentes (P+F) sobre movilidad [y seguridad básicas.](frequently-asked-questions.md) Tenga en cuenta que no puede usar una cuenta de administrador delegada para administrar la movilidad y la seguridad básicas. Para obtener más información, consulta [Partners: Ofrecer administración delegada.](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e) 

La administración de dispositivos forma parte del Centro de seguridad & cumplimiento, por lo que tendrá que ir allí para iniciar la configuración básica de movilidad y seguridad.

## <a name="activate-the-basic-mobility-and-security-service"></a>Activación del servicio básico de movilidad y seguridad

1. Inicie sesión en Microsoft 365 con su cuenta de administrador global.

2. Vaya a [Activar movilidad y seguridad básicas.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)

   La movilidad y la seguridad básicas pueden tardar algún tiempo en activarse. Cuando termine, recibirá un correo electrónico que explica los siguientes pasos que debe realizar.

## <a name="set-up-mobile-device-management"></a>Configurar la administración de dispositivos móviles

Cuando el servicio esté listo, siga estos pasos para finalizar la instalación.

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a>Paso 1: (Obligatorio) Configurar dominios para movilidad y seguridad básicas

Si no tiene un dominio personalizado asociado a Microsoft 365 o si no está administrando dispositivos Windows, puede omitir esta sección. De lo contrario, deberá agregar registros DNS para el dominio en el host DNS. Si ya ha agregado los registros, como parte de la configuración de su dominio con Microsoft 365, está todo configurado. Después de agregar los registros, los usuarios de Microsoft 365 de su organización que inicien sesión en su dispositivo Windows con una dirección de correo electrónico que use su dominio personalizado se redirigirán para inscribirse en Movilidad y seguridad básicas.

¿Necesita ayuda para configurar los registros? Busque su registrador de dominios y seleccione el nombre del registrador para ir a la ayuda paso a paso para crear un registro DNS en la lista proporcionada en Agregar registros DNS para conectar [su dominio.](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) Usa esas instrucciones para crear registros CNAME que se describen en Simplificar la inscripción [de Windows sin Azure AD Premium.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)

Después de agregar los dos registros CNAME, vuelva al Centro de seguridad y cumplimiento de & y vaya a Administración de **dispositivos** de prevención de pérdida de datos para  >     completar el paso siguiente.

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>Paso 2: (Obligatorio) Configurar un certificado APNs para dispositivos iOS

Para administrar dispositivos iOS como iPad y iPhone, debe crear un certificado APNs.

1. Inicie sesión en Microsoft 365 con su cuenta de administrador global.

2. En el tipo de explorador:  [https://protection.office.com](https://protection.office.com/) .

3. Seleccione  **Administración de dispositivos de prevención** de pérdida de   > datos y elija Certificado **de APNs para dispositivos iOS.** ****

4. En la página Configuración del certificado de notificación de inserción de Apple, elija **Siguiente.**

5. Seleccione **Descargar el archivo CSR y** guarde la solicitud de firma de certificado en algún lugar del equipo que   recuerde. Seleccione **Siguiente**.

6. En la página Crear un certificado de APNs:

   - Seleccione Apple APNS Portal para abrir el Portal de certificados de inserción de Apple.
   - Sign in with an Apple ID.

     > [!IMPORTANT]
     > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

   - Seleccione Crear un certificado y acepte los Términos de uso.
   - Vaya a la solicitud de firma de certificado que descargó en su equipo desde Microsoft 365 y seleccioneUpload.
   - Download the APN certificate created by the Apple Push Certificate Portal to your computer.

     > [!TIP]
     > If you're having trouble downloading the certificate, refresh your browser.

7. Vuelva a Microsoft 365 y seleccione **Siguiente.**

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. Seleccione  **Finalizar**.

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>Paso 3: (Recomendado) Configurar la autenticación multifactor

MFA ayuda a proteger el inicio de sesión en Microsoft 365 para la inscripción de dispositivos móviles al requerir una segunda forma de autenticación. Los usuarios deben confirmar una llamada telefónica, un mensaje de texto o una notificación de la aplicación en su dispositivo móvil después de escribir correctamente la contraseña de su cuenta de trabajo. Solo pueden inscribir su dispositivo después de que se complete este segundo formulario de autenticación. Después de que los dispositivos de usuario se inscriban en movilidad y seguridad básicas, los usuarios pueden acceder a los recursos de Microsoft 365 solo con su cuenta profesional.

Para obtener información sobre cómo activar MFA en el portal de Azure AD, vea [Configurar la autenticación multifactor.](https://go.microsoft.com/fwlink/p/?LinkId=519255)

Después de configurar MFA, vuelva al Centro de seguridad y cumplimiento de & y vaya a directivas de dispositivos de administración de **dispositivos** de prevención de pérdida de datos para   >     >  ****   completar el paso siguiente.

### <a name="step-4-recommended-manage-device-security-policies"></a>Paso 4: (Recomendado) Administrar directivas de seguridad de dispositivos

El siguiente paso es crear e implementar directivas de seguridad de dispositivos para ayudar a proteger los datos de la organización de Microsoft 365. Por ejemplo, puedes ayudar a evitar la pérdida de datos si un usuario pierde su dispositivo mediante la creación de una directiva para bloquear dispositivos después de cinco minutos de inactividad y borrar dispositivos después de tres errores de inicio de sesión.

1. Inicie sesión en Microsoft 365 con su cuenta de administrador global.

2. Seleccione [Activar administración de dispositivos móviles.](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx) Si el servicio está activado, en su lugar, los pasos de activación verás un vínculo a [Administrar dispositivos.](https://admin.microsoft.com/adminportal/home#/MifoDevices)  

3. Ve a **Directivas de dispositivo.**

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Configuración de directivas básicas de seguridad y movilidad":::

4. Cree e implemente directivas de seguridad de dispositivos adecuadas para su organización siguiendo los pasos descritos en Crear directivas de seguridad de dispositivos en Movilidad y [Seguridad básicas.](create-device-security-policies.md)

> [!TIP]
>
> - Al crear una nueva directiva, es posible que quieras establecer la directiva para permitir el acceso y notificar la infracción de la directiva cuando un dispositivo de usuario no cumple con la directiva. Esto le permite ver cuántos dispositivos móviles se ven afectados por la directiva sin bloquear el acceso a Microsoft 365.
>
> - Antes de implementar una nueva directiva para todos los usuarios de la organización, te recomendamos que la pruebes en los dispositivos usados por un pequeño número de usuarios.
>
> - Además, antes de implementar directivas, haga que su organización conozca las posibles consecuencias de inscribir un dispositivo en movilidad y seguridad básicas. Según cómo configure las directivas, los dispositivos que no cumplan con las directivas (dispositivos no compatibles) podrían bloquearse para que no tengan acceso a Microsoft 365. Los dispositivos no compatibles también pueden tener aplicaciones instaladas, fotos y otra información personal que, en un dispositivo inscrito, podrían eliminarse si se elimina el dispositivo. Para obtener más información, consulta [Borrar un dispositivo móvil en Movilidad y seguridad básicas.](wipe-mobile-device.md)

## <a name="make-sure-users-enroll-their-devices"></a>Asegurarse de que los usuarios inscriban sus dispositivos

Después de crear e implementar una directiva de administración de dispositivos móviles, cada usuario con licencia de Microsoft 365 de su organización que aplique la directiva de dispositivo recibirá un mensaje de inscripción la próxima vez que inicie sesión en Microsoft 365 desde su dispositivo móvil. Deben completar los pasos de inscripción y activación para poder acceder a documentos y correo electrónico de Microsoft 365. Para obtener más información, consulta [Inscribir el dispositivo móvil con movilidad y seguridad básicas.](enroll-your-mobile-device.md)

> [!IMPORTANT]
> Si el proceso de inscripción no admite el idioma preferido de un usuario, es posible que los usuarios reciban notificaciones de inscripción y pasos en sus dispositivos móviles en otro idioma. Actualmente, no todos los idiomas admitidos en Microsoft 365 son compatibles con el proceso de inscripción en dispositivos móviles.

Los usuarios con dispositivos Android o iOS deben instalar la aplicación Portal de empresa como parte del proceso de inscripción.

## <a name="related-topics"></a>Temas relacionados

[Capacidades de Movilidad y seguridad básicas](capabilities.md)<br/>
[Crear directivas de seguridad de dispositivos en Movilidad y seguridad básicas](create-device-security-policies.md)