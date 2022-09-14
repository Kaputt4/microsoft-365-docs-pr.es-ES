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
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- VSBFY23
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
description: Configure Basic Mobility and Security para proteger y administrar los dispositivos móviles de los usuarios mediante acciones como limpiar un dispositivo de forma remota.
ms.openlocfilehash: 0146378e199c9ac805d8eeaafba59598dbc70f6c
ms.sourcegitcommit: 37e137535c4f70702afe1a5eeaa899c75ee02cfd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2022
ms.locfileid: "67660781"
---
# <a name="set-up-basic-mobility-and-security"></a>Configurar Movilidad y seguridad básicas

La movilidad y seguridad básicas integrada para Microsoft 365 le ayuda a proteger y administrar los dispositivos móviles de los usuarios, como iPhones, iPads, Android y teléfonos Windows. Puede crear y administrar directivas de seguridad de dispositivo, borrar un dispositivo de forma remota y ver informes detallados del dispositivo.

¿Tiene preguntas? Para obtener una pregunta más frecuente que ayude a resolver preguntas comunes, consulte [Preguntas más frecuentes sobre movilidad y seguridad básicas.](frequently-asked-questions.yml) Tenga en cuenta que no puede usar una cuenta de administrador delegado para administrar Basic Mobility and Security. Para obtener más información, consulta [Partners: Administración delegada de ofertas](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e). 

La administración de dispositivos forma parte del Centro de cumplimiento de seguridad &, por lo que tendrá que ir allí para iniciar la configuración básica de movilidad y seguridad.

## <a name="activate-the-basic-mobility-and-security-service"></a>Activación del servicio básico de movilidad y seguridad

1. Inicie sesión en Microsoft 365 con su cuenta de administrador global.

2. Vaya a [Activar movilidad y seguridad básicas](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).

   La activación de Basic Mobility and Security puede tardar algún tiempo. Cuando termine, recibirá un correo electrónico en el que se explican los pasos siguientes.

## <a name="set-up-mobile-device-management"></a>Configuración de Mobile Administración de dispositivos

Cuando el servicio esté listo, complete los pasos siguientes para finalizar la instalación.

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a>Paso 1: (Obligatorio) Configuración de dominios para la movilidad y la seguridad básicas

Si no tiene un dominio personalizado asociado a Microsoft 365 o si no está administrando dispositivos Windows, puede omitir esta sección. De lo contrario, deberá agregar registros DNS para el dominio en el host DNS. Si ya ha agregado los registros, como parte de la configuración de su dominio con Microsoft 365, ya está todo establecido. Después de agregar los registros, los usuarios de Microsoft 365 de su organización que inician sesión en su dispositivo Windows con una dirección de correo electrónico que usa el dominio personalizado se redirigen para inscribirse en Basic Mobility and Security.

¿Necesita ayuda para configurar los registros? Busque el registrador de dominio y seleccione el nombre del registrador para ir a la ayuda paso a paso para crear un registro DNS en la lista proporcionada en [Agregar registros DNS para conectar el dominio](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider). Use esas instrucciones para crear registros CNAME descritos en [Simplificación de la inscripción de Windows sin Azure AD Premium](/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium).

Después de agregar los dos registros CNAME, vuelva al Centro de cumplimiento de seguridad & y vaya a **Administración** de dispositivos de **prevención** >  de pérdida de datos para completar el paso siguiente.

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a>Paso 2: (Obligatorio) Configurar un certificado de APNs para dispositivos iOS

Para administrar dispositivos iOS como iPad y iPhone, debe crear un certificado APNs.

1. Inicie sesión en Microsoft 365 con su cuenta de administrador global.

