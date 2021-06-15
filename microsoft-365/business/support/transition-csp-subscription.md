---
title: Transición a una suscripción de CSP de Microsoft 365 Empresa
description: Descubra cómo puede realizar la transición de una suscripción Microsoft 365 Empresa CSP de vista previa a disponibilidad general (GA).
author: jasongroce
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-mar
- AdminSurgePortfolio
ms.author: jasongroce
ms.topic: article
manager: jasonh
ms.prod: microsoft-365-business
localization_priority: Normal
audience: microsoft-business
keywords: Microsoft 365 Empresa, Microsoft 365, SMB, transición suscripción de CSP
ms.date: 11/01/2017
ms.openlocfilehash: 3f6c71edb50cc3c5509e61a83efb64185c10648d
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925011"
---
# <a name="transition-a-microsoft-365-business-csp-subscription"></a>Transición a una suscripción de CSP de Microsoft 365 Empresa

Si tienes una suscripción de CSP de versión preliminar de Microsoft 365 sigue esta guía para averiguar cómo puedes hacer la transición de tu suscripción de versión preliminar existente a Microsoft 365 Empresa GA (disponibilidad general).

**Cómo realizar la transición de una suscripción de versión preliminar a GA**

1. Inicie sesión en el <a href="https://partnercenter.microsoft.com" target="_blank">Centro de partners</a>.
2. En el panel, selecciona **Clientes** y, a continuación, busca y selecciona el nombre de la compañía.

    Se mostrarán las suscripciones de la compañía.

    ![Suscripciones de cliente en el Centro de partners](../../media/pc_customer_subscriptions_1.png)
    
3. En la página **Suscripciones** de la empresa, seleccione **Agregar suscripción**.
4. En la **página Nueva suscripción,** seleccione **Pequeña** empresa y, a continuación, **seleccione Microsoft 365 Empresa** de la lista.
5. Añade el número de licencias y, a continuación, selecciona **Siguiente: Revisión** para revisar la suscripción y, a continuación, selecciona **Enviar**.

    ![Revisar la nueva suscripción a Microsoft 365 Empresa](../../media/pc_customer_reviewnewsubscription.png)

    Las **suscripciones basadas en licencia** mostrará **Versión preliminar de Microsoft 365 Empresa** y **Microsoft 365 Empresa**. A continuación, suspenderás la suscripción de vista previa.

6. Selecciona **Versión preliminar de Microsoft 365 Empresa**.
7. En la **Microsoft 365 Empresa vista previa,** seleccione **Suspendido** para suspender la suscripción de vista previa.

    ![Suspender la suscripción a la versión preliminar de Microsoft 365 Empresa](../../media/pc_customer_m365bpreview_suspend.png)

8. Selecciona **Enviar** para confirmar.

    En la **página Suscripciones,** confirme que el estado **Microsoft 365 Empresa vista previa** muestra **Suspendido**.

    ![Confirmar el estado suspendido de la suscripción de la vista preliminar](../../media/pc_customer_m365bpreview_suspend_confirm.png)

9. Opcionalmente, también puedes validar el contrato de licencia. Para ello, sigue estos pasos:
    1. Selecciona **Usuarios y licencias** desde la página **Suscripciones** de la compañía.
    2. En la **página Usuarios y licencias,** seleccione un usuario.
    3. En la página del usuario, compruebe la sección Asignar **licencias** y confirme que muestra **Microsoft 365 Empresa**.

        ![Confirmar que al usuario se le asigna la licencia de Microsoft 365 Empresa](../../media/pc_customer_userslicenses_m365b_validate.png)

## <a name="impact-to-customers-and-users-during-and-after-transition"></a>Impacto en clientes y usuarios durante y después de la transición

No hay ningún impacto para los clientes y los usuarios durante la transición y después de la transición.

## <a name="impact-to-customers-who-dont-transition"></a>Impacto en los clientes que no realizan la transición

En la siguiente tabla se resume el impacto para los clientes que no realizan la transición desde una suscripción de versión preliminar de Microsoft 365 Empresa a una suscripción de Microsoft 365 Empresa.

