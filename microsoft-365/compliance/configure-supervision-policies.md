---
title: Configurar directivas de supervisión
description: Configure las directivas de supervisión de comunicaciones en Office 365 para capturar las comunicaciones de los empleados para que las examinan los revisores internos o externos.
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
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
titleSuffix: Office 365 Compliance
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74244b5288043a1d1bc62e0ae09ee8c25ff7d4e1
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546782"
---
# <a name="configure-supervision-policies-in-office-365"></a>Configurar directivas de supervisión en Office 365

>[!IMPORTANT]
>Tras la publicación del cumplimiento de las comunicaciones en Cumplimiento de Microsoft 365 en febrero de 2020, se retirará la supervisión en Office 365. Las directivas de supervisión ya no estarán disponibles para su creación y, finalmente, se quitarán después de un período prolongado de acceso de solo lectura.
>
>Si usa supervisión, tenga en cuenta lo siguiente:
>
>- A partir del 15 de junio de 2020, los inquilinos no podrán crear nuevas directivas de supervisión.
>- A partir del 31 de agosto de 2020, las directivas existentes dejarán de capturar mensajes nuevos.
>- A partir del 26 de octubre de 2020, se eliminarán las directivas existentes.
>
>Animamos activamente a los clientes que actualmente exploran o usan [](communication-compliance.md) la supervisión en Office 365 a usar la nueva solución de cumplimiento de comunicaciones para abordar los requisitos normativos o de supervisión de comunicaciones con un conjunto mucho más amplio de capacidades inteligentes.

Use directivas de supervisión para capturar las comunicaciones de los empleados para su examen por parte de revisores internos o externos. Para obtener más información acerca de cómo las directivas de supervisión pueden ayudarle a supervisar las comunicaciones de su organización, vea Directivas de supervisión [en Office 365.](supervision-policies.md)

