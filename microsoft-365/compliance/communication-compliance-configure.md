---
title: Introducción al cumplimiento de las comunicaciones
description: Configure directivas de cumplimiento de comunicaciones para configurar las comunicaciones de usuario para su revisión.
keywords: Microsoft 365, Microsoft Purview, cumplimiento, cumplimiento de comunicaciones
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 8030a842f36f30fdc267a81e4736abdf8f4328f5
ms.sourcegitcommit: 1734c95ce72d9c8af695cb4b49b1e40d921a1fee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2022
ms.locfileid: "66685907"
---
# <a name="get-started-with-communication-compliance"></a>Introducción al cumplimiento de las comunicaciones

Use directivas de cumplimiento de comunicaciones para identificar las comunicaciones de los usuarios para que las examinen los revisores internos o externos. Para obtener más información sobre cómo las directivas de cumplimiento de comunicaciones pueden ayudarle a detectar comunicaciones en su organización, consulte [Directivas de cumplimiento de comunicaciones](/microsoft-365/compliance/communication-compliance-policies). Si desea revisar cómo Contoso configuró rápidamente una directiva de cumplimiento de comunicaciones para detectar contenido inadecuado en las comunicaciones de Microsoft Teams, Exchange Online y Yammer, consulte este [caso práctico](/microsoft-365/compliance/communication-compliance-case-study).

## <a name="subscriptions-and-licensing"></a>Suscripciones y licencias

Antes de empezar a trabajar con el cumplimiento de comunicaciones, debe confirmar su [suscripción a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) y cualquier complemento. Para acceder y usar el cumplimiento de comunicaciones, su organización debe tener una de las siguientes suscripciones o complementos:

- suscripción Microsoft 365 E5/A5/F5/G5 (versión de pago o de prueba)
- suscripción Microsoft 365 E3/A3/F3/G5 + el complemento de cumplimiento Microsoft 365 E5/A5/F5/G5
- suscripción Microsoft 365 E3/A3/F3/G5 + el complemento Microsoft 365 E5/A5/F5/G5 Insider Risk Management
- Office 365 Enterprise suscripción A5 (versión de pago o de prueba)
- Office 365 A5 suscripción (versión de pago o de prueba)
- Office 365 Enterprise suscripción A3 + el complemento de Cumplimiento avanzado de Office 365 (ya no está disponible para nuevas suscripciones, consulte la nota)

A los usuarios incluidos en las directivas de cumplimiento de comunicaciones se les debe asignar una de las licencias anteriores. Para obtener más información sobre las suscripciones y las licencias, consulte [Guía de Microsoft 365 para el cumplimiento de & de seguridad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-compliance).

> [!IMPORTANT]
> El cumplimiento de comunicaciones está disponible actualmente en los inquilinos hospedados en regiones geográficas y países compatibles con las dependencias del servicio de Azure. Para comprobar que el cumplimiento de comunicaciones es compatible con su organización, consulte [Disponibilidad de dependencias de Azure por país o región](/troubleshoot/azure/general/dependency-availability-by-country).

