---
title: Integrar los vales de ServiceNow en el centro de seguridad y cumplimiento de Microsoft 365
description: Obtenga información sobre cómo crear y realizar un seguimiento de vales en ServiceNow desde el centro de seguridad y el centro de cumplimiento de Microsoft 365.
keywords: seguridad, Microsoft 365, M365, cumplimiento, centro de cumplimiento, centro de seguridad, ServiceNow, billetes, tareas, nieve, conexión
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: a2650efbac0966b84e6fbfd6ce78cb732f4933b3
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769658"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a>Integrar los vales de ServiceNow en el centro de seguridad y cumplimiento de Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!CAUTION]
>**El período de versión preliminar del conector de ServiceNow está finalizando**<br>
>Esta capacidad ya no estará disponible al final de noviembre de 2020. Gracias por sus comentarios y el soporte técnico continuo mientras determinamos los siguientes pasos.

ServiceNow es una plataforma de informática en la nube popular que ayuda a las empresas a administrar flujos de trabajo digitales para operaciones empresariales. Su plataforma ahora tiene flujos de trabajo de ti, flujos de trabajo de empleados y flujos de trabajo de clientes. [Obtenga más información sobre ServiceNow](https://www.servicenow.com/)

Microsoft se ha asociado con ServiceNow para facilitar a los administradores de ti la administración de sus billetes y tareas en ambas plataformas. El [centro de seguridad 365](overview-security-center.md) de Microsoft y el [centro de cumplimiento de Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) están mejorados con la capacidad de crear y realizar un seguimiento de vales en ServiceNow de forma nativa.

- [**Administración de vales de ServiceNow en el centro de seguridad**](tickets-security-center.md)
- **Administrar vales de ServiceNow en el centro de cumplimiento** (próximamente)

## <a name="prerequisites"></a>Requisitos previos

Tener acceso al centro de seguridad de Microsoft 365 o al centro de cumplimiento y a una instancia de ServiceNow con:  

* Kingston o una versión superior
* Tener credenciales de admin HI
* Tener privilegios de administrador en la instancia del proveedor de destino

ServiceNow recomienda que los usuarios conserven la configuración predeterminada en su instancia de ServiceNow. La realización de personalizaciones puede provocar errores al completar la lista de comprobación de instalación e integración con el centro de seguridad de Microsoft 365.

## <a name="data-exchange"></a>Intercambio de datos

Cuando conecta el centro de seguridad de Microsoft 365 o el centro de cumplimiento a ServiceNow, Microsoft recibe los siguientes datos adicionales:

* Nombre de instancia de ServiceNow
* IDENTIFICADOR de cliente de ServiceNow
* Secreto de cliente de ServiceNow
* Tokens de actualización & acceso a ServiceNow

Al crear un vale de ServiceNow desde el centro de seguridad de Microsoft 365 o el centro de cumplimiento, se envían los siguientes datos a ServiceNow:

* IDENTIFICADOR de usuario que inicia la creación de vales
* Nombre de tarea
* Descripción de la tarea
* Priority
* Fecha de vencimiento
* Origen de la recomendación (recomendación del usuario o recomendación de Microsoft)
* Categoría de recomendación (dispositivos, datos, aplicaciones, identidad, infraestructura)

## <a name="connect-to-servicenow"></a>Conectarse a ServiceNow

Vaya a [crear y realizar un seguimiento de los vales de ServiceNow en el centro de seguridad de Microsoft 365](tickets-security-center.md) para obtener información sobre cómo conectarse a ServiceNow. La conexión desde el centro de cumplimiento de Microsoft 365 estará disponible próximamente.

## <a name="troubleshooting"></a>Solución de problemas

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a>Recibe un error en el primer paso de la lista de comprobación de instalación (creación de OAuth)

**Mensaje de error** : se rechazó la operación de lectura contra ' oauth_entity ' del ámbito ' x_mioms_m365ticket ' debido a la Directiva de acceso entre ámbitos de la tabla

La aplicación supone que cualquier administrador de la instancia de ServiceNow puede crear y leer entidades de OAuth. Este error puede deberse a una personalización en su instancia de ServiceNow que restringe quién puede crear o leer entidades de OAuth.

**ServiceNow recomienda a los usuarios mantener la funcionalidad predeterminada.**

Establezca la configuración de la tabla "registros de aplicación" en default:

* Label = registros de aplicación
* Name = oauth_entity
* Accesible desde = todos los ámbitos de aplicación
* Puede leer = casilla de verificación seleccionada

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a>Cómo validar la entidad de OAuth creada para el conector de cumplimiento de & de seguridad de Microsoft 365

Vaya a la tabla registros de aplicaciones ( **menú > el registro de aplicaciones de OAuth > sistema** ) en ServiceNow. Busque la entidad OAuth que ha creado, con el nombre que le ha asignado.

### <a name="signing-in-as-the-integration-user"></a>Iniciar sesión como usuario de integración

Antes de autorizar la conexión entre el centro de seguridad de Microsoft 365 y ServiceNow, asegúrese de usar el inicio de sesión de usuario de integración y la contraseña que creó en los pasos de instalación. No use sus credenciales personales.

1. Vaya a la página de autorización en ServiceNow.
2. Si ha iniciado sesión con sus credenciales personales, seleccione el vínculo **que no se encuentra** en la esquina superior derecha.
3. Inicie sesión en ServiceNow como el usuario de integración que creó anteriormente a partir de la lista de comprobación de instalación.  
4. Seleccione **permitir** en la página de servicenow que pregunta si el conector Security + Compliance Connector puede conectarse a su cuenta de servicenow.
5. Continúe con los pasos de configuración.

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a>Cómo validar el usuario de integración creado con la lista de comprobación de instalación para el conector de seguridad & cumplimiento de Microsoft 365

Vaya a la tabla de usuarios **(menú > User Administration >** users) en ServiceNow y busque el usuario de integración creado por usted, con el nombre que le haya asignado.

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a>Su empresa tiene habilitado el inicio de sesión único, lo que le impide conectarse a ServiceNow a través del centro de seguridad de Microsoft 365

Si su compañía ha habilitado el inicio de sesión único y recibe un error o inicia sesión, siga una de las dos soluciones.

#### <a name="sign-in-to-servicenow-as-the-integration-user"></a>Inicie sesión en ServiceNow como usuario de integración

1. Vuelva a navegar a la página Authorization en ServiceNow.
2. Seleccione el vínculo **que desee** en la esquina superior derecha.
3. Inicie sesión en ServiceNow como el usuario de integración que creó anteriormente a partir de la lista de comprobación de instalación.  
4. Seleccione **permitir** en la página de servicenow que pregunta si el conector Security + Compliance Connector puede conectarse a su cuenta de servicenow.
5. Continúe con los pasos de configuración.

#### <a name="create-a-security-admin-user"></a>Crear un usuario administrador de seguridad

1. Cree un usuario con privilegios de administrador de seguridad en Azure Active Directory. El usuario debe tener el mismo nombre y dirección de correo electrónico que el usuario de integración que ha creado a partir de la lista de comprobación de instalación. Puede quitar el rol de administrador de seguridad una vez que se haya completado el inicio de sesión y la conexión.
2. Inicie sesión en el centro de seguridad de Microsoft 365 como este usuario y siga los pasos de configuración.

### <a name="ip-filtering"></a>Filtrado IP

Si ha habilitado el filtrado IP, es posible que necesite permitir de forma explícita direcciones IP. Consulte [IP address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) para obtener información sobre cómo permitir intervalos de IP en ServiceNow. Vea [intervalos IP de Azure y etiquetas de servicio: nube pública](https://www.microsoft.com/en-us/download/details.aspx?id=56519) para obtener una lista de las direcciones IP que se van a permitir.

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a>La instalación se ha completado, pero no ve los vales y no se puede compartir

Si se han completado los pasos de instalación y configuración, pero no ve las tarjetas de ServiceNow en la Página principal y no puede compartir con ServiceNow desde la puntuación segura de Microsoft, compruebe el estado de la página de aprovisionamiento en https://security.microsoft.com/ticketProvisioning . Seleccione **autorizar** y volver a la Página principal. Deben aparecer las tarjetas.

## <a name="resources"></a>Recursos

- [Administración de vales de ServiceNow en el centro de seguridad](tickets-security-center.md)