>[!NOTE]
>Los usuarios supervisados por directivas de supervisión deben tener una licencia de Cumplimiento de Microsoft 365 E5, una licencia de Office 365 Enterprise E3 con el complemento cumplimiento avanzado, o estar incluidos en una suscripción de Office 365 Enterprise E5, o estar incluidos en una suscripción de Microsoft 365 E5.
>Si no tiene un plan Enterprise E5 existente y desea probar la supervisión, puede registrarse para obtener una versión de prueba de [Office 365 Enterprise E5.](https://go.microsoft.com/fwlink/p/?LinkID=698279)
  
Siga estos pasos para configurar y usar la supervisión en su organización:
  
- **Paso 1 (opcional):** Configurar [grupos para supervisión](#step-1-set-up-groups-for-supervision-optional)

    Antes de empezar a usar directivas de supervisión, determine quién necesita revisar las comunicaciones y quién realiza las revisiones. Si desea empezar a trabajar con unos pocos usuarios para ver cómo funciona la supervisión, puede omitir la configuración de grupos por ahora.

- **Paso 2 (obligatorio):** Hacer [que la supervisión esté disponible en la organización](#step-2-make-supervision-available-in-your-organization-required)

    Agrégase al grupo de roles Revisión de supervisión para poder configurar directivas. Cualquier persona que tenga asignado este rol puede acceder **a la página Supervisión** del Centro de & cumplimiento. Si el correo electrónico revisable se hospeda en Exchange Online, cada revisor debe tener acceso remoto [de PowerShell a Exchange Online.](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)

- **Paso 3 (opcional):** Crear tipos personalizados de [información confidencial y diccionarios](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional) de palabras clave personalizadas

    Si necesita un tipo personalizado de información confidencial o un diccionario de palabras clave personalizado para la directiva de supervisión, debe crearlo antes de iniciar el asistente para supervisión.

- **Paso 4 (obligatorio):** Configurar [una directiva de supervisión](#step-4-set-up-a-supervision-policy-required)

    Las directivas de supervisión se crean en el Centro de & cumplimiento. Estas directivas definen qué comunicaciones están sujetas a revisión en su organización y especifican quién realiza las revisiones. Las comunicaciones incluyen el correo electrónico y las comunicaciones de Microsoft Teams, y las comunicaciones de plataforma de terceros (como Facebook, Twitter, etc.). Las directivas de supervisión creadas en organizaciones no se admiten en la supervisión de comunicaciones en las suscripciones de Microsoft 365.

- **Paso 5 (opcional):** Probar [la directiva de supervisión de comunicaciones](#step-5-test-your-supervision-policy-optional)

    Pruebe la directiva de supervisión para asegurarse de que funciona según lo desee. Es importante asegurarse de que su estrategia de cumplimiento cumple los estándares.

## <a name="step-1-set-up-groups-for-supervision-optional"></a>Paso 1: Configurar grupos para supervisión (opcional)

 Al crear una directiva de supervisión, se define quién tiene sus comunicaciones examinadas y quién realiza las revisiones. En la directiva, usará direcciones de correo electrónico para identificar a personas o grupos de personas. Para simplificar la configuración, puede crear grupos para personas que tengan su comunicación examinada y grupos para las personas que revisan dichas comunicaciones. Si usa grupos, es posible que necesite varios. Por ejemplo, desea supervisar las comunicaciones entre dos grupos distintos de personas o si desea especificar un grupo que no se va a supervisar.

Use el siguiente gráfico para ayudarle a configurar grupos en su organización para las directivas de supervisión de comunicaciones:

| **Miembro de directiva** | **Grupos admitidos** | **Grupos no admitidos** |
|:-----|:-----|:-----|
|Usuarios supervisados <br> Usuarios no supervisados | Grupos de distribución <br> Grupos de Microsoft 365 | Grupos de distribución dinámicos |
| Reviewers | Grupos de seguridad habilitados para correo  | Grupos de distribución <br> Grupos de distribución dinámicos |
  
Cuando selecciona un grupo de Microsoft 365 para usuarios supervisados, la directiva supervisa el contenido del buzón compartido y los canales de Microsoft Teams asociados al grupo. Al seleccionar una lista de distribución, la directiva supervisa los buzones de usuario individuales.

Para administrar usuarios supervisados en grandes organizaciones empresariales, es posible que deba supervisar todos los usuarios en grupos grandes. Puede usar PowerShell para configurar un grupo de distribución para una directiva de supervisión global para el grupo asignado. Esto le permite supervisar a miles de usuarios con una única directiva y mantener actualizada la directiva de supervisión a medida que los nuevos empleados se unan a la organización.

1. Cree un grupo de [distribución](https://docs.microsoft.com/powershell/module/exchange/new-distributiongroup) dedicado para la directiva de supervisión global con las siguientes propiedades: asegúrese de que este grupo de distribución no se usa para otros fines u otros servicios de Office 365.

    - **MemberDepartRestriction = Closed**. Garantiza que los usuarios no puedan quitarse a sí mismos del grupo de distribución.
    - **MemberJoinRestriction = Closed**. Garantiza que los usuarios no se puedan agregar al grupo de distribución.
    - **ModerationEnabled = True**. Garantiza que todos los mensajes enviados a este grupo están sujetos a aprobación y que el grupo no se usa para comunicarse fuera de la configuración de la directiva de supervisión.

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. Seleccione un atributo personalizado de [Exchange sin usar para](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww) realizar un seguimiento de los usuarios agregados a la directiva de supervisión de su organización.

3. Ejecute el siguiente script de PowerShell en una programación periódica para agregar usuarios a la directiva de supervisión:

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

Para obtener más información acerca de la configuración de grupos, vea:

- [Crear y administrar grupos de distribución](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [Administrar grupos de seguridad habilitados para correo](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [Información general sobre grupos de Microsoft 365](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-supervision-available-in-your-organization-required"></a>Paso 2: Hacer que la supervisión esté disponible en su organización (obligatorio)

Para que **la supervisión** esté disponible como opción de menú en el Centro de seguridad & cumplimiento, debe tener asignado el rol de administrador de revisión de supervisión.
  
Para ello, puede agregarse como miembro del grupo de roles Revisión de supervisión o puede crear un grupo de roles.
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>Agregar miembros al grupo de roles Revisión de supervisión

1. Inicie sesión [https://protection.office.com](https://protection.office.com) con las credenciales de una cuenta de administrador de su organización.

2. En el Centro de & cumplimiento, vaya a **Permisos.**

3. Seleccione el **grupo de roles Revisión** de supervisión y, a continuación, haga clic en el icono Editar.

4. En la **sección** Miembros, agregue las personas que desea administrar la supervisión de comunicación de su organización.

### <a name="create-a-new-role-group"></a>Crear un nuevo grupo de roles

1. Inicie sesión [https://protection.office.com/permissions](https://protection.office.com/permissions) con las credenciales de una cuenta de administrador de su organización.

2. En el Centro de & cumplimiento, vaya a **Permisos** y, a continuación, haga clic en Agregar ( **+** ).

3. En la **sección Roles,** haga clic en Agregar ( ) y desplácese hacia **+** abajo hasta Administrador de **revisión de supervisión.** Agregue este rol al grupo de roles.

4. En la **sección** Miembros, agregue las personas que desea administrar la supervisión de comunicación de su organización.

Para obtener más información acerca de los grupos de roles y los permisos, vea [Permisos en el Centro de cumplimiento.](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a>Habilitar el acceso remoto de PowerShell para los revisores (si el correo electrónico está hospedado en Exchange Online)

1. Siga las instrucciones de [Habilitar o deshabilitar el acceso a Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)

## <a name="step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a>Paso 3: Crear tipos personalizados de información confidencial y diccionarios de palabras clave personalizadas (opcional)

Para elegir entre tipos de información confidencial personalizados existentes o diccionarios de palabras clave personalizadas en el Asistente para directivas de supervisión, primero debe crear estos elementos si es necesario.

### <a name="create-custom-keyword-dictionarylexicon-optional"></a>Crear diccionario de palabras clave/léxico personalizado (opcional)

Use un editor de texto (como el Bloc de notas) para crear un archivo que incluya los términos de palabra clave que desea supervisar en una directiva de supervisión. Asegúrese de que cada término está en una línea independiente y guarde el archivo en el formato **Unicode/UTF-16 (Little Endian).**

### <a name="create-custom-sensitive-information-types"></a>Crear tipos personalizados de información confidencial

1. Cree un nuevo tipo de información confidencial y agregue el diccionario personalizado en el Centro de & cumplimiento. Vaya a **Clasificaciones Tipos de** información confidencial y siga los pasos del Asistente para nuevo tipo \>  de **información confidencial.** Aquí hará lo siguiente:

    - Definir un nombre y una descripción para el tipo de información confidencial
    - Definir los elementos de proximidad, nivel de confianza y patrón principal
    - Importar el diccionario personalizado como requisito para el elemento correspondiente
    - Revisar las selecciones y crear el tipo de información confidencial

    Para obtener información más detallada, vea [Crear un tipo personalizado](create-a-custom-sensitive-information-type.md) de información confidencial y Crear un diccionario de palabras [clave](create-a-keyword-dictionary.md)

    Después de crear el diccionario/léxico personalizado, puede ver las palabras clave configuradas con el cmdlet [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/get-dlpkeyworddictionary) o agregar y quitar términos con el cmdlet [Set-DlpKeywordDictionary.](https://docs.microsoft.com/powershell/module/exchange/set-dlpkeyworddictionary)

## <a name="step-4-set-up-a-supervision-policy-required"></a>Paso 4: Configurar una directiva de supervisión (obligatorio)
  
1. Inicie sesión [https://protection.office.com](https://protection.office.com) con las credenciales de una cuenta de administrador de su organización.

2. En el Centro de & cumplimiento, seleccione **Supervisión.**
  
3. Seleccione **Crear** y siga el asistente para configurar la configuración de directiva. Con el asistente, hará lo siguiente:

    - Asigne un nombre y una descripción a la directiva.
    - Elija los usuarios o grupos que desea supervisar, incluida la elección de usuarios o grupos que quiera excluir.
    - Definir las condiciones de la directiva [de supervisión.](supervision-policies.md#ConditionalSettings) Puede elegir entre la dirección del mensaje, la palabra clave, los tipos de archivo y las condiciones de coincidencia de tamaño.
    - Elija si desea incluir tipos de información confidencial. Aquí es donde puedes seleccionar tipos de información confidencial predeterminados y personalizados.
    - Elige si quieres habilitar el modelo de lenguaje ofensivo. Esto detecta un idioma inadecuado enviado o recibido en el cuerpo de los mensajes de correo electrónico.
    - Definir el porcentaje de comunicaciones que se revisarán.
    - Elija los revisores de la directiva. Los revisores pueden ser usuarios individuales o [grupos de seguridad habilitados para correo.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group) Todos los revisores deben tener buzones hospedados en Exchange Online.
    - Revisa las selecciones de directiva y crea la directiva.

## <a name="step-5-test-your-supervision-policy-optional"></a>Paso 5: Probar la directiva de supervisión (opcional)

Después de crear una directiva de supervisión de comunicaciones, es una buena idea probar para asegurarse de que la directiva aplica correctamente las condiciones definidas. Es posible que también desee probar las directivas de prevención de pérdida de datos [(DLP)](create-test-tune-dlp-policy.md) si las directivas de supervisión incluyen tipos de información confidencial. Siga estos pasos para probar la directiva de supervisión:

1. Abra un cliente de correo electrónico o Microsoft Teams que haya iniciado sesión como un usuario supervisado definido en la directiva que desea probar.
2. Envíe un correo electrónico o un chat de Microsoft Teams que cumpla los criterios definidos en la directiva de supervisión. Puede ser una palabra clave, un tamaño de datos adjuntos, un dominio, etc. Asegúrese de determinar si la configuración condicional configurada en la directiva es demasiado restrictiva o demasiado lenienta.

    >[!NOTE]
    >Los correos electrónicos sujetos a directivas definidas se procesan casi en tiempo real y se pueden probar inmediatamente después de configurar la directiva. Los chats en Microsoft Teams pueden tardar hasta 24 horas en procesarse completamente en una directiva. 

3. Inicie sesión en Microsoft 365 como revisor designado en la directiva de supervisión de comunicaciones. Vaya a **Supervisión**  >  *de la directiva personalizada*  >  **abierta** para ver el informe de la directiva.