Si no tiene un plan E5 Office 365 Enterprise existente y quiere probar el cumplimiento de la comunicación, puede [agregar Microsoft 365](/office365/admin/try-or-buy-microsoft-365) a su suscripción existente o [registrarse para obtener una prueba](https://www.microsoft.com/microsoft-365/enterprise) de Office 365 Enterprise E5.

> [!NOTE]
> Cumplimiento avanzado de Office 365 ya no se vende como una suscripción independiente. Cuando expiren las suscripciones actuales, los clientes deben realizar la transición a una de las suscripciones anteriores, que contienen las mismas características de cumplimiento o adicionales.

## <a name="recommended-actions"></a>Acciones recomendadas

Las acciones recomendadas pueden ayudar a su organización a empezar a trabajar con las funcionalidades de cumplimiento de comunicaciones y sacar el máximo partido de las directivas existentes. Incluidas en la página **Directivas** , las acciones recomendadas proporcionan información detallada y resumen los tipos de información confidencial y las actividades de contenido inadecuado en las comunicaciones de su organización. Las conclusiones son compatibles con la [clasificación de datos](/microsoft-365/compliance/data-classification-overview) y la aplicación de etiquetas de confidencialidad, etiquetas de retención y clasificación de tipos de información confidencial. Estas conclusiones no incluyen ninguna información de identificación personal (PII) para los usuarios de su organización.

![Acciones recomendadas de cumplimiento de comunicaciones.](../media/communication-compliance-recommended-actions.png)

La actividad en los mensajes que contienen contenido inadecuado se agrega mediante el [tipo de clasificador](/microsoft-365/compliance/communication-compliance-policies#classifiers) de las directivas existentes que usan la plantilla de contenido inapropiada o las directivas personalizadas que usan clasificadores para contenido inadecuado. Investigue las alertas de estos mensajes en el panel de alertas de las directivas.

La actividad que implica [tipos de información confidencial](/microsoft-365/compliance/communication-compliance-policies#sensitive-information-types) se detecta en los mensajes cubiertos en las directivas existentes y en los mensajes que no están cubiertos por las directivas existentes. Las conclusiones se agregan para todos los tipos de información confidencial, incluidos los que su organización no ha definido previamente en una directiva de cumplimiento de comunicaciones existente. Use esta información para crear una nueva directiva de cumplimiento de comunicaciones o para actualizar las directivas existentes.

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a>Paso 1 (obligatorio): Habilitación de permisos para el cumplimiento de comunicaciones

> [!IMPORTANT]
> Después de configurar los grupos de roles, los permisos del grupo de roles pueden tardar hasta 30 minutos en aplicarse a los usuarios asignados en toda la organización.

Hay seis grupos de roles que se usan para configurar los permisos iniciales para administrar las características de cumplimiento de comunicaciones. Para que **el cumplimiento de la comunicación** esté disponible como una opción de menú en portal de cumplimiento Microsoft Purview y para continuar con estos pasos de configuración, debe estar asignado a uno de los siguientes roles o grupos de roles:

- Rol [*de administrador global*](/azure/active-directory/roles/permissions-reference#global-administrator) de Azure Active Directory
- Rol [*administrador de cumplimiento de*](/azure/active-directory/roles/permissions-reference#compliance-administrator) Azure Active Directory
- portal de cumplimiento Microsoft Purview grupo [*de roles De administración de la organización*](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)
- portal de cumplimiento Microsoft Purview grupo de roles [*administrador de cumplimiento*](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)
- *Grupo de roles de cumplimiento de comunicaciones*
- *Grupo de roles de Administración cumplimiento de comunicaciones*

Los miembros de los roles siguientes tienen los mismos permisos de solución incluidos en el grupo de roles *De cumplimiento de comunicaciones Administración*:

- *Administrador global* de Azure Active Directory
- *Administrador de cumplimiento de* Azure Active Directory
- administración de la *organización* portal de cumplimiento Microsoft Purview
- *Administrador de cumplimiento de* portal de cumplimiento Microsoft Purview

> [!IMPORTANT]
> Asegúrese de que siempre tiene al menos un usuario en los grupos de roles *Cumplimiento de comunicaciones* o *Cumplimiento de comunicaciones Administración* (según la opción que elija) para que la configuración de cumplimiento de comunicaciones no entre en un escenario de "administrador cero" si determinados usuarios abandonan la organización.

En función de cómo quiera administrar las directivas y alertas de cumplimiento de comunicaciones, deberá asignar usuarios a grupos de roles específicos para administrar diferentes conjuntos de características de cumplimiento de comunicaciones. Tiene la opción de asignar usuarios con diferentes responsabilidades de cumplimiento a grupos de roles específicos para administrar diferentes áreas de características de cumplimiento de comunicaciones. O bien, puede decidir asignar todas las cuentas de usuario para administradores, analistas, investigadores y visores designados al grupo de roles *cumplimiento de comunicaciones* . Use un único grupo de roles o varios grupos de roles para adaptarse mejor a los requisitos de administración de cumplimiento.

Elija entre estas opciones de grupo de roles de solución al configurar y administrar el cumplimiento de las comunicaciones:

| Función | Permisos de funciones |
|:-----|:-----------------|
| **Cumplimiento de comunicaciones** | Use este grupo de roles para administrar el cumplimiento de las comunicaciones de su organización en un solo grupo. Al agregar todas las cuentas de usuario para administradores, analistas, investigadores y visores designados, puede configurar los permisos de cumplimiento de comunicaciones en un solo grupo. Este grupo de roles contiene todos los roles de permiso de cumplimiento de comunicaciones. Esta configuración es la manera más fácil de empezar a trabajar rápidamente con el cumplimiento de las comunicaciones y es una buena opción para las organizaciones que no necesitan permisos independientes definidos para grupos de usuarios independientes. Los usuarios que crean directivas como administrador de cumplimiento de comunicaciones deben tener su buzón hospedado en Exchange Online.|
| **Administrador de cumplimiento de comunicaciones** | Use este grupo de roles para configurar inicialmente el cumplimiento de comunicaciones y, posteriormente, para separar a los administradores de cumplimiento de comunicaciones en un grupo definido. Los usuarios asignados a este grupo de roles pueden crear, leer, actualizar y eliminar directivas de cumplimiento de comunicaciones, configuración global y asignaciones de grupos de roles. Los usuarios asignados a este grupo de roles no pueden ver alertas de mensajes. Los usuarios que crean directivas como administrador de cumplimiento de comunicaciones deben tener su buzón hospedado en Exchange Online.|
| **Analista de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que actuarán como analistas de cumplimiento de comunicaciones. Los usuarios asignados a este grupo de roles pueden ver las directivas donde se asignan como revisores, ver los metadatos del mensaje (no el contenido del mensaje), escalar a revisores adicionales o enviar notificaciones a los usuarios. Los analistas no pueden resolver las alertas pendientes. |
| **Investigador de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que actuarán como investigadores de cumplimiento de comunicaciones. Los usuarios asignados a este grupo de roles pueden ver los metadatos y el contenido del mensaje, escalar a revisores adicionales, escalar a un caso de eDiscovery (Premium), enviar notificaciones a los usuarios y resolver la alerta. |
| **Visor de cumplimiento de comunicaciones** | Use este grupo para asignar permisos a los usuarios que administrarán los informes de comunicación. Los usuarios asignados a este grupo de roles pueden acceder a todos los widgets de informes en la página principal de cumplimiento de comunicaciones y pueden ver todos los informes de cumplimiento de comunicaciones. |

### <a name="option-1-assign-all-compliance-users-to-the-communication-compliance-role-group"></a>Opción 1: Asignar todos los usuarios de cumplimiento al grupo de roles De cumplimiento de comunicaciones

1. [https://compliance.microsoft.com/permissions](https://compliance.microsoft.com/permissions) Inicie sesión con las credenciales de una cuenta de administrador en su organización de Microsoft 365.

2. En el Centro de cumplimiento de seguridad &amp; , vaya a **Permisos**. Seleccione el vínculo para ver y administrar roles en Office 365.

3. Seleccione el grupo *de roles Cumplimiento de comunicación* y, a continuación, seleccione **Editar grupo de roles**.

4. Seleccione **Elegir miembros** en el panel de navegación izquierdo y, a continuación, seleccione **Editar**.

5. Seleccione **Agregar** y, a continuación, active la casilla para todos los usuarios que quiera agregar al grupo de roles *Cumplimiento de comunicación* .

6. Seleccione **Agregar** y, después, **Listo**.

7. Seleccione **Guardar** para agregar los usuarios al grupo de roles. Seleccione **Cerrar** para completar los pasos.

### <a name="option-2-assign-users-to-specific-communication-compliance-role-groups"></a>Opción 2: Asignar usuarios a grupos de roles de cumplimiento de comunicaciones específicos

Use esta opción para asignar usuarios a grupos de roles específicos para segmentar el acceso y las responsabilidades de cumplimiento de la comunicación entre los distintos usuarios de la organización.

1. Inicie sesión en el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador en la organización de Microsoft 365 y, a continuación, vaya a **Permisos**</a>.

2. Seleccione el vínculo para ver y administrar roles en Office 365.

3. Seleccione uno de los grupos de roles de cumplimiento de comunicaciones y, a continuación, seleccione **Editar grupo de roles**.

4. Seleccione **Elegir miembros** en el panel de navegación izquierdo y, a continuación, seleccione **Editar**.

5. Seleccione **Agregar** y, a continuación, active la casilla para todos los usuarios que quiera agregar al grupo de roles.

6. Seleccione **Agregar** y, después, **Listo**.

7. Seleccione **Guardar** para agregar los usuarios al grupo de roles.

8. Seleccione el siguiente grupo de roles de cumplimiento de comunicaciones y repita los pasos del 4 al 7 para cada grupo de roles necesario.

9. Seleccione **Cerrar** para completar los pasos.

Para obtener más información sobre los grupos de roles y los permisos, consulte [Permisos en el Centro de cumplimiento](../security/office-365-security/protect-against-threats.md).

## <a name="step-2-required-enable-the-audit-log"></a>Paso 2 (obligatorio): Habilitación del registro de auditoría

El Cumplimiento de comunicaciones requiere registros de auditoría para mostrar alertas y realizar un seguimiento de las acciones de corrección realizadas por los revisores. Los registros de auditoría son un resumen de todas las actividades asociadas con una directiva organizativa definida o en cualquier momento en que se realicen cambios en la directiva de cumplimiento de comunicaciones.

La auditoría está habilitada para organizaciones de Microsoft 365 de forma predeterminada. Algunas organizaciones pueden haber deshabilitado la auditoría por motivos específicos. Si la auditoría está deshabilitada para su organización, puede deberse a que otro administrador la ha desactivado. Se recomienda confirmar que es correcto volver a activar la auditoría al completar este paso.

Para obtener instrucciones paso a paso para activar la auditoría, consulte [Activar o desactivar la búsqueda de registros de auditoría](/microsoft-365/compliance/turn-audit-log-search-on-or-off). Después de activar la auditoría, se muestra un mensaje que dice que el registro de auditoría se está preparando y que puede ejecutar una búsqueda en un par de horas después de que se complete la preparación. Solo tiene que realizar esta acción una vez. Para obtener más información sobre el uso del registro de auditoría, vea [Buscar en el registro de auditoría](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a>Paso 3 (opcional): Configuración de grupos para el cumplimiento de la comunicación

 Al crear una directiva de cumplimiento de comunicaciones, se define quién tiene sus comunicaciones revisadas y quién realiza revisiones. En la directiva, usará direcciones de correo electrónico para identificar personas o grupos de personas. Para simplificar la configuración, puede crear grupos para las personas que tienen su comunicación revisada y grupos para las personas que revisan esas comunicaciones. Si usa grupos, es posible que necesite varios. Por ejemplo, si desea detectar comunicaciones entre dos grupos distintos de personas o si desea especificar un grupo que no se va a supervisar.

Use el siguiente gráfico para ayudarle a configurar grupos en su organización para directivas de cumplimiento de comunicaciones:

| **Miembro de directiva** | **Grupos admitidos** | **Grupos no admitidos** |
|:-----|:-----|:-----|
|Usuarios supervisados <br> Usuarios excluidos | Grupos de distribución <br> Grupos de Microsoft 365 | Grupos de distribución dinámicos <br> Grupos de distribución anidados <br> Grupos de seguridad habilitados para correo <br> Grupos de Microsoft 365 con pertenencia dinámica |
| Reviewers | Ninguno | Grupos de distribución <br> Grupos de distribución dinámicos <br> Grupos de distribución anidados <br> Grupos de seguridad habilitados para correo |

Al asignar un *grupo de distribución* en la directiva, la directiva supervisa todos los correos electrónicos y chats de Teams de cada usuario del *grupo de distribución*. Al asignar un *grupo de Microsoft 365* en la directiva, la directiva detecta todos los correos electrónicos y chats de Teams enviados al *grupo de Microsoft 365*, no los correos electrónicos y chats individuales recibidos por cada miembro del grupo. Se recomienda usar grupos de distribución en directivas de cumplimiento de comunicaciones para que los correos electrónicos individuales y los chats de Teams de cada usuario se supervisen automáticamente.

Si es una organización con una implementación local de Exchange o un proveedor de correo electrónico externo y desea detectar chats de Microsoft Teams para los usuarios, debe crear un grupo de distribución para que los usuarios con buzones locales o externos supervisen. Más adelante en estos pasos, asignará este grupo de distribución como la selección usuarios **y grupos supervisados** en el Asistente para directivas. Para obtener más información sobre los requisitos y limitaciones para habilitar el almacenamiento basado en la nube y la compatibilidad de Teams con los usuarios locales, consulte [Búsqueda de datos de chat de Teams para usuarios locales](/microsoft-365/compliance/search-cloud-based-mailboxes-for-on-premises-users).

Para administrar usuarios supervisados en grandes organizaciones empresariales, es posible que tenga que supervisar todos los usuarios en grupos grandes. Puede usar PowerShell para configurar un grupo de distribución para una directiva de cumplimiento de comunicaciones global para el grupo asignado. Esto le permite supervisar miles de usuarios con una sola directiva y mantener actualizada la directiva de cumplimiento de comunicaciones a medida que los nuevos empleados se unan a su organización.

1. Cree un [grupo de distribución](/powershell/module/exchange/new-distributiongroup) dedicado para la directiva de cumplimiento de comunicaciones global con las siguientes propiedades: Asegúrese de que este grupo de distribución no se usa para otros fines u otros servicios de Office 365.

    - **MemberDepartRestriction = Closed**. Garantiza que los usuarios no puedan quitarse ellos mismos del grupo de distribución.
    - **MemberJoinRestriction = Closed**. Garantiza que los usuarios no puedan agregarse a sí mismos al grupo de distribución.
    - **ModerationEnabled = True**. Garantiza que todos los mensajes enviados a este grupo están sujetos a aprobación y que el grupo no se usa para comunicarse fuera de la configuración de la directiva de cumplimiento de comunicaciones.

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. Seleccione un [atributo personalizado de Exchange](/Exchange/recipients/mailbox-custom-attributes) sin usar para realizar un seguimiento de los usuarios agregados a la directiva de cumplimiento de comunicaciones de su organización.

3. Ejecute el siguiente script de PowerShell en una programación periódica para agregar usuarios a la directiva de cumplimiento de comunicaciones:

    ```PowerShell
    $Mbx = (Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited -Filter {CustomAttribute9 -eq $Null})
    $i = 0
    ForEach ($M in $Mbx)
    {
      Write-Host "Adding" $M.DisplayName
      Add-DistributionGroupMember -Identity <your group name> -Member $M.DistinguishedName -ErrorAction SilentlyContinue
      Set-Mailbox -Identity $M.Alias -<your custom attribute name> SRAdded
      $i++
    }
    Write-Host $i "Mailboxes added to supervisory review distribution group."
    ```

Para obtener más información sobre cómo configurar grupos, consulte:

- [Crear y administrar grupos de distribución](/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Introducción a Grupos de Microsoft 365](/office365/admin/create-groups/office-365-groups)

## <a name="step-4-optional-verify-your-yammer-tenant-is-in-native-mode"></a>Paso 4 (opcional): compruebe que el inquilino de Yammer está en modo nativo

En modo nativo, todos los usuarios de Yammer están en Azure Active Directory (Azure AD), todos los grupos son grupos Office 365 y todos los archivos se almacenan en SharePoint Online. El inquilino de Yammer debe estar en modo nativo para que las directivas de cumplimiento de comunicaciones examinen e identifiquen conversaciones de riesgo en mensajes privados y conversaciones de la comunidad en Yammer.

Para obtener más información sobre cómo configurar Yammer en modo nativo, consulte:

- [Introducción al modo nativo de Yammer en Microsoft 365](/yammer/configure-your-yammer-network/overview-native-mode)
- [Configurar su red de Yammer para el Modo nativo para Microsoft 365](/yammer/configure-your-yammer-network/native-mode)

## <a name="step-5-required-create-a-communication-compliance-policy"></a>Paso 5 (obligatorio): Creación de una directiva de cumplimiento de comunicaciones

>[!IMPORTANT]
>No se admite el uso de PowerShell para crear y administrar directivas de cumplimiento de comunicaciones. Para crear y administrar estas directivas, debe usar los controles de administración de directivas en la [solución de cumplimiento de comunicaciones](https://compliance.microsoft.com/supervisoryreview).

>[!TIP]  
>¿Desea ver un tutorial detallado sobre cómo configurar una nueva directiva de cumplimiento de comunicaciones y corregir una alerta? Consulte [este vídeo de 15 minutos](/microsoft-365/compliance/communication-compliance-plan#creating-a-communication-compliance-policy-walkthrough) para ver una demostración de cómo las directivas de cumplimiento de comunicaciones pueden ayudarle a detectar mensajes inadecuados, investigar posibles infracciones y corregir problemas de cumplimiento.

1. Inicie sesión en la [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador en la organización de Microsoft 365.

2. En el portal de cumplimiento Microsoft Purview, seleccione **Cumplimiento de la comunicación**.

3. Seleccione la pestaña **Directivas**.

4. Seleccione **Crear directiva** para crear y configurar una nueva directiva a partir de una plantilla o para crear y configurar una directiva personalizada.

    Si elige una plantilla de directiva para crear una directiva, hará lo siguiente:

    - Confirme o actualice el nombre de la directiva. Los nombres de las directivas no se pueden cambiar una vez se crea la directiva.

    - Elija los usuarios o grupos que desea supervisar, incluidos los usuarios o grupos que desea excluir. Al usar la plantilla de conflicto de intereses, seleccionará dos grupos o dos usuarios para supervisar las comunicaciones internas.

    - Elija los revisores de la directiva. Los revisores son usuarios individuales y todos los revisores deben tener buzones hospedados en Exchange Online. Los revisores agregados aquí son los revisores entre los que puede elegir al escalar una alerta en el flujo de trabajo de investigación y corrección. Cuando los revisores se agregan a una directiva, reciben automáticamente un mensaje de correo electrónico que les notifica la asignación a la directiva y proporciona vínculos a información sobre el proceso de revisión.

    - Elija un campo de condición limitada, normalmente un tipo de información confidencial o un diccionario de palabras clave para aplicar a la directiva.

    > [!NOTE]
    > Si desea habilitar el [reconocimiento óptico de caracteres (OCR)](/microsoft-365/compliance/communication-compliance-policies#optical-character-recognition-ocr) para examinar imágenes insertadas o adjuntas en mensajes para texto impreso o manuscrito que coincida con las condiciones de la directiva, seleccione Personalizar **condiciones y porcentaje de directivas**  >  y habilite **Extraer texto impreso o manuscrito de imágenes para su evaluación**.

    Si decide usar el Asistente para directivas para crear una directiva personalizada, hará lo siguiente:

    - Asigne un nombre y una descripción a la directiva. Los nombres de las directivas no se pueden cambiar una vez se crea la directiva.

    - Elija los usuarios o grupos que desea supervisar, incluidos todos los usuarios de la organización, usuarios y grupos específicos, u otros usuarios y grupos que quiera excluir.

    - Elija los revisores de la directiva. Los revisores son usuarios individuales y todos los revisores deben tener buzones hospedados en Exchange Online. Los revisores agregados aquí son los revisores entre los que puede elegir al escalar una alerta en el flujo de trabajo de investigación y corrección. Cuando los revisores se agregan a una directiva, reciben automáticamente un mensaje de correo electrónico que les notifica la asignación a la directiva y proporciona vínculos a información sobre el proceso de revisión.

    - Elija los canales de comunicación que desea examinar, incluidos Exchange, Microsoft Teams o Yammer. También tendrá que examinar los orígenes de terceros si configuró un conector en Microsoft 365.

    - Elija la dirección de comunicación que desea detectar, incluidas las comunicaciones entrantes, salientes o internas.

    - Defina las [condiciones](/microsoft-365/compliance/communication-compliance-policies#conditional-settings) de la directiva de cumplimiento de comunicaciones. Puede elegir entre la dirección del mensaje, la palabra clave, los tipos de archivo y las condiciones de coincidencia de tamaño.

    - Elija si desea incluir tipos de información confidencial. En este paso puede seleccionar tipos de información confidencial predeterminados y personalizados. Elija entre los tipos de información confidencial personalizados existentes o diccionarios de palabras clave personalizadas en el Asistente para directivas de cumplimiento de comunicaciones. Puede crear estos elementos antes de ejecutar el asistente si es necesario. También puede crear nuevos tipos de información confidencial desde el Asistente para directivas de cumplimiento de comunicaciones.

    - Elija si desea habilitar clasificadores. Los clasificadores pueden detectar el lenguaje inadecuado y las imágenes enviadas o recibidas en el cuerpo de los mensajes de correo electrónico u otros tipos de texto. Puede elegir los siguientes clasificadores integrados: *Amenazas*, *Profanidad*, *Acoso dirigido*, *Imágenes para adultos*, *Imágenes de Racy* e *Imágenes de Gory*.

    - Habilite el [reconocimiento óptico de caracteres (OCR)](/microsoft-365/compliance/communication-compliance-policies#optical-character-recognition-ocr) para examinar imágenes incrustadas o adjuntas en mensajes para texto impreso o manuscrito que coincida con las condiciones de la directiva. En el caso de las directivas personalizadas, se debe configurar una o varias opciones condicionales asociadas con texto, palabras clave, clasificadores o tipos de información confidencial en la directiva para habilitar la selección del examen óptico del reconocimiento de caracteres.

    - Definir el porcentaje de comunicaciones que se revisan.

    - Revise las selecciones de directiva y cree la directiva.

5. Seleccione **Crear directiva** al usar las plantillas o **Enviar** al usar el Asistente para directivas personalizadas.

6. La página **Se ha creado la directiva** muestra con instrucciones sobre cuándo se activará la directiva y qué comunicaciones se capturarán.

## <a name="step-6-optional-update-compliance-boundaries-for-communication-compliance-policies"></a>Paso 6 (opcional): Actualización de los límites de cumplimiento para las directivas de cumplimiento de comunicaciones

[Los límites de cumplimiento](/microsoft-365/compliance/set-up-compliance-boundaries) crean límites lógicos dentro de una organización que controlan las ubicaciones de contenido del usuario (como buzones, cuentas de OneDrive y sitios de SharePoint) que los administradores de eDiscovery pueden buscar.

Si ha configurado límites de cumplimiento en su organización, debe actualizar los límites de cumplimiento para permitir que determinados usuarios accedan a buzones que admiten directivas de cumplimiento de comunicaciones. Tendrá que permitir el acceso a los administradores de cumplimiento de comunicaciones y a los revisores de cumplimiento de comunicaciones para que las acciones de administración e investigación y corrección de directivas funcionen correctamente.

Para permitir el acceso a los administradores y revisores de cumplimiento de comunicaciones, ejecute los siguientes comandos de PowerShell. Solo necesita ejecutar estos comandos una vez, incluso si agrega nuevas directivas de cumplimiento de comunicaciones en el futuro:

```powershell
Import-Module ExchangeOnlineManagement
$UserCredential = Get-Credential
Connect-IPPSSession -Credential $UserCredential
New-ComplianceSecurityFilter -FilterName "CC_mailbox" -Users <list your communication compliance admins and reviewers user alias or email address> -Filters "Mailbox_Name -like 'SupervisoryReview{*'" -Action All
```

Para obtener más información sobre la sintaxis de cmdlets, vea [New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter).

## <a name="step-7-optional-create-notice-templates-and-configure-user-anonymization"></a>Paso 7 (opcional): Creación de plantillas de aviso y configuración de anonimización de usuarios

Si desea tener la opción de responder a una alerta de directiva mediante el envío de un aviso al usuario asociado, deberá crear al menos una plantilla de aviso en su organización. Los campos de plantilla de aviso son editables antes de que se envíen como parte del proceso de corrección de alertas y se recomienda crear una plantilla de aviso personalizada para cada directiva de cumplimiento de comunicaciones.

También puede optar por habilitar la anonimización de los nombres de usuario mostrados al investigar las coincidencias de directivas y tomar medidas en los mensajes.

1. Inicie sesión en la [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com) con las credenciales de una cuenta de administrador en la organización de Microsoft 365.

2. En el portal de cumplimiento Microsoft Purview, vaya a **Cumplimiento de comunicaciones**.

3. Para configurar la anonimización de los nombres de usuario, seleccione la pestaña **Privacidad** .

4. Para habilitar la anonimización, seleccione **Mostrar versiones anónimas de nombres de usuario**.

5. Haga clic en **Guardar**.

6. Vaya a la pestaña **Plantillas de aviso** y seleccione **Crear plantilla de aviso**.

7. En la página **Modificar una plantilla de aviso** , complete los campos siguientes:

    - Nombre de plantilla (obligatorio)
    - Enviar desde (obligatorio)
    - Cc y CCO (opcional)
    - Asunto (obligatorio)
    - Cuerpo del mensaje (obligatorio)

8. Seleccione **Guardar** para crear y guardar la plantilla de aviso.

## <a name="step-8-optional-test-your-communication-compliance-policy"></a>Paso 8 (opcional): Prueba de la directiva de cumplimiento de comunicaciones

Después de crear una directiva de cumplimiento de comunicaciones, es recomendable probarla para asegurarse de que la directiva aplica correctamente las condiciones definidas. También puede probar las [directivas de Prevención de pérdida de datos de Microsoft Purview (DLP)](/microsoft-365/compliance/create-test-tune-dlp-policy) si las directivas de cumplimiento de comunicaciones incluyen tipos de información confidencial. Asegúrese de dar tiempo a las directivas para que se activen para que se capturen las comunicaciones que desea probar.

Siga estos pasos para probar la directiva de cumplimiento de comunicaciones:

1. Abra un cliente de correo electrónico, Microsoft Teams o Yammer mientras ha iniciado sesión como un usuario supervisado definido en la directiva que desea probar.

2. Envíe un correo electrónico, un chat de Microsoft Teams o un mensaje de Yammer que cumpla los criterios que ha definido en la directiva de cumplimiento de comunicaciones. Esta prueba puede ser una palabra clave, un tamaño de datos adjuntos, un dominio, etc. Asegúrese de determinar si la configuración condicional configurada en la directiva es demasiado restrictiva o demasiado indulgente.

    > [!NOTE]
    > Los mensajes de correo electrónico pueden tardar aproximadamente 24 horas en procesarse completamente en una directiva. Las comunicaciones en Microsoft Teams, Yammer y plataformas de terceros pueden tardar aproximadamente 48 horas en procesarse completamente en una directiva.

3. Inicie sesión en Microsoft 365 como revisor designado en la directiva de cumplimiento de comunicaciones. Vaya a **Alertas** de **cumplimiento** >  de comunicaciones para ver las alertas de las directivas.

4. Corrija la alerta mediante los controles de corrección y compruebe que la alerta se haya resuelto correctamente.

## <a name="next-steps"></a>Siguientes pasos

Una vez completados estos pasos para crear la primera directiva de cumplimiento de comunicaciones, comenzará a recibir alertas de indicadores de actividad después de 24-48 horas. Configure directivas adicionales según sea necesario mediante las instrucciones del paso 5 de este artículo.

Para más información sobre la investigación de alertas de cumplimiento de comunicaciones, consulte [Investigación y corrección de alertas de cumplimiento de comunicaciones](/microsoft-365/compliance/communication-compliance-investigate-remediate).

Para mantenerse al día con las últimas actualizaciones de cumplimiento de comunicaciones, seleccione **Novedades** del [cumplimiento de comunicaciones](https://compliance.microsoft.com/) de su organización.
