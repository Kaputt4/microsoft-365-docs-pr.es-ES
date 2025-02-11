---
title: Aplicar cifrado mediante etiquetas de confidencialidad
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Configure las etiquetas de confidencialidad para el cifrado que protege los datos con el acceso y uso restringido.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fcd1dd49aa1bf985794d9bb2dd0c270de01e8bc2
ms.sourcegitcommit: b1ed6470645455c2f1fcf467450debc622c40147
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67710552"
---
# <a name="restrict-access-to-content-by-using-sensitivity-labels-to-apply-encryption"></a>Restringir el acceso al contenido mediante el uso de etiquetas de confidencialidad para aplicar el cifrado

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Al crear una etiqueta de confidencialidad, puede restringir el acceso al contenido al que se aplique la etiqueta. Por ejemplo, con las opciones de encriptación de una etiqueta de confidencialidad, se puede proteger el contenido para que:

- Solo los usuarios de su organización puedan abrir un correo electrónico o documentos confidenciales.
- Solo los usuarios del departamento de marketing puedan editar e imprimir documentos o correos electrónicos de anuncios de promociones, mientras que todos los demás usuarios de su organización solo puedan leerlos.
- Los usuarios no puedan reenviar un correo electrónico o copiar información que contenga noticias sobre una reorganización interna.
- La lista de precios actual que se envía a socios comerciales no pueda abrirse tras una fecha especificada.

Cuando se encripta un documento o correo electrónico, el acceso al contenido está restringido, por lo que:

- Se puede desencriptar solo por los usuarios autorizados por la configuración de encriptado de la etiqueta.
- Permanece encriptado independientemente de dónde resida, dentro o fuera de su organización, incluso si cambia el nombre del archivo.
- Se encripta tanto en reposo (por ejemplo, en una cuenta de OneDrive) como y en tránsito (por ejemplo, cuando un correo electrónico viaja a través de Internet).

Por último, como administrador, al configurar una etiqueta de confidencialidad para aplicar el cifrado, puede elegir entre:

- **Asignar permisos ahora** para que determine exactamente los permisos para el contenido con esa etiqueta y los usuarios que los obtendrán.
- **Permitir a los usuarios asignar permisos** al aplicar la etiqueta al contenido. De esta forma, puede permitir a los usuarios de su organización cierta flexibilidad que pueden necesitar para colaborar y llevar a cabo su trabajo.

La configuración de cifrado está disponible cuando se [crea una etiqueta de confidencialidad](create-sensitivity-labels.md) en el Portal de cumplimiento de Microsoft Purview.