|       | T-0 a T+30     | T+30 a T+60 | T+60 a T+120 | Más allá de T+120  |
|-------|-----------------|--------------|---------------|---------------|
| **Estado** | En periodo de gracia | Expirada      | Deshabilitada      | Desaprovisionada |
| **Impactos del servicio**                                                        |
| **Portal de administración de Microsoft 365 Empresa** | Sin impacto en la funcionalidad | Sin impacto en la funcionalidad | Puede agregar o eliminar usuarios, comprar suscripciones.</br> No se pueden asignar ni revocar licencias. | Se elimina la suscripción del cliente y todos los datos. El administrador puede administrar otras suscripciones de pago. |
| **Aplicaciones de Office**                         | Ningún impacto en el usuario final | Ningún impacto en el usuario final | Office entra en modo de funcionalidad reducida.</br> Los usuarios solo pueden ver los archivos. | Office entra en modo de funcionalidad reducida.</br> Los usuarios solo pueden ver los archivos. |
| **Servicios en la nube (SharePoint Online, Exchange Online, Skype, Teams, etc.)** | Ningún impacto en el usuario final | Ningún impacto en el usuario final | Los usuarios finales y administradores no tienen acceso a datos en la nube. | Se elimina la suscripción del cliente y todos los datos. |
| **Componentes EM+S** | Ningún impacto en el administrador</br> Ningún impacto en el usuario final | Ningún impacto en el administrador</br> Ningún impacto en el usuario final | La funcionalidad ya no se aplica.</br> Consulta [Impactos del dispositivo móvil en la expiración de la suscripción](#mobile-device-impacts-upon-subscription-expiration) y [Equipo con Windows 10 tras la expiración de la suscripción](#windows-10-pc-impacts-upon-subscription-expiration) para obtener más información. | La funcionalidad ya no se aplica.</br> Consulta [Impactos del dispositivo móvil en la expiración de la suscripción](#mobile-device-impacts-upon-subscription-expiration) y [Equipo con Windows 10 tras la expiración de la suscripción](#windows-10-pc-impacts-upon-subscription-expiration) para obtener más información. |
| **Windows 10 Empresa** | Ningún impacto en el administrador</br> Ningún impacto en el usuario final | Ningún impacto en el administrador</br> Ningún impacto en el usuario final | La funcionalidad ya no se aplica.</br> Consulta [Impactos del dispositivo móvil en la expiración de la suscripción](#mobile-device-impacts-upon-subscription-expiration) y [Equipo con Windows 10 tras la expiración de la suscripción](#windows-10-pc-impacts-upon-subscription-expiration) para obtener más información. | La funcionalidad ya no se aplica.</br> Consulta [Impactos del dispositivo móvil en la expiración de la suscripción](#mobile-device-impacts-upon-subscription-expiration) y [Equipo con Windows 10 tras la expiración de la suscripción](#windows-10-pc-impacts-upon-subscription-expiration) para obtener más información. |
| **Inicio de sesión de Azure AD en un equipo de Windows 10** | Ningún impacto en el administrador</br> Ningún impacto en el usuario final | Ningún impacto en el administrador</br> Ningún impacto en el usuario final | Ningún impacto en el administrador</br> Ningún impacto en el usuario final | Una vez eliminado el espacio empresarial, un usuario solo puede iniciar sesión con credenciales locales. Vuelva a crear la imagen del dispositivo si no hay credenciales locales. |

## <a name="mobile-device-impacts-upon-subscription-expiration"></a>Impactos del dispositivo móvil tras la expiración de la suscripción

En la tabla siguiente se resume el impacto en las directivas de administración de aplicaciones en dispositivos móviles.

|                            | Experiencia con licencia completa                      | T+60 días tras expiración          |
|----------------------------|------------------------------------------------|------------------------------------|
| **Eliminar archivos de trabajo de un dispositivo inactivo** | Los archivos de trabajo se eliminan después de los días seleccionados | Los archivos de trabajo permanecen en los dispositivos personales del usuario |
| **Obligar a los usuarios a guardar todos los archivos de trabajo en OneDrive para la Empresa** | Los archivos de trabajo solo se pueden guardar en OneDrive para la Empresa | Los archivos de trabajo se pueden guardar en cualquier lugar |
| **Cifrar archivos de trabajo** | Los archivos de trabajo se cifran | Los archivos de trabajo ya no se cifran.</br> Se eliminan las directivas de seguridad y se eliminan los datos de Office sobre aplicaciones. |
| **Exigir un PIN o huella dactilar para tener acceso a aplicaciones de Office** | Acceso restringido a aplicaciones | Ninguna restricción de acceso en nivel de aplicaciones |
| **Restablecer PIN cuando se produce un error de inicio de sesión** | Acceso restringido a aplicaciones | Ninguna restricción de acceso en nivel de aplicaciones |
| **Requerir que los usuarios vuelvan a iniciar sesión después de que las aplicaciones de Office hayan estado inactivas** | Inicio de sesión requerido | No es necesario iniciar sesión |
| **Denegar acceso a archivos de trabajo en dispositivos desbloqueados o modificados** | No se puede acceder a los archivos de trabajo en dispositivos con jailbreak o root | Es posible acceder a archivos de trabajo en dispositivos desbloqueados o modificados |
| **Permitir a los usuarios copiar el contenido de aplicaciones de Office en aplicaciones personales** | Copiar y pegar restringidos a las aplicaciones disponibles como parte de Microsoft 365 suscripción | Copiar/pegar disponible en todas las aplicaciones |

## <a name="windows-10-pc-impacts-upon-subscription-expiration"></a>Impactos de equipos con Windows 10 tras la expiración de la suscripción

La siguiente tabla resume el impacto en las directivas de configuración de dispositivos con Windows 10.

|                            | Experiencia con licencia completa                      | T+60 días tras expiración          |
|----------------------------|------------------------------------------------|------------------------------------|
| **Ayudar a proteger los equipos de amenazas con Windows Defender** | Activar/desactivar fuera de control de usuario | El usuario puede activar o desactivar Windows Defender en el equipo Windows 10 equipo |
| **Ayudar a proteger los equipos de amenazas basadas en web en Microsoft Edge** | Protección para PC en Microsoft Edge | El usuario puede activar o desactivar la protección del equipo en Microsoft Edge |
| **Apagar pantalla del dispositivo cuando está inactivo** | El administrador define la directiva de intervalo de tiempo de espera de pantalla | El tiempo de espera de pantalla lo puede configurar el usuario final |
| **Permitir que los usuarios descarguen aplicaciones desde Microsoft Store** | El administrador define si un usuario puede descargar aplicaciones de Microsoft Store | El usuario puede descargar aplicaciones de Microsoft Store en cualquier momento |
| **Permitir que los usuarios accedan a Cortana** | El administrador define la directiva sobre acceso de usuarios a Cortana | Dispositivos de usuario para activar/desactivar Cortana |
| **Permitir que los usuarios reciban sugerencias y anuncios de Microsoft** | El administrador define la directiva sobre la recepción de los usuarios de sugerencias y anuncios de Microsoft | El usuario puede activar y desactivar sugerencias y anuncios de Microsoft |
| **Permitir a los usuarios copiar contenido de aplicaciones de Office en aplicaciones personales** | El administrador define la directiva para mantener Windows 10 dispositivos actualizados | Los usuarios pueden decidir cuándo actualizar Windows |
