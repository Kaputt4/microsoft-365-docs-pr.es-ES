---
title: Ver o editar directivas de protección de dispositivos
description: Ver, editar, crear y eliminar directivas de protección de dispositivos en Microsoft 365 Empresa Premium
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: microsoft-365-security
ms.subservice: other
ms.date: 09/15/2022
ms.localizationpriority: high
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-security
- tier1
ms.openlocfilehash: ad7b0728cbba3a59d58b0bbd8706aca3431ff253
ms.sourcegitcommit: 0283c436f3ba61a708b52b57a1955f5ea74376a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2022
ms.locfileid: "68096993"
---
# <a name="view-and-edit-device-protection-policies"></a>Ver y editar directivas de protección de dispositivos

En Microsoft 365 Empresa Premium, la configuración de seguridad de los dispositivos administrados se configura mediante directivas de protección de dispositivos en el portal de Microsoft 365 Defender o en el Centro de administración de Microsoft Endpoint Manager. Para simplificar la experiencia de configuración, hay una serie de directivas preconfiguradas que ayudan a proteger los dispositivos de la organización en cuanto se incorporan. Use las directivas predeterminadas, edite las directivas existentes o cree sus propias directivas.

**Esta guía indica cómo**:

- Obtener información general de las directivas predeterminadas
- Trabaje con directivas de dispositivo en el portal de Microsoft 365 Defender o en el Centro de administración de Microsoft Endpoint Manager (Intune).

## <a name="about-the-default-device-protection-policies"></a>Información sobre las directivas de protección del dispositivo predeterminadas

Microsoft 365 Empresa Premium incluye dos tipos principales de directivas para proteger los dispositivos de la organización:

- Las **directivas de protección de última generación**, que determinan la forma en que se configura el Antivirus de Microsoft Defender y otras características de la protección contra amenazas.

- Las **directivas de firewall**, que determinan qué tipo tráfico de red puede fluir hacia y desde los dispositivos de la organización

Estas directivas forman parte de Microsoft Defender para Empresas, que se incluye en la suscripción de Microsoft 365 Empresa Premium. Se proporciona información para trabajar con directivas en el portal de Microsoft 365 Defender o en el Centro de administración de Microsoft Endpoint Manager.

## <a name="working-with-device-polices-in-the-microsoft-365-defender-portal"></a>Trabajar con directivas de dispositivo en el portal de Microsoft 365 Defender

Los detalles siguientes se aplican al trabajo con las directivas en el Centro de seguridad.

### <a name="view-existing-device-protection-policies"></a>Ver las directivas de protección del dispositivo existentes

Para ver las directivas de protección de dispositivos existentes en el portal de Microsoft 365 Defender:

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

1. In the navigation pane, choose **Device configuration**. Policies are organized by operating system (such as **Windows client**) and policy type (such as **Next-generation protection** and **Firewall**).

    :::image type="content" source="../media/mdb-deviceconfiguration.png" lightbox="../media/mdb-deviceconfiguration.png" alt-text="Página de configuración del dispositivo.":::

1. Seleccione una pestaña del sistema operativo (por ejemplo, **clientes de Windows**) y, a continuación, revise la lista de directivas en las categorías **Protección de última generación** y **Firewall**.

1. Para ver más detalles sobre una directiva, seleccione su nombre. Se abre un panel lateral que proporciona más información sobre la directiva, por ejemplo, qué dispositivos están protegidos por esa directiva.

   :::image type="content" source="../media/mdb-deviceconfig-selectedpolicy.png" lightbox="../media/mdb-deviceconfig-selectedpolicy.png" alt-text="Recorte de pantalla de una directiva seleccionada en la página Configuración del dispositivo.":::

### <a name="edit-an-existing-device-protection-policy"></a>Editar una directiva existente de protección de dispositivos

Para editar una directiva de dispositivo:

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

1. In the navigation pane, choose **Device configuration**. Policies are organized by operating system (such as **Windows client**) and policy type (such as **Next-generation protection** and **Firewall**).

1. Seleccione una pestaña del sistema operativo (por ejemplo, **clientes de Windows**) y, a continuación, revise la lista de directivas en las categorías **Protección de última generación** y **Firewall**.

1. Para editar una directiva, seleccione su nombre y, a continuación, elija **Editar**.

1. En la pestaña **Información general**, revise la información. Si es necesario, puede editar la descripción. A continuación, elija **Siguiente**.