2. Vaya al [Centro de administración de Microsoft 365](https://portal.office.com/adminportal/home?#/MifoDevices) y elija **Certificado de APNs para iOS**.

4. En la página Configuración del certificado de notificación push de Apple, elija **Siguiente**.

5. Seleccione **Descargar el archivo CSR** y guarde la solicitud de firma de certificado en algún lugar del equipo que recuerde. Seleccione **Siguiente**.

6. En la página Crear un certificado APNs:

   - Select Apple APNS Portal to open the Apple Push Certificates Portal. 
   - Sign in with an Apple ID.

     > [!IMPORTANT]
     > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

   - Select Create a Certificate and accept the Terms of Use.
   - Vaya a la solicitud de firma de certificados que descargó en el equipo de Microsoft 365 y seleccione Cargar.
   - Download the APN certificate created by the Apple Push Certificate Portal to your computer.

     > [!TIP]
     > If you're having trouble downloading the certificate, refresh your browser.

7. Volver a Microsoft 365 y seleccione **Siguiente**.

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. Seleccione **Finalizar**.

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a>Paso 3: (Recomendado) Configuración de la autenticación multifactor

MFA ayuda a proteger el inicio de sesión en Microsoft 365 para la inscripción de dispositivos móviles, ya que requiere una segunda forma de autenticación. Los usuarios deben confirmar una llamada telefónica, un mensaje de texto o una notificación de aplicación en su dispositivo móvil después de escribir correctamente la contraseña de su cuenta profesional. Solo pueden inscribir su dispositivo una vez completada esta segunda forma de autenticación. Una vez inscritos los dispositivos de usuario en Basic Mobility and Security, los usuarios pueden acceder a los recursos de Microsoft 365 solo con su cuenta profesional.

Para obtener información sobre cómo activar MFA en el portal de Azure AD, consulte [Configuración de la autenticación multifactor](../security-and-compliance/set-up-multi-factor-authentication.md).

Después de configurar MFA, vuelva al Centro de cumplimiento de seguridad & y vaya a Data **loss prevention****Device management Device policies**(Directivas de **dispositivos** de administración  >  de dispositivos de prevención  >  de pérdida de datos) para completar el paso siguiente.

### <a name="step-4-recommended-manage-device-security-policies"></a>Paso 4: (Recomendado) Administrar directivas de seguridad de dispositivos

El siguiente paso es crear e implementar directivas de seguridad de dispositivos para ayudar a proteger los datos de la organización de Microsoft 365. Por ejemplo, puede ayudar a evitar la pérdida de datos si un usuario pierde su dispositivo mediante la creación de una directiva para bloquear los dispositivos después de cinco minutos de inactividad y borrar los dispositivos después de tres errores de inicio de sesión.

1. Inicie sesión en Microsoft 365 con su cuenta de administrador global.

2. Seleccione [Activar mobile Administración de dispositivos](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx). Si el servicio está activado, en su lugar, los pasos de activación verán un vínculo a [Administrar dispositivos](https://admin.microsoft.com/adminportal/home#/MifoDevices) .

3. Vaya a **Directivas de dispositivo**.

   :::image type="content" source="../../media/basic-mobility-security/basic-mobility-microsoft-purview.png" alt-text="Configuración básica de la directiva de seguridad y movilidad.":::

4. Cree e implemente directivas de seguridad de dispositivos adecuadas para su organización siguiendo los pasos descritos en [Creación de directivas de seguridad de dispositivos en Movilidad y seguridad básicas](create-device-security-policies.md).

> [!TIP]
>
> - Al crear una nueva directiva, es posible que desee establecer la directiva para permitir el acceso y notificar la infracción de directiva cuando un dispositivo de usuario no es compatible con la directiva. Esto le permite ver cuántos dispositivos móviles se ven afectados por la directiva sin bloquear el acceso a Microsoft 365.
>
> - Antes de implementar una nueva directiva para todos los usuarios de la organización, se recomienda probarla en los dispositivos usados por un pequeño número de usuarios.
>
> - Además, antes de implementar directivas, informe a su organización de los posibles impactos de inscribir un dispositivo en Basic Mobility and Security. En función de cómo configure las directivas, se podría bloquear el acceso a Microsoft 365 a los dispositivos que no cumplan con las directivas (dispositivos no compatibles). Los dispositivos no compatibles también pueden tener aplicaciones instaladas, fotos y otra información personal que, en un dispositivo inscrito, se podría eliminar si el dispositivo se borra. Para obtener más información, consulta [Borrar un dispositivo móvil en Basic Mobility and Security](wipe-mobile-device.md).

## <a name="make-sure-users-enroll-their-devices"></a>Asegúrese de que los usuarios inscriben sus dispositivos

Después de crear e implementar una directiva de administración de dispositivos móviles, cada usuario con licencia de Microsoft 365 de su organización al que se aplica la directiva de dispositivo recibe un mensaje de inscripción la próxima vez que inicie sesión en Microsoft 365 desde su dispositivo móvil. Deben completar los pasos de inscripción y activación para poder acceder al correo electrónico y a los documentos de Microsoft 365. Para obtener más información, consulta [Inscribir tu dispositivo móvil con Basic Mobility and Security](enroll-your-mobile-device.md).

> [!IMPORTANT]
> Si el idioma preferido de un usuario no es compatible con el proceso de inscripción, es posible que los usuarios reciban notificaciones de inscripción y pasos en sus dispositivos móviles en otro idioma. No todos los idiomas admitidos en Microsoft 365 se admiten actualmente para el proceso de inscripción en dispositivos móviles.

Los usuarios con dispositivos Android o iOS deben instalar la aplicación Portal de empresa como parte del proceso de inscripción.

## <a name="related-content"></a>Contenido relacionado

[Funcionalidades de movilidad y seguridad básicas](capabilities.md) (artículo)\
[Creación de directivas de seguridad de dispositivos en Basic Mobility and Security](create-device-security-policies.md) (artículo)