> [!NOTE]
> Ahora que se está implementando en versión preliminar, una etiqueta de confidencialidad en Outlook puede aplicar la protección S/MIME en lugar del cifrado y los permisos de Microsoft Azure AD Rights Management. Para obtener más información, vea [Configurar una etiqueta para aplicar la protección S/MIME en Outlook](sensitivity-labels-office-apps.md#configure-a-label-to-apply-smime-protection-in-outlook).

## <a name="understand-how-the-encryption-works"></a>Entender cómo funciona el cifrado

El cifrado usa el servicio Azure Rights Management (Azure RMS) de Azure Information Protection. Esta solución de protección usa directivas de cifrado, identidades y de autorización. Para obtener más información, consulte [¿qué es Azure Rights Management?](/azure/information-protection/what-is-azure-rms) en la documentación de Azure Information Protection. 

Cuando usa esta solución de cifrado, la característica de **superusuario** garantiza que los usuarios y los servicios autorizados siempre puedan leer e inspeccionar los datos que se han cifrado para la organización. Si es necesario, el cifrado puede quitarse o modificarse. Para obtener más información, consulte [configuración de superusuarios para Azure Information Protection y servicios de detección y de recuperación de datos de Azure](/azure/information-protection/configure-super-users).

## <a name="important-prerequisites"></a>Requisitos previos importantes

Para poder usar el cifrado, es posible que tenga que realizar algunas tareas de configuración. Al configurar las opciones de cifrado, no hay ninguna comprobación para validar que se cumplen los requisitos previos.

- Activar la protección de Azure Information Protection
    
    Para que las etiquetas de confidencialidad puedan aplicar el cifrado, el servicio de protección (Azure Rights Management) de Azure Information Protection debe estar activado para su espacio empresarial. En los espacios empresariales más recientes, esta es la configuración predeterminada, pero es posible que tenga que activar el servicio manualmente. Para obtener más información, consulte [Activar el servicio de protección de Azure Information Protection](/azure/information-protection/activate-service).

- Comprobar los requisitos de red
    
    Es posible que deba realizar algunos cambios en sus dispositivos de red, como firewalls. Para obtener más información, consulte [Firewalls y la infraestructura de red](/azure/information-protection/requirements#firewalls-and-network-infrastructure) de la documentación de Azure Information Protection.

- Comprobación de la configuración de Azure AD
    
    Hay algunas configuraciones de Azure Active Directory (Azure AD) que pueden impedir el acceso autorizado al contenido cifrado. Por ejemplo, la configuración de acceso entre inquilinos y las directivas de acceso condicional. Para más información, consulte [Configuración de Azure AD para contenido cifrado](encryption-azure-ad-configuration.md).

- Configurar Exchange para Azure Information Protection
    
    Exchange no tiene que estar configurado para Azure Information Protection antes de que los usuarios puedan aplicar etiquetas en Outlook para cifrar los mensajes de correo. Sin embargo, hasta que Exchange no esté configurado para Azure Information Protection, no obtendrá toda la funcionalidad del uso de la protección de Azure Rights Management con Exchange.
    
    Por ejemplo, los usuarios no pueden ver mensajes de correo electrónico cifrados en teléfonos móviles o con Outlook en la Web, no se pueden indizar mensajes de correo electrónico cifrados para la búsqueda y no puede configurar DLP de Exchange Online para la protección de administración de derechos. 
    
    Para asegurarse de que Exchange puede admitir estos escenarios adicionales:
    
    - Para Exchange Online, consulte las instrucciones de [Exchange Online: configuración de IRM](/azure/information-protection/configure-office365#exchangeonline-irm-configuration).
    - Para Exchange local, debe implementar el [conector RMS y configurar los servidores de Exchange](/azure/information-protection/deploy-rms-connector).

## <a name="how-to-configure-a-label-for-encryption"></a>Cómo configurar una etiqueta para el cifrado

1. Siga las instrucciones generales para [crear o editar una etiqueta de confidencialidad](create-sensitivity-labels.md#create-and-configure-sensitivity-labels) y asegúrese de que **los elementos** están seleccionados para el ámbito de la etiqueta: 
    
    ![Opciones de ámbito de etiqueta de confidencialidad para archivos y correos electrónicos.](../media/filesandemails-scope-options-sensitivity-label.png)

2. A continuación, en la página **Elegir configuración de protección para elementos etiquetados**, asegúrese de seleccionar **Cifrar elementos**
    
    :::image type="content" source="../media/protection-options-sensitivity-label.png" alt-text="Opciones de protección de etiquetas de confidencialidad para los elementos." Lightbox="../media/protection-options-sensitivity-label.png":::

4.  En la página **Cifrado**, seleccione una de las siguientes opciones:
    
    - **Quitar cifrado si el archivo o correo electrónico está cifrado**: al seleccionar esta opción, al aplicar la etiqueta se quitará el cifrado existente, incluso si se aplicó independientemente de una etiqueta de confidencialidad.
        
        Es importante comprender que esta configuración puede dar lugar a una etiqueta de confidencialidad que es posible que los usuarios no puedan aplicar cuando no tengan permisos suficientes para quitar el cifrado existente. Para obtener más información sobre este escenario, vea la sección [¿Qué ocurre con el cifrado existente al aplicar una etiqueta?](#what-happens-to-existing-encryption-when-a-labels-applied)
    
    - **Configurar las opciones de cifrado**: activa el cifrado y hace que la configuración de cifrado sea visible:
        
        :::image type="content" source="../media/encrytion-options-sensitivity-label.png" alt-text="Opciones de etiqueta de confidencialidad para el cifrado. "lightbox="../media/encrytion-options-sensitivity-label.png":::
        
        Las instrucciones para estas opciones de configuración están en la sección [Establecer la configuración de cifrado](#configure-encryption-settings).

### <a name="what-happens-to-existing-encryption-when-a-labels-applied"></a>Qué sucede con el cifrado existente al aplicar una etiqueta

Si se aplica una etiqueta de confidencialidad a contenido sin cifrar, el resultado de las opciones de cifrado que puede seleccionar se explica por sí mismo. Por ejemplo, si no ha seleccionado **Cifrar archivos y mensajes de correo electrónico**, el contenido permanecerá sin cifrar.

Sin embargo, es posible que el contenido ya esté cifrado. Por ejemplo, otro usuario puede haber aplicado:

- Sus propios permisos, que incluyen permisos definidos por el usuario cuando se le solicitan con una etiqueta, permisos personalizados por el cliente de Azure Information Protection y la protección del documento con **acceso restringido** desde una aplicación de Office.
- Una plantilla de Azure Rights Management Protection que cifre el contenido independientemente de una etiqueta. Esta categoría incluye las reglas de flujo de correo que aplican el cifrado mediante la protección de derechos.
- Una etiqueta que aplica el cifrado con los permisos asignados por el administrador.

En la tabla siguiente se identifica lo que ocurre con el cifrado existente cuando se aplica una etiqueta de confidencialidad al contenido:

| | Cifrado: no seleccionado | Cifrado: configurado | Cifrado: quitar |
|:-----|:-----|:-----|:-----|
|**Permisos especificados por un usuario**|Se preserva el cifrado original|Se aplica el cifrado de la nueva etiqueta|Se quita el cifrado original|
|**Plantilla de protección**|Se preserva el cifrado original|Se aplica el cifrado de la nueva etiqueta|Se quita el cifrado original|
|**Etiqueta con permisos definidos por el administator**|Se quita el cifrado original|Se aplica el cifrado de la nueva etiqueta|Se quita el cifrado original|

En los casos en los que se aplica el cifrado de la nueva etiqueta o se elimina el cifrado original, esto solo se produce si el usuario que aplica la etiqueta tiene un derecho de uso o un rol que admite esta acción:

- El [derecho de uso](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) exportar o control total.
- El rol de [emisor de Administración de derechos o propietario de la Administración de derechos](/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner), o bien de [superusuario](/azure/information-protection/configure-super-users).

Si el usuario no tiene uno de estos derechos o roles, la etiqueta no se puede aplicar y, por lo tanto, se preserva el cifrado original. El usuario verá el siguiente mensaje: **No tiene permiso para realizar este cambio en la etiqueta de confidencialidad. Póngase en contacto con el propietario del contenido.**

Por ejemplo, la persona que aplica No reenviar a un mensaje de correo puede reetiquetar el hilo para reemplazar el cifrado o quitarlo, ya que es el propietario de la Administración de derechos del correo electrónico. Pero, con la excepción de superusuarios, los destinatarios de este mensaje de correo electrónico no pueden volver a etiquetarlo porque no tienen los derechos de uso necesarios.

#### <a name="email-attachments-for-encrypted-email-messages"></a>Datos adjuntos de correo electrónico para mensajes de correo electrónico codificados

Cuando un mensaje de correo electrónico se cifre con cualquier método, todos los documentos de Office no cifrados que se adjunten al correo electrónico heredarán automáticamente la misma configuración de cifrado.

Los documentos que ya están cifrados y se agregan como datos adjuntos siempre conservan el cifrado original.

## <a name="configure-encryption-settings"></a>Configurar opciones de cifrado

Cuando seleccione **Establecer la configuración de cifrado**, en la página **Cifrado** para crear o editar una etiqueta de confidencialidad, elija una de las siguientes opciones:

- **Asignar permisos ahora** para que pueda determinar exactamente qué permisos obtienen los distintos usuarios para el contenido que tenga aplicada la etiqueta. Para obtener más información, vea la sección siguiente [Asignar permisos ahora](#assign-permissions-now).
- **Permitir a los usuarios asignar permisos** al aplicar la etiqueta al contenido. De esta forma, puede permitir a los usuarios de su organización cierta flexibilidad que pueden necesitar para colaborar y llevar a cabo su trabajo. Para obtener más información, vea la sección [Permitir a los usuarios asignar permisos](#let-users-assign-permissions) en esta página.

Por ejemplo, si tiene una etiqueta de confidencialidad denominada **Extremadamente confidencial** que se aplicará al contenido más confidencial, es posible que quiera decidir ahora quién obtendrá cierto tipo de permisos para ese contenido.

Por otra parte, si tiene una etiqueta de confidencialidad denominada **Contratos empresariales** y el flujo de trabajo de su organización requiere que sus usuarios colaboren en este contenido con diferentes personas según sea necesario, puede que quiera permitir a los usuarios decidir quién obtiene permisos cuando asignan la etiqueta. Esta flexibilidad aumenta la productividad de los usuarios y reduce las solicitudes de actualización y creación de nuevas etiquetas a los administradores para solucionar escenarios específicos.

Elegir si asignar permisos ahora o permitir a los usuarios asignar permisos:

![Opción para agregar permisos definidos por el usuario o un administrador.](../media/sensitivity-label-user-or-admin-defined-permissions.png)

## <a name="assign-permissions-now"></a>Asignar permisos ahora

Use las siguientes opciones para controlar quién puede tener acceso al correo electrónico o a los documentos a los que se aplica esta etiqueta. Puede:

- **Permitir que el acceso al contenido con la etiqueta expire**, ya sea en una fecha específica o tras un número determinado de días después de aplicar la etiqueta. Después de ese momento, los usuarios no podrán abrir el elemento con la etiqueta. Si especifica una fecha, se activará en la medianoche de esa fecha, en la zona horaria actual. Algunos clientes de correo electrónico pueden no aplicar la expiración y mostrar correos electrónicos una vez pasada dicha fecha, debido a otros mecanismos de almacenamiento en caché.

- **Permitir el acceso sin conexión** nunca, siempre o durante una cantidad específica de días después de aplicar la etiqueta. Use esta opción para equilibrar los requisitos de seguridad que tiene con la capacidad de que los usuarios abran contenido cifrado cuando no tengan conexión a Internet. Si restringe el acceso sin conexión a nunca o a un número de días, cuando se alcance ese umbral, se debe volver a autenticar a los usuarios y se registrará su acceso. Para obtener más información sobre cómo funciona este proceso, consulte la siguiente sección sobre la [licencia de uso de Rights Management](#rights-management-use-license-for-offline-access).

Configuración de control de acceso para contenido cifrado:

![Configuración de permisos definidos por el administrador.](../media/sensitivity-encryption-settings-for-admin-defined-permissions.png)

Recomendaciones para la configuración de expiración y acceso sin conexión:

|Configuración|Valor recomendado|
|-------|----------------|-------------------|
|**El acceso del usuario al contenido expira**|**Nunca** a menos que el contenido tenga un requisito específico de tiempo limitado.|
|**Permitir acceso sin conexión**|Depende de la confidencialidad del contenido:<br /><br />- **Solo durante un número de días** = **7** para datos empresariales confidenciales que podrían causar daños a la empresa si se comparten con personas no autorizadas. Esta recomendación ofrece un compromiso equilibrado entre flexibilidad y seguridad. Entre los ejemplos, se incluyen contratos, informes de seguridad, resúmenes de previsión y datos de cuentas de ventas.<br /><br />- **Nunca** para datos empresariales muy confidenciales que podrían causar daños a la empresa si se compartiesen con personas no autorizadas. Esta recomendación brinda prioridad a la seguridad frente a la flexibilidad y garantiza que, si quita el acceso de uno o varios usuarios al documento, no podrán abrirlo. Algunos ejemplos son la información de empleados y clientes, las contraseñas, el código fuente y los informes financieros anunciados de manera previa. <br /><br />- **Siempre** para contenido menos confidencial en el que no importa si los usuarios pueden seguir abriendo el contenido cifrado durante un máximo de 30 días (o el período de validez de licencia de uso configurado para el inquilino) después de quitar su acceso y haber abierto previamente el contenido cifrado.|

Solo las etiquetas configuradas para asignar permisos ahora admiten valores diferentes para el acceso sin conexión. Las etiquetas que permiten a los usuarios asignar los permisos usan el período de validez de la licencia de uso de Rights Management del inquilino. Por ejemplo, las etiquetas configuradas para No reenviar, Solo cifrar y las que solicitan a los usuarios que especifiquen sus propios permisos. El valor predeterminado de esta configuración es 30 días.

### <a name="rights-management-use-license-for-offline-access"></a>Licencia de uso de administración de derechos para el acceso sin conexión

> [!NOTE]
> Aunque puede configurar las opciones de cifrado para permitir el acceso sin conexión, es posible que algunas aplicaciones no admitan el acceso sin conexión para el contenido cifrado. Por ejemplo, los archivos etiquetados y cifrados en [Power BI Desktop](/power-bi/admin/service-security-sensitivity-label-overview) no se abrirán sin conexión.

Cuando un usuario abre un documento o correo electrónico que está protegido mediante cifrado del servicio de Azure Rights Management, se concede una licencia de uso de Azure Rights Management para el usuario. Esta licencia de uso es un certificado que contiene los derechos de uso del usuario para el documento o correo electrónico, y la clave de cifrado que se usó para cifrar el contenido. La licencia de uso también contiene una fecha de vencimiento (si se ha configurado) y el tiempo durante el que la licencia de uso es válida.

Si no se ha establecido ninguna fecha de expiración, el período predeterminado de validez de licencia de uso para un espacio empresarial es 30 días. Durante la duración de la licencia de uso, el usuario no se vuelve a autenticar o autorizar para ver el contenido. Este proceso permite que el usuario pueda abrir el documento o correo electrónico protegido sin conexión a Internet. Cuando la validez de la licencia de uso expire, la próxima vez que el usuario acceda a un documento o correo electrónico protegido, el usuario debe ser autorizado y autenticarse de nuevo.

Además de volver a hacer la autenticación, se vuelven a evaluar la pertenencia a grupos de usuario y la directiva. Esto significa que los usuarios podrían experimentar resultados diferentes de acceso para el mismo documento o correo electrónico si hay cambios en la configuración del cifrado o en la pertenencia a grupos con respecto al último momento en que se accedió al contenido.

Para obtener información sobre cómo cambiar la configuración de 30 días predeterminada, vea [Licencia de uso de administración de derechos](/azure/information-protection/configure-usage-rights#rights-management-use-license).

### <a name="assign-permissions-to-specific-users-or-groups"></a>Asignar permisos a usuarios o grupos específicos

Puede conceder permisos a usuarios específicos para que solo pueden interactuar con el contenido con la etiqueta:

1. Primero, agregue usuarios o grupos a los que se asignarán permisos para el contenido con la etiqueta.

2. Después, elijaqué permisos obtienen los usuarios para el contenido con la etiqueta.

Asignación de permisos:

![Opciones para asignar permisos a usuarios.](../media/Sensitivity-Assign-permissions-settings.png)

#### <a name="add-users-or-groups"></a>Agregar usuarios o grupos

Al asignar permisos, puede elegir:

- Todos los usuarios de su organización (todos los miembros del espacio empresarial). Esta configuración excluye cuentas de invitado.

- Cualquier usuario autenticado. Asegúrese de comprender las [limitaciones y requisitos](#requirements-and-limitations-for-add-any-authenticated-users) de esta configuración antes de seleccionarla.

- Cualquier usuario específico o grupo de seguridad habilitado para correo electrónico, grupo de distribución o grupo de Microsoft 365 en Azure AD. El grupo de Microsoft 365 puede tener [pertenencia estática o dinámica](/azure/active-directory/users-groups-roles/groups-create-rule). No puede usar un [grupo de distribución dinámico de Exchange](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups) porque este tipo de grupo no está sincronizado con Azure AD. Tampoco puede usar un grupo de seguridad que no esté habilitado para correo electrónico.
    
    Aunque puede especificar grupos que incluyan contactos de correo como método conveniente para conceder acceso a varias personas fuera de la organización, actualmente hay un problema conocido con esta configuración. Para más información, consulte [Contactos de correo en grupos que tienen acceso intermitente a contenido cifrado](/office365/troubleshoot/sensitivity-labels/mail-contacts-lose-access-encrypted-content).

- Cualquier dirección de correo electrónico o dominio. Use esta opción para especificar todos los usuarios de otra organización que usan Azure AD, escribiendo un nombre de dominio de dicha organización. También puede usar esta opción para proveedores de redes sociales si escribe su nombre de dominio, como **gmail.com**, **hotmail.com** o **outlook.com**.

    > [!NOTE]
    > Si especifica un dominio de una organización que usa Azure AD, no puede restringir el acceso a ese dominio específico. En su lugar, todos los dominios comprobados en Azure AD se incluyen automáticamente para el espacio empresarial propietario del nombre de dominio que especifique.

Al elegir todos los usuarios y grupos de su organización o al examina el directorio, los usuarios o grupos deben tener una dirección de correo electrónico.

Se recomienda usar grupos en lugar de usuarios. Esta estrategia mantiene la configuración más sencilla.

##### <a name="requirements-and-limitations-for-add-any-authenticated-users"></a>Requisitos y limitaciones para "Añadir todos los usuarios autenticados"

Esta configuración no impide que los usuarios tengan acceso al contenido cifrado por la etiqueta, a la vez que cifra el contenido y ofrece opciones para restringir la manera en que puede usarse el contenido (permisos) y tener acceso a él (acceso de expiración y sin conexión). Sin embargo, la aplicación que abra el contenido cifrado debe poder admitir la autenticación que se usa. Por este motivo, los proveedores de redes sociales federadas, como Google, y la autenticación de contraseña de una sola vez, solo funcionan para correo electrónico, y solo cuando se usa Exchange Online. Las cuentas de Microsoft se pueden usar con las aplicaciones de Office 365 y el [visor de Azure Information Protection](https://portal.azurerms.com/#/download).

> [!NOTE]
> Considere la posibilidad de usar esta configuración con la [integración de SharePoint y OneDrive con Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview) cuando las etiquetas de confidencialidad estén [habilitadas para los archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

Algunos escenarios comunes para la configuración de todos los usuarios autenticados:

- No le importa quién vea el contenido, pero desea restringir cómo se usa. Por ejemplo, no quiere que el contenido se pueda modificar, copiar o imprimir.
- No es necesario restringir el acceso al contenido, pero quiere confirmar quién lo abre.
- Tiene un requisito para que el contenido se cifre en reposo y en tránsito, pero no se requieren controles de acceso.

#### <a name="choose-permissions"></a>Elegir permisos

Al elegir qué permisos permitir para los usuarios o grupos, puede seleccionar entre:

- Un [nivel de permiso predefinido](/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels) con un grupo de derechos preestablecido, como coautor o revisor.
- Permisos personalizados, donde puede elegir uno o más derechos de uso.

Para obtener más información sobre cómo seleccionar los permisos adecuados, consulte [derechos y descripciones de uso](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions).  

![Opciones para elegir permisos predefinidos o personalizados.](../media/Sensitivity-Choose-permissions-settings.png)

Tenga en cuenta que la misma etiqueta puede conceder diferentes permisos a diferentes usuarios. Por ejemplo, una sola etiqueta puede asignar a algunos usuarios como revisor y a otros usuarios como coautor, como se muestra en la siguiente captura.

Para ello, agregue usuarios o grupos, asigne sus permisos y guarde las opciones de configuración. Luego repita estos pasos, agregue usuarios y asigne permisos para guardar la configuración de nuevo. Puede repetir esta configuración tantas veces como sea necesario para definir permisos diferentes para distintos usuarios.

![Usuarios distintos con permisos diferentes.](../media/Sensitivity-Multiple-users-permissions.png)

#### <a name="rights-management-issuer-user-applying-the-sensitivity-label-always-has-full-control"></a>El emisor de administración de derechos (el usuario que aplica la etiqueta de confidencialidad) siempre tiene control total

El cifrado para una etiqueta de confidencialidad usa el servicio de Azure Rights Management de Azure Information Protection. Cuando un usuario aplica una etiqueta de confidencialidad para proteger un documento o correo electrónico mediante el cifrado, ese usuario pasa a ser el emisor de la Administración de derechos para ese contenido.

El emisor de administración de derechos siempre obtiene permisos de control total para el documento o correo electrónico y además:

- Si la configuración de cifrado incluye una fecha de expiración, el emisor de administración de derechos puede abrir y editar el documento o correo electrónico después de esa fecha.
- El emisor de administración de derechos siempre puede acceder al documento o correo electrónico sin conexión.
- El emisor de administración de derechos puede seguir abriendo un documento después de que se revoque.

Para obtener más información, vea [Emisor de administración de derechos y propietario de administración de derechos](/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner).

### <a name="double-key-encryption"></a>Cifrado de claves doble

> [!NOTE]
> Esta característica solo es compatible actualmente con el cliente de etiquetado unificado de Azure Information Protection.

Seleccione esta opción solo después de configurar el servicio Cifrado de doble clave. Necesitará usar el cifrado de doble clave para los archivos que tengan aplicada esta etiqueta. Una vez configurada y guardada, no podrá editar la etiqueta.

Para obtener más información, ver los requisitos previos y las instrucciones de configuración, consulte el [Cifrado de doble clave (DKE)](double-key-encryption.md).

## <a name="let-users-assign-permissions"></a>Permitir a los usuarios asignar permisos

> [!IMPORTANT]
> No todos los clientes con etiquetado admiten todas las opciones que permiten a los usuarios asignar sus propios permisos. Use esta sección para obtener más información.

Puede usar las siguientes opciones para que los usuarios puedan asignar permisos cuando aplican manualmente una etiqueta de confidencialidad al contenido:

- En Outlook, un usuario puede seleccionar restricciones equivalentes a la opción [No reenviar](/azure/information-protection/configure-usage-rights#do-not-forward-option-for-emails) o [Solo cifrar](/azure/information-protection/configure-usage-rights#encrypt-only-option-for-emails)para los destinatarios seleccionados.
    
    La opción No reenviar es compatible con todos los clientes de correo electrónico que admiten etiquetas de confidencialidad. Sin embargo, aplicar la opción **Solo cifrar** con una etiqueta de confidencialidad es una versión reciente que solo se admite mediante etiquetas integradas y no con el cliente de etiquetas unificado de Azure Information Protection. Para los clientes de correo electrónico que no admiten esta funcionalidad, la etiqueta no estará visible.
    
    Para comprobar las versiones mínimas de las aplicaciones de Outlook que usan etiquetas integradas para admitir la aplicación de la opción Solo cifrar con una etiqueta de confidencialidad, use la [tabla de funcionalidades para Outlook](sensitivity-labels-office-apps.md#sensitivity-label-capabilities-in-outlook) y la fila **Permitir que los usuarios asignen permisos: solo cifrar**.

- En Word, PowerPoint y Excel, se pide al usuario que seleccione sus propios permisos para organizaciones, usuarios o grupos específicos.

    Esta opción es compatible con el cliente de etiquetado unificado de Azure Information Protection y por algunas aplicaciones que usan etiquetado integrado. Para las aplicaciones que no admiten esta función, la etiqueta no estará visible para los usuarios, o bien la etiqueta está visible para dar coherencia pero no se puede aplicar con un mensaje de explicación a los usuarios.
    
    Para comprobar qué aplicaciones que usan etiquetas integradas admiten esta opción, use la [tabla de funciones para Word, Excel y PowerPoint](sensitivity-labels-office-apps.md#sensitivity-label-capabilities-in-word-excel-and-powerpoint) y la fila **Permitir que los usuarios asignen permisos**.

Cuando se admitan las opciones, use la tabla siguiente para identificar cuándo los usuarios ven la etiqueta de confidencialidad:

|Configuración |Etiqueta visible en Outlook|Etiqueta visible en Word, Excel y PowerPoint|
|:-----|:-----|:-----|:-----|
|**En Outlook, un usuario puede aplicar restricciones con la opción No reenviar o Solo cifrar**|Sí |No |
|**En Word, PowerPoint y Excel, pida a los usuarios que especifiquen los permisos**|No |Sí|

Cuando ambas opciones están seleccionadas, la etiqueta es visible tanto en Outlook como en Word, Excel y PowerPoint.

Una etiqueta de confidencialidad que permite a los usuarios asignar permisos se debe aplicar al contenido manualmente. No se puede aplicar automáticamente o usar como etiqueta recomendada.

Configurar los permisos asignados por el usuario:

![Configuración de cifrado para los permisos definidos por el usuario.](../media/sensitivity-encryption-settings-for-user-defined-permissions.png)

### <a name="outlook-restrictions"></a>Restricciones de Outlook

En Outlook, cuando un usuario aplica una etiqueta de confidencialidad que le permite asignar permisos a un mensaje, puede elegir la opción **No reenviar** o **Solo cifrar**. El usuario verá el nombre y la descripción de la etiqueta en la parte superior del mensaje, lo que indica que se está protegiendo el contenido. A diferencia de Word, PowerPoint y Excel (vea la [siguiente sección](#word-powerpoint-and-excel-permissions)), no se pide a los usuarios que seleccionen permisos específicos.

![Etiqueta de confidencialidad aplicada a mensajes en Outlook.](../media/sensitivity-label-outlook-protection-applied.png)

Cuando cualquiera de estas opciones se aplica a un correo electrónico, este se cifra y los destinatarios tienen que autenticarse. Luego, el destinatario obtiene automáticamente derechos de uso restringido:

- **No reenviar**: los destinatarios no podrán reenviar el correo electrónico, imprimirlo ni copiarlo. Por ejemplo, en el cliente de Outlook, el botón Reenviar y las opciones de menú Guardar como e Imprimir no están disponibles, y no se pueden agregar o cambiar destinatarios en los cuadros Para, CC o CCO.
    
    Para obtener más información sobre cómo funciona esta opción, consulte [Opción No reenviar para correos electrónicos](/azure/information-protection/configure-usage-rights#do-not-forward-option-for-emails).

- **Solo cifrar**: los destinatarios tienen todos los derechos de uso excepto Guardar como, Exportar y Control total. Esta combinación de derechos de uso significa que los destinatarios no tienen restricciones, a excepción de que no pueden quitar la protección. Por ejemplo, un destinatario puede copiar del correo electrónico, imprimirlo y reenviarlo.
    
    Para obtener más información sobre cómo funciona esta opción, consulte [Opción Solo cifrar para correos electrónicos](/azure/information-protection/configure-usage-rights#encrypt-only-option-for-emails).

Los documentos de Office sin cifrar asociados al correo electrónico heredan automáticamente las mismas restricciones. Para No reenviar, los derechos de uso que se aplican a estos documentos son Editar contenido, Editar; Guardar; Ver, Abrir, Leer y Permitir macros. Si el usuario quiere derechos de uso distintos para los datos adjuntos o el archivo adjunto no es un documento de Office compatible con esta protección heredada, debe cifrar el archivo antes de adjuntarlo al correo electrónico.

### <a name="word-powerpoint-and-excel-permissions"></a>Permisos de Word, PowerPoint y Excel

En Word, PowerPoint y Excel, cuando un usuario aplica una etiqueta de confidencialidad que le permite asignar permisos a un documento, se le pide al usuario que especifique su elección de usuarios y permisos para el cifrado.

Por ejemplo, con el cliente de etiquetas unificado de Azure Information Protection, a menos que la [co-autoría esté habilitada](sensitivity-labels-coauthoring.md), los usuarios pueden:

- Seleccionar un nivel de permisos, como Visor (que asigna el permiso de solo vista) o Co-autoría (que asigna los permisos de vista, edición, copia e impresión). 
- Seleccionar organizaciones, usuarios o grupos. Esto puede incluir usuarios dentro o fuera de su organización.
- Establecer una fecha de expiración, después de la que los usuarios seleccionados no pueden tener acceso al contenido. Para obtener más información, vea la sección anterior [Licencia de uso de Rights Management para el acceso sin conexión](#rights-management-use-license-for-offline-access).

![Opciones de protección para el usuario con permisos personalizados.](../media/sensitivity-aip-custom-permissions-dialog.png)

Para el etiquetado integrado y para el cliente de etiquetado unificado de Azure Information Protection cuando la [coautoría está habilitada](sensitivity-labels-coauthoring.md), los usuarios ven el mismo cuadro de diálogo que verían si seleccionaran lo siguiente:

- Windows: pestaña **Archivo** > **Información** > **Proteger documento** > **Restringir accesso** > **Accesso restringido**

- MacOS: pestaña **Revisar** > **Protección** > **Permisos** > **Acceso restringido**

> [!TIP]
> Si los usuarios estaban familiarizados con la configuración de permisos personalizados con el cliente de etiquetado unificado de Azure Information Protection antes de [habilitar la co-autoría](sensitivity-labels-coauthoring.md), puede resultar útil revisar la asignación de niveles de permisos a derechos de uso individuales: [Derechos incluidos en los niveles de permisos](/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels).

#### <a name="support-for-organization-wide-custom-permissions"></a>Compatibilidad con permisos personalizados para toda la organización

Ahora, implementándose en versión preliminar para el etiquetado integrado en Windows, los usuarios pueden especificar un nombre de dominio que se aplicará a todos los usuarios de una organización propietaria del dominio y que se encuentra en Azure Active Directory. Esta funcionalidad proporciona [paridad con el cliente de etiquetado unificado Azure Information Protection](sensitivity-labels-aip.md#feature-parity-for-built-in-labeling-and-the-aip-add-in-for-office-apps):

![Cuadro de diálogo actualizado para admitir permisos personalizados para toda la organización.](../media/org-wide-custom-permissions-dialog.png)

Por ejemplo, un usuario escribe "@contoso.com" (o "contoso.com") y concede acceso de lectura. Dado que Contoso Corporation posee el dominio contoso.com, se concederá acceso de lectura a todos los usuarios de ese dominio y a todos los demás dominios de los que es propietaria la organización en Azure Active Directory.

Es importante informar a los usuarios de que el acceso no está restringido solo a los usuarios del dominio especificado. Por ejemplo, "@ventas.contoso.com" no restringiría el acceso a los usuarios solo en el subdominio de ventas, sino que también concedería acceso a los usuarios del dominio marketing.contoso.com e incluso a los usuarios con un espacio de nombres separado en el mismo inquilino de Azure Active Directory.

## <a name="example-configurations-for-the-encryption-settings"></a>Configuraciones de ejemplo para la configuración de cifrado

Para cada ejemplo que se muestra a continuación, lleve a cabo la configuración desde la página **Cifrado**, cuando **Establecer la configuración de cifrado** esté seleccionada:

![Opción de aplicar cifrado en el Asistente de etiquetas de confidencialidad.](../media/apply-encryption-option.png)

### <a name="example-1-label-that-applies-do-not-forward-to-send-an-encrypted-email-to-a-gmail-account"></a>Ejemplo 1: etiqueta que aplica No reenviar para enviar un correo electrónico cifrado a una cuenta de Gmail

Esta etiqueta solo se muestra en Outlook y Outlook en la Web y debe usar Exchange Online. Pida a los usuarios que seleccionen esta etiqueta cuando necesiten enviar un correo electrónico cifrado a las personas que usen una cuenta de Gmail (o cualquier otra cuenta de correo electrónico fuera de su organización).

Los usuarios escriben la dirección de correo electrónico de Gmail en el cuadro **Para**.  Después, seleccionan la etiqueta y la opción No reenviar se agrega automáticamente al correo electrónico. El resultado es que los destinatarios no pueden reenviar el correo electrónico o imprimirlo, copiar desde él o guardar el correo electrónico fuera de su buzón con la opción **Guardar como**.

1. En la página **Cifrado**: para **¿Quiere asignar permisos ahora o permitir que los usuarios decidan?** seleccione **Permita a los usuarios asignar permisos al aplicar la etiqueta**.

2. Marque la casilla de verificación: **En Outlook, aplicar restricciones equivalentes a la opción No reenviar**.

3. Si está seleccionada, desactive la casilla: **En Word, PowerPoint y Excel, pedir a los usuarios que especifiquen los permisos**.

4. Seleccione **Siguiente** y complete la configuración.

### <a name="example-2-label-that-restricts-read-only-permission-to-all-users-in-another-organization"></a>Ejemplo 2: etiqueta que restringe los permisos de solo lectura a todos los usuarios de otra organización

Esta etiqueta es adecuada para compartir documentos muy confidenciales como solo lectura, y los documentos siempre requieren una conexión a Internet para verlos.

Esta etiqueta no es adecuada para los correos electrónicos.

1. En la página **Cifrado**: para **¿Quiere asignar permisos ahora o permitir que los usuarios decidan?** seleccione **Asignar permisos ahora**.

2. Para **permitir el acceso sin conexión**, seleccione **nunca**.

3. Seleccione **asignar permisos**.

4. En el panel **Asignar permisos**, seleccione **Agregar direcciones de correo electrónico o dominios específicos**.

5. En el cuadro de texto, escriba el nombre de un dominio de la otra organización, por ejemplo, **fabrikam.com**. Luego seleccione **Agregar**.

6. Seleccione **Elegir permisos**.

7. En el panel **Elegir permisos**, seleccione el cuadro de lista desplegable, seleccione **Visor** y, después, **Guardar**.

8. De nuevo, en el panel **asignar permisos**, seleccione **guardar**.

9. En la página **Cifrado,** seleccione **Siguiente** y complete la configuración.

### <a name="example-3-add-external-users-to-an-existing-label-that-encrypts-content"></a>Ejemplo 3: agregar usuarios externos a una etiqueta existente que cifra el contenido

Los nuevos usuarios que agregue serán capaces de abrir documentos y mensajes de correo electrónico que ya estén protegidos con esta etiqueta. Los permisos concedidos a estos usuarios pueden ser distintos de los permisos que tienen los usuarios existentes.

1. En la página **Cifrado**: para **¿Quiere asignar permisos ahora o permitir que los usuarios decidan?** asegúrese de que la opción **Asignar permisos ahora** está seleccionada.

2. Seleccione **asignar permisos**.

3. En el panel **Asignar permisos**, seleccione **Agregar direcciones de correo electrónico o dominios específicos**.

4. En el cuadro de texto, escriba la dirección de correo electrónico del primer usuario (o grupo) que desea agregar y seleccione **agregar**.

5. Seleccione **Elegir permisos**.

6. En el panel **Elegir permisos**, seleccione los permisos para este usuario (o grupo) y seleccione **Guardar**.

7. De nuevo, en el panel **Asignar permisos**, repita los pasos del 3 al 6 para cada usuario (o grupo) que quiera agregar a esta etiqueta. Luego haga click en **Guardar**

8. En la página **Cifrado,** seleccione **Siguiente** y complete la configuración.

### <a name="example-4-label-that-encrypts-content-but-doesnt-restrict-who-can-access-it"></a>Ejemplo 4: etiqueta que cifra el contenido, pero que no restringe quién puede tener acceso a él.

Esta configuración tiene la ventaja de no tener que especificar usuarios, grupos o dominios para cifrar un correo electrónico o un documento. El contenido seguirá estando cifrado y aún podrá especificar derechos de uso, una fecha de expiración y acceso sin conexión.

Use esta configuración solo cuando no necesite restringir quién puede abrir el documento o correo electrónico protegido. Consulte [más información acerca de esta configuración.](#requirements-and-limitations-for-add-any-authenticated-users).

1. En la página **Cifrado**: para **¿Quiere asignar permisos ahora o permitir que los usuarios decidan?** asegúrese de que la opción **Asignar permisos ahora** está seleccionada.

2. Configure las opciones de **el acceso de usuario al contenido expira** y **permitir el acceso sin conexión** según sea necesario.

3. Seleccione **asignar permisos**.

4. En el panel **asignar permisos**, seleccione **agregar cualquiera de los usuarios autenticados**.

    Para **Usuarios y grupos**, verá que **Usuarios autenticados** se agrega automáticamente. No se puede cambiar este valor, solo eliminarlo, lo que cancela la selección de **agregar cualquiera de los usuarios autenticados**.

5. Seleccione **Elegir permisos**.

6. En el panel **Elegir permisos**, seleccione el cuadro de lista desplegable, elija los permisos que quiera y seleccione **Guardar**.

7. De nuevo, en el panel **asignar permisos**, seleccione **guardar**.

8. En la página **Cifrado,** seleccione **Siguiente** y complete la configuración.

## <a name="considerations-for-encrypted-content"></a>Consideraciones sobre el contenido cifrado

Cifrar los documentos y mensajes de correo electrónico más confidenciales le ayuda a asegurarse de que solo los usuarios autorizados puedan acceder a estos datos. Sin embargo, hay algunas consideraciones que debe tener en cuenta:

- Si su organización no ha [habilitado las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md):

  - Search, eDiscovery y Delve no funcionarán en archivos cifrados.
  - Las directivas DLP funcionan para los metadatos de estos archivos cifrados (incluida la información de la etiqueta de retención), pero no el contenido de estos archivos (como números de tarjeta de crédito en los archivos).
  - Los usuarios no pueden abrir archivos cifrados con Office en la web. Cuando las etiquetas de confidencialidad de los archivos de Office en SharePoint y OneDrive están habilitadas, los usuarios pueden usar Office en la Web para abrir archivos cifrados, con algunas limitaciones [](sensitivity-labels-sharepoint-onedrive-files.md#limitations)entre las que se incluyen el cifrado que se ha aplicado con una clave local (conocido como "mantenga su propia clave" o HYOK, por sus siglas en inglés), [el cifrado de doble clave](#double-key-encryption) y el cifrado que se ha aplicado independientemente de una etiqueta de confidencialidad.

- Si comparte documentos cifrados con personas ajenas a su organización, es posible que tenga que crear cuentas de invitado y modificar las directivas de acceso condicional. Para obtener más información, vea [Sharing encrypted documents with external users](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content).

- Cuando los usuarios autorizados abren documentos cifrados en sus aplicaciones de Office, ven el nombre y descripción de la etiqueta en una barra de mensajes amarilla en la parte superior de la aplicación. Cuando los permisos de cifrado se extienden a personas fuera de la organización, revise detenidamente los nombres y descripciones de las etiquetas que estarán visibles en esta barra de mensajes cuando se abra el documento.

- Para que varios usuarios editen un archivo cifrado al mismo tiempo, todos deben usar Office en la Web o se debe haber [habilitado la coautoría de archivos cifrados con etiquetas de confidencialidad](sensitivity-labels-coauthoring.md) y todos los usuarios deben tener [aplicaciones de Office compatibles con esta característica](sensitivity-labels-coauthoring.md#prerequisites). Si este no es el caso y el archivo ya está abierto:
    
  - En las aplicaciones de Office (Windows, Mac, Android y iOS), los usuarios verán un mensaje de **archivo en uso** con el nombre de la persona que ha desprotegido el archivo. Podrán ver una copia de solo lectura, guardar y editar una copia del archivo, y recibir una notificación cuando el archivo esté disponible.
  - En Office para la Web, los usuarios ven un mensaje de error que indica que no pueden editar el documento con otras personas. A continuación, pueden seleccionar **Abrir en Vista de lectura**.

- La funcionalidad [Autoguardado](https://support.office.com/article/what-is-autosave-6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) en las aplicaciones de Office está deshabilitada para los archivos cifrados si no ha [habilitado la coautoría para archivos cifrados con etiquetas de confidencialidad](sensitivity-labels-coauthoring.md). Los usuarios verán un mensaje en el que se indica que el archivo tiene permisos restringidos que deben quitarse para que se pueda activar el autoguardado.

- Office para Windows admite etiquetas que aplican cifrado cuando los usuarios no están conectados a Internet. No obstante, para las demás plataformas (macOS, iOS, Android), los usuarios deben estar en línea para aplicar estas etiquetas en las aplicaciones de Office. El cliente de etiquetado unificado Azure Information Protection también debe estar en línea para aplicar estas etiquetas en Explorador de archivos y PowerShell. No es necesario que los usuarios estén en línea para abrir contenido cifrado. Para obtener más información sobre el acceso sin conexión, consulte la sección [Licencia de uso de Rights Management para el acceso sin conexión ](#rights-management-use-license-for-offline-access).

- Los archivos cifrados pueden tardar más en abrirse en las aplicaciones de Office (Windows, Mac, Android y iOS).

- Si se agrega una etiqueta que aplica el cifrado a través de una aplicación de Office, cuando el documento está [extraído en SharePoint](https://support.microsoft.com/office/check-out-check-in-or-discard-changes-to-files-in-a-library-7e2c12a9-a874-4393-9511-1378a700f6de) y el usuario descarta la desprotección, el documento permanece etiquetado y cifrado.

- A menos que haya [habilitado la coautoría de archivos cifrados con etiquetas de confidencialidad](sensitivity-labels-coauthoring.md), las siguientes acciones para archivos cifrados no son compatibles con aplicaciones de Office (Windows, Mac, Android e iOS) y los usuarios ven un mensaje de error que indica que algo salió mal. Sin embargo, se puede usar la funcionalidad de SharePoint como alternativa:

  - Ver, restaurar y guardar copias de versiones anteriores. Como alternativa, los usuarios pueden realizar estas acciones con Office en la web cuando [permitir y configurar el control de versiones para una lista o biblioteca](https://support.office.com/article/enable-and-configure-versioning-for-a-list-or-library-1555d642-23ee-446a-990a-bcab618c7a37).
  - Cambie el nombre o la ubicación de los archivos. Como alternativa, los usuarios pueden [renombre un archivo, carpeta o vínculo en una biblioteca de documentos](https://support.microsoft.com/office/rename-a-file-folder-or-link-in-a-document-library-bc493c1a-921f-4bc1-a7f6-985ce11bb185) en SharePoint.

Para disfrutar de la mejor experiencia de colaboración para los archivos que se cifran con una etiqueta de confidencialidad, le recomendamos que use [etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md) y Office para la Web.



## <a name="next-steps"></a>Pasos siguientes

¿Necesita compartir los documentos etiquetados y cifrados con personas fuera de su organización?  Consulte [Compartir documentos cifrados con usuarios externos](sensitivity-labels-office-apps.md#sharing-encrypted-documents-with-external-users).
