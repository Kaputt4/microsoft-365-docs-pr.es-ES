---
title: Configurar SAP SuccessFactors como origen de contenido para Aprendizaje Microsoft Viva
ms.author: daisyfeller
author: daisyfell
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 10/27/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: medium
description: Obtenga información sobre cómo configurar SAP SuccessFactors como un origen de contenido de aprendizaje para Aprendizaje Microsoft Viva.
ms.openlocfilehash: fafa0d8b610c3964617015ba3d4d1b9771c9e850
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60747274"
---
# <a name="configure-sap-successfactors-as-a-content-source-for-microsoft-viva-learning"></a>Configurar SAP SuccessFactors como origen de contenido para Aprendizaje Microsoft Viva

En este artículo se muestra cómo configurar SAP SuccessFactors como un origen de contenido de terceros para Aprendizaje Microsoft Viva. En primer lugar, deberá editar la configuración del sistema en successFactors Portal y, a continuación, deberá completar la configuración en el Centro de administración de Microsoft 365.

>[!NOTE]
>El contenido accesible a través de Viva Learning está sujeto a términos distintos de los Términos del producto de Microsoft. El contenido de SAP SuccessFactors y los servicios asociados están sujetos a los términos de privacidad y servicio de SAP SuccessFactors.

## <a name="configure-in-your-successfactors-portal"></a>Configurar en el portal de SuccessFactors

>[!NOTE]
>Deberá tener permisos de administrador en SuccessFactors para completar estos pasos.

1. Obtenga los flujos de trabajo necesarios para editar la configuración PARTNER_EXTRACT, a la que puede acceder yendo a **Configuración** del sistema de administración del  >    >    >  **sistema** PARTNER_EXTRACT .

2. Use la herramienta PGP para generar la clave PGP (clave pública, clave privada, frase de contraseña de clave privada) del tamaño que prefiera. Al generar la clave PGP, puede seleccionar el algoritmo RSA, que se recomienda. La herramienta GNUPG es una de las herramientas de generación de claves de PGP que puede usar.

3. Rellene los siguientes parámetros en la PARTNER_EXTRACT configuración. Para editar la configuración de extracción de partners en SuccessFactors, necesitará permiso de flujo de trabajo **Editar** configuración del sistema en SuccessFactors.

    - correo electrónico de notificación del cliente para todo el estado del trabajo
        - defaultJob.email=
    
    - Partner1
        - La longitud máxima de PartnerID es de 10 caracteres. Puede ser el identificador de inquilino de LMS.
    partners1.partnerID=
    
    - EncryptionKey es la clave de cifrado pública PGP, que es la sección completa entre BEGIN PGP PUBLIC KEY BLOCK y END PGP PUBLIC KEY BLOCK
        - partners1.encryptionKey=
    
    - KeyOwner se asigna al id. de usuario de la clave pública
        - partners1.keyOwner=
    
    - enabled puede ser "false" o "true". Esta opción se establece en "true" para habilitar el extracto de partner.
        - partners1.enabled=
    
    [![Imagen de la configuración PARTNER_EXTRACT configuración. ](../media/learning/sf-focus.png) ](../media/learning/sf-2.png#lightbox)

Una vez que haya completado estos pasos en el portal successFactors, deberá completar la configuración en el Centro de administración de Microsoft 365.

## <a name="configure-in-your-microsoft-365-admin-center"></a>Configurar en el Centro de administración de Microsoft 365

>[!NOTE]
>Tendrás que tener permisos de administrador en Microsoft 365 para completar estos pasos.

1. Vaya a su [Centro de administración de Microsoft 365](https://admin.microsoft.com).

2. Vaya a **Configuración**  >  **configuración de la organización**. Busque Viva *Learning* y habilite SAP SuccessFactors desde las opciones.

3. Rellene los detalles de configuración:

    **Nombre para mostrar:** escriba el nombre para mostrar deseado para el carrusel de SAP SuccessFactors.

    **DIRECCIÓN URL de host SFTP:** vaya a **LMS Admin Application**  >  **System Administration**  >  **Configuration**  >  **System**  >  **CONNECTORS**. Obtener el valor de la `connector.ftp.server` propiedad.

    **Nombre de usuario:** siga los mismos pasos que siguió para la dirección URL del host SFTP. Obtener el valor de la `connector.ftp.userID` propiedad.

    **Contraseña:** escriba la contraseña. Consulte con el propietario de la aplicación LMS para obtener ayuda para recuperar la contraseña.

    **Ruta de acceso de** carpeta: vaya a **LMS Admin Application** System Administration  >    >  **Configuration** System  >  **Configuration PARTNER_EXTRACT**  >  . Obtener el valor de la `defaultFtp.path` propiedad.

    **Dirección URL de host del cliente:** esta es la dirección URL del dominio BizX. Puedes obtener esto desde la dirección URL de inicio de sesión de BizX. Por ejemplo, si la dirección URL de inicio de sesión de BizX `organization.successfactors.com/sf/start/#/login` es la dirección URL del host es `organization.successfactors.com` .

    **Dirección URL de Learning cliente:** puede obtener esto desde la dirección URL del módulo de dominio de aprendizaje. Por ejemplo, si la dirección URL del dominio de aprendizaje es la dirección `organization.scdemo.successfactors.com/learning/...` URL Learning destino es `organization.scdemo.successfactors.com` .

    **Clave privada PGP:** clave privada PGP para descifrado, que es toda la sección entre BEGIN PGP PRIVATE KEY BLOCK y END PGP PRIVATE KEY BLOCK. Tendrás que copiar la clave exactamente como se ha generado; no quites nuevos caracteres de línea.

    Frase de contraseña de clave privada **PGP:** deberá obtener este valor del administrador de TI o del equipo que proporciona la clave PGP.

    **Id. de** empresa: inicie sesión en el portal de SuccessFactors. Seleccione el icono de perfil y, a continuación, **seleccione Mostrar versión Configuración**. Puede ver su identificador de empresa aquí.

    ![Imagen del icono de perfil con Mostrar versión Configuración seleccionado.](../media/learning/sf-3.png)
        
    ![Imagen del panel de configuración de versión.](../media/learning/sf-1.png)

4. Seleccione **Guardar** para activar el contenido de SuccessFactors en Aprendizaje Microsoft Viva. Puede haber un retraso antes de que el contenido esté disponible en Viva Learning.

>[!Note]
> Los cursos successFactors empezarán a aparecer en Viva Learning 7 días después de la instalación correcta.

>[!Note]
> Todos los usuarios de una organización podrán descubrir todos los cursos específicos del espacio empresarial, pero solo podrán acceder a los cursos a los que tienen acceso y consumir. La detección de contenido específico del usuario está planeada para futuras versiones.

>[!NOTE]
>Los metadatos del espacio empresarial se almacenan de forma centralizada en nuestros almacenes de datos y no se almacenan en almacenes de datos específicos geográficamente.

>[!NOTE]
>Actualmente, todos los usuarios de una organización pueden descubrir todos los cursos específicos del inquilino, pero solo podrán consumir los cursos a los que tienen acceso. La detección de contenido específica del usuario basada en roles y permisos está planeada para futuras versiones.