1. En la pestaña **Grupos de dispositivos**, determine qué grupos de dispositivos deben recibir esta directiva.  

   - Para dejar el grupo de dispositivos seleccionado tal y como está, elija **Siguiente**.
   - Para quitar un grupo de dispositivos de la directiva, seleccione **Quitar**.
   - Para configurar un nuevo grupo de dispositivos, seleccione **Crear nuevo grupo** y, a continuación, configure el grupo de dispositivos. (Para obtener ayuda con esta tarea, consulte [Grupos de dispositivos en Microsoft 365 Empresa Premium](m365bp-device-groups-mdb.md)).
   - Para aplicar la directiva a otro grupo de dispositivos, seleccione **Usar grupo existente**.

   Después de especificar qué grupos de dispositivos deben recibir la directiva, elija **Siguiente**.

1. En la pestaña **Opciones de configuración**, revise la configuración. Si es necesario, puede editar la configuración de la directiva. Para obtener ayuda con esta tarea, consulte los artículos siguientes: 

   - [Comprender las opciones de configuración de última generación](../security/defender-business/mdb-next-gen-configuration-settings.md)   
   - [Configuración de firewall](../security/defender-business/mdb-firewall.md)

   Una vez que haya especificado las opciones de configuración de protección de última generación, elija **Siguiente**.

1. En la pestaña **Revisar la directiva**, revise la información general, los dispositivos de destino y las opciones de configuración.

   - Si necesita realizar cambios, seleccione **Editar**.
   - Cuando esté listo para continuar, elija **Actualizar directiva**.

### <a name="create-a-new-device-protection-policy"></a>Crear una nueva directiva de protección de dispositivos

Para crear una nueva directiva de protección de dispositivos:

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

1. In the navigation pane, choose **Device configuration**. Policies are organized by operating system (such as **Windows client**) and policy type (such as **Next-generation protection** and **Firewall**).

1. Seleccione una pestaña del sistema operativo (por ejemplo, **clientes de Windows**) y, a continuación, revise la lista de directivas de **Protección de última generación**.

1. En **Protección de última generación** o **Firewall**, seleccione **+ Agregar**.

1. En la pestaña **Información general**, siga estos pasos:

   1. Especifique un nombre y una descripción. Esta información le ayudará a usted y a su equipo a identificar la directiva más adelante.
   2. Revise el orden de la directiva y edítelo si fuera necesario. (Para obtener más información, consulte [Orden de directiva](../security/defender-business/mdb-policy-order.md)).
   3. Elija **Siguiente**.

1. En la pestaña **Grupos de dispositivos**, cree un nuevo grupo de dispositivos o use un grupo existente. Las directivas se asignan a los dispositivos a través de grupos de dispositivos. Estos son algunos aspectos que debe tener en cuenta:

   - Initially, you might only have your default device group, which includes the devices people in your organization are using to access organization data and email. You can keep and use your default device group.
   - Cree un nuevo grupo de dispositivos para aplicar una directiva con una configuración específica que sea diferente de la directiva predeterminada.
   - Al configurar el grupo de dispositivos, se especifican determinados criterios, como la versión del sistema operativo. Los dispositivos que cumplen los criterios se incluyen en ese grupo de dispositivos, a menos que se excluyan.
   - Todos los grupos de dispositivos, incluidos los grupos de dispositivos predeterminados y personalizados que defina, se almacenan en Azure Active Directory (Azure AD).

   Para más información sobre los grupos de dispositivos, consulte [Grupos de dispositivos en Microsoft Defender para Empresas](../security/defender-business/mdb-create-edit-device-groups.md).

1. En la pestaña **Opciones de configuración**, especifique la configuración de la directiva y, a continuación, elija **Siguiente**. Para obtener más información sobre la configuración individual, consulte [Comprender las opciones de configuración de última generación en Microsoft Defender para Empresas](../security/defender-business/mdb-next-gen-configuration-settings.md).

1. En la pestaña **Revisar la directiva**, revise la información general, los dispositivos de destino y las opciones de configuración.

   - Si necesita realizar cambios, seleccione **Editar**.
   - Cuando esté listo para continuar, elija **Crear directiva**.

## <a name="working-with-device-policies-in-the-microsoft-endpoint-manager-admin-center"></a>Trabajar con directivas de dispositivo en el Centro de administración de Microsoft Endpoint Manager

Use la siguiente información para crear y administrar las directivas del dispositivo en Intune a través de la seguridad de los puntos de conexión en el Centro de administración de Microsoft Endpoint Manager.

### <a name="create-duplicate-and-edit-policies"></a>Crear, duplicar y editar directivas

Para crear una directiva en Intune

1. Inicie sesión en el Centro de administración de Microsoft Endpoint Manager.

1. Seleccione **Seguridad del punto de conexión** y el tipo de directiva que desea configurar y, a continuación, seleccione **Crear directiva**.

1. Elija entre los siguientes tipos de directiva:

    - Antivirus
    - Cifrado de disco
    - Firewall
    - Detección y respuesta de puntos de conexión
    - Reducción de la superficie expuesta a ataques
    - Protección de cuentas
    - Escriba las propiedades siguientes:

1. Plataforma: Elija la plataforma para la que va a crear la directiva. Las opciones disponibles dependen del tipo de directiva que seleccione.

1. Perfil: Elija entre los perfiles disponibles para la plataforma seleccionada. Para obtener información sobre los perfiles, consulte la sección dedicada en este artículo para el tipo de directiva elegido.

1. Seleccione **Crear**.

1. En la página Datos básicos, escriba un nombre y una descripción para el perfil y, después, elija **Siguiente**.

1. En la página Opciones de configuración, expanda cada grupo de opciones y configure las opciones que desea administrar con este perfil.

1. Cuando haya finalizado la configuración, seleccione **Siguiente**.

1. En la página Ámbito (etiquetas), seleccione **Seleccionar etiquetas de ámbito** para abrir el panel **Seleccionar etiquetas** y así asignar etiquetas de ámbito al perfil.

1. Seleccione **Siguiente** para continuar.

1. En la página **Asignaciones**, seleccione los grupos que recibirán este perfil. Para obtener más información sobre la asignación de perfiles, vea Asignación de perfiles de usuario y dispositivo.

1. Seleccione **Siguiente**.

1. Cuando haya terminado, elija Crear en la página **Revisar y crear**. El nuevo perfil se muestra en la lista cuando se selecciona el tipo de directiva del perfil creado.

Para duplicar una directiva en Intune:

1. Inicie sesión en el Centro de administración de Microsoft Endpoint Manager.

1. Select the policy that you want to copy. Next, select **Duplicate** or select the ellipsis **(...)** to the right of the policy and select **Duplicate**.
1. Proporcione un Nuevo nombre a la directiva y seleccione **Guardar**.

Para editar una directiva:

1. Seleccione la nueva directiva y, a continuación, seleccione **Propiedades**.

1. Seleccione **Configuración** para expandir una lista de las opciones de configuración de la directiva. No puede modificar la configuración desde esta vista, aunque puede revisar cómo está configurada.

1. Para modificar la directiva, seleccione **Editar** en cada una de las categorías en las que quiera realizar cambios:

    - Conceptos básicos
    - Tareas
    - Etiquetas de ámbito
    - Opciones de configuración

1. Una vez realizados los cambios, seleccione **Guardar** para guardar las modificaciones. Las ediciones en una categoría deben guardarse para poder introducir ediciones en otras categorías.

## <a name="manage-conflicts"></a>Administrar conflictos

Muchas de las configuraciones del dispositivo que puede administrar con las Directivas de seguridad de puntos de conexión también están disponibles a través de otros tipos de directivas en Intune. Estos otros tipos de directiva incluyen directivas de configuración de dispositivos y líneas de base de seguridad. Debido a que la configuración se puede administrar a través de varios tipos de directiva diferentes o mediante varias instancias del mismo tipo de directiva, prepárese para identificar y resolver los conflictos de directivas de los dispositivos que no cumplan las configuraciones esperadas.

Las líneas de base de seguridad pueden establecer un valor no predeterminado para que un ajuste cumpla con la configuración recomendada a la que se dirige la línea de base.

Otros tipos de directiva, incluidas las directivas de seguridad del punto de conexión, están establecidas en el valor No configurado de forma predeterminada. Estos otros tipos de directiva requieren que configure explícitamente las opciones de la directiva.

Independientemente del método de la directiva, la administración de la misma configuración en el mismo dispositivo a través de varios tipos de directiva, o a través de varias instancias del mismo tipo de directiva, puede dar lugar a conflictos que deben evitarse.

## <a name="see-also"></a>Vea también

[Administración de seguridad de puntos de conexión en Microsoft Intune](/mem/Intune/protect/endpoint-security)

[Procedimientos recomendados para proteger Microsoft 365 para planes empresariales](../admin/security-and-compliance/secure-your-business-data.md)

## <a name="next-objective"></a>Siguiente objetivo

[Configurar y administrar grupos de dispositivos](m365bp-device-groups-mdb.md)