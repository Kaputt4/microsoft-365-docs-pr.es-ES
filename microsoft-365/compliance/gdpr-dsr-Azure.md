---
title: Solicitudes de interesados de Azure para el RGPD
description: ''
keywords: Microsoft 365, Microsoft 365 Education, documentación de Microsoft 365, RGPD
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: 7a294893d609747b5ab36c66319427608462b451
ms.sourcegitcommit: 6e2a54ec395eaef4c4658ca52322c3d0f184ca02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "34698342"
---
# <a name="azure-data-subject-requests-for-the-gdpr"></a>Solicitudes de interesados de Azure para el RGPD

## <a name="introduction-to-data-subject-requests-dsrs"></a>Introducción a las solicitudes de interesados

El [Reglamento de protección de datos (RGPD)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) de la Unión Europea ofrece derechos a las personas (que se denominan *interesados* en el reglamento) para administrar los datos personales recopilados por una empresa u otro tipo de agencia u organización (es decir, el *responsable de los datos* o *responsable*). Los datos personales se definen de forma muy amplia según el RGPD como cualquier dato relacionado con una persona física, ya sea identificada o identificable. El RGPD ofrece a los interesados derechos específicos sobre sus datos personales, como la obtención de copias de sus datos, la solicitud de correcciones, impedir su procesamiento o eliminación, o el envío en formato electrónico para transferirlos a otro responsable. Las solicitudes formales realizadas por un interesado a un responsable para realizar una acción con sus datos personales se denominan *solicitudes de interesado*.

Esta guía explica cómo usar productos, servicios y herramientas administrativas de Microsoft para ayudar a nuestros clientes responsables de los datos a encontrar y actuar sobre datos personales para responder solicitudes de interesado. En concreto, esto incluye cómo encontrar, acceder y actuar sobre datos personales alojados en la nube de Microsoft. Este es un breve resumen de los procedimientos descritos en esta guía:

- **Detección:** use herramientas de búsqueda y detección para encontrar con facilidad datos de clientes que puedan ser el objeto de una solicitud de derechos del titular de los datos. Después de recopilar los documentos que puedan ser el objeto de una solicitud, puede realizar una o varias de las acciones de solicitud de derechos del titular de los datos descritas en los pasos siguientes para responder a la petición. Como alternativa, puede determinar que la solicitud no cumple las directrices de respuesta a solicitudes de derechos del titular de los datos.
- **Acceso:** recupere datos personales que residan en la nube de Microsoft y, si se le pide, realice una copia para proporcionársela al titular de los datos.
- **Rectificación:** realice cambios o implemente otras acciones solicitadas en los datos personales, si corresponde.
- **Restricción:** restrinja el tratamiento de datos personales, ya sea al quitar las licencias de distintos servicios de Azure o al desactivar los servicios que quiera, siempre que sea posible. También puede quitar los datos de la nube de Microsoft y conservarlos de forma local o en otra ubicación.
- **Eliminación:** elimine de forma permanente los datos personales que residen en la nube de Microsoft.
- **Exportación:** envíe una copia electrónica (en un formato de lectura mecánica) de datos personales al titular de los datos.

Cada sección de esta guía describe los procedimientos técnicos que puede realizar una organización responsable de los datos para responder a una solicitud del interesado de datos personales en la nube de Microsoft.

## <a name="terminology"></a>Terminología

A continuación se ofrecen definiciones de términos relacionados con esta guía.

- **Poseedor:** la persona física o jurídica, entidad pública, agencia u organismo que, solo o junto a otras personas, determina los fines y los medios del procesamiento de datos personales; donde los fines y los medios de dicho procesamiento están determinados por la ley de la Unión Europea o de los Estados miembros, el poseedor o los criterios específicos para su designación pueden estar proporcionados por la ley de la Unión Europea o de los Estados miembros.
- **Datos personales y titular de los datos:** cualquier información sobre una persona física identificada o identificable (“titular de los datos”); una persona física identificable es una que puede identificarse, directa o indirectamente, especialmente en referencia a un identificador, con un nombre, un número de identificación, datos de ubicación, un identificador en línea o uno o más factores específicos físicos, fisiológicos, genéticos, mentales, económicos, culturales o de identidad social de esa persona física.
- **Procesador:** persona física o jurídica, entidad pública, agencia u otro organismo que procesa datos personales en nombre del poseedor.
- **Los datos de clientes:** todos los datos, (incluidos todos los archivos de texto, sonido, vídeo o imagen, y software) proporcionados a Microsoft por un cliente (o en su representación) mediante el uso del servicio empresarial. En los datos de clientes, se incluye (1) información de identificación personal de los usuarios finales (por ejemplo, nombres de usuario e información de contacto en Azure Active Directory) y contenido del cliente cargado o creado por clientes en servicios específicos (por ejemplo, el contenido del cliente en una cuenta de Azure Storage, contenido del cliente de Azure SQL Database, o la imagen de la máquina virtual de un cliente en Azure Virtual Machines).
- **Registros generados por el sistema:** registros y datos relacionados generados por Microsoft que permiten a Microsoft prestar servicios empresariales a los usuarios. Los registros generados por el sistema contienen principalmente datos anonimiz*Registros generados por el sistema: registros y datos relacionados generados por Microsoft que permiten a Microsoft prestar servicios empresariales a los usuarios. Los registros generados por el sistema contienen principalmente datos anonimizados parcialmente, como identificadores únicos (por lo general, un número generado por el sistema que no se puede usar para identificar a una persona, pero que se usa para prestar servicios empresariales a los usuarios). Los registros generados por el sistema también pueden contener información identificable sobre los usuarios finales, como un nombre de usuario.

## <a name="how-to-use-this-guide"></a>Uso de esta guía

Esta guía consta de dos partes:

- **Parte 1: Responder a solicitudes de interesados de clientes**: la primera parte de esta guía describe cómo acceder, corregir, restringir, eliminar y exportar datos desde las aplicaciones en las que se han creado. Esta sección detalla cómo ejecutar la solicitud de interesado con el contenido de cliente y también con la información identificable de los usuarios finales.
- **Parte 2: Responder a solicitudes de interesados para registros generados por el sistema**: al usar los servicios de empresa de Microsoft, Microsoft genera información conocida como registros generados por el sistema para proporcionar el servicio. La parte 2 de esta guía explica cómo acceder, eliminar y exportar esta información para Azure.

## <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-service-accounts"></a>Comprender las solicitudes de interesados para Azure Active Directory y cuentas de servicio de Microsoft

Al plantear servicios proporcionados a clientes empresariales, siempre debe entenderse la ejecución de solicitudes de interesados en el contexto de un inquilino específico de Azure Active Directory (AAD). En concreto, este siempre se ejecuta en un inquilino AAD determinado. Si un usuario forma parte de varios inquilinos, es importante destacar que una solicitud de interesado *solo* se ejecuta en el contexto del inquilino específico que ha recibido la solicitud. Esto es importante para comprender que la ejecución de una solicitud de interesado por parte de un cliente empresarial **no** afecta a los datos de otro cliente empresarial adyacente.

Lo mismo se aplica a las cuentas de servicio de Microsoft (MSA) en el contexto de los servicios proporcionados por un cliente empresarial: la ejecución de una solicitud de interesado de una cuenta MSA *asociada a un cliente AAD* **solo** estará relacionada con los datos del cliente. Además, es importante comprender lo siguiente al gestionar cuentas MSA en un cliente:

- Si un usuario MSA crea una suscripción de Azure, la suscripción se tratará como si fuera un inquilino AAD. Por lo tanto, las solicitudes de interesado se rastrean en el interior del cliente tal y como se ha descrito anteriormente.
- Si se elimina una suscripción de Azure creada con una cuenta MSA, esta última **no se verá afectada**.Como se indicó anteriormente, las solicitudes de interesado que se ejecutan en la suscripción de Azure se limitan al ámbito del mismo inquilino.

Las solicitudes de interesados en una cuenta de MSA, **fuera de un determinado inquilino**, se ejecutan mediante el panel de privacidad del consumidor. Consulte la Guía de solicitud de datos de Windows para obtener más información.

## <a name="part-1-dsr-guide-for-customer-data"></a>Parte 1: Guía de solicitud de interesado para datos de cliente

### <a name="executing-dsrs-against-customer-data"></a>Ejecutar solicitudes de interesado en datos de cliente

Microsoft proporciona la capacidad de acceder a determinados datos de cliente, eliminarlos y exportarlos a través del Azure Portal y también directamente a través de interfaces de programación de aplicaciones (API) o interfaces de usuario (UI) ya existentes para servicios específicos (también denominados *experiencias de producto*). Los detalles al respecto de estas experiencias de producto se describen en la documentación de referencia de sus respectivos servicios.

>[!IMPORTANT]  
> Los servicios compatibles con solicitudes de interesado en el producto requieren el uso directo de una interfaz de programación de aplicaciones (API) o de una interfaz de usuario (UI) del servicio, que describa las operaciones CRUD (crear, leer, actualizar y eliminar) aplicables. Por lo tanto, la ejecución de la solicitud de interesado en un servicio específico debe realizarse además con la ejecución de una solicitud de interesado en Azure Portal para completar toda la solicitud de un interesado. Consulte la documentación de referencia de los servicios específicos para obtener más detalles.

### <a name="step-1-discover"></a>Paso 1: Detección

El primer paso para responder a una solicitud de derechos del interesado es buscar los datos de cliente que sean el objeto de la solicitud. Este primer paso (buscar y revisar los datos personales que sean objeto de la solicitud) le permitirá determinar si la solicitud del titular de los datos cumple con los requisitos de la organización para aceptarla o rechazarla. Por ejemplo, después de encontrar y revisar los datos personales, puede determinar que la solicitud no cumple los requisitos de su organización porque al llevarse a cabo puede afectar negativamente los derechos y libertades de terceros.

Después de encontrar los datos, puede realizar la acción específica para satisfacer la solicitud del interesado.

[Azure Active Directory](https://azure.microsoft.com/services/active-directory/) el servicio de administración de identidad y directorio multiinquilino basado en la nube de Microsoft. Puede encontrar información de identificación personal de los usuarios finales, como perfiles de usuario de clientes y empleados e información de trabajo de usuarios que contenga datos personales en su entorno [Azure Active Directory](https://azure.microsoft.com/services/active-directory/) (AAD) usando el [Azure Portal](https://portal.azure.com/).

Esto es útil si desea buscar o cambiar datos personales de un usuario específico. También puede agregar o cambiar perfiles de usuario e información de trabajo. Debe iniciar sesión con una cuenta de administrador global para el directorio.

#### <a name="how-do-i-locate-or-view-user-profile-and-work-information"></a>¿Cómo buscar o ver perfiles de usuario e información de trabajo?

1. Inicie sesión en [Azure Portal](https://portal.azure.com/) con una cuenta de administrador global para el directorio.

2. Seleccione **Todos los servicios**, escriba **Usuarios y grupos** en el cuadro de texto y, después, seleccione **Entrar**.

     ![Seleccionar todos los servicios](media/azure-dsr_image3.png)

3. En la hoja **Usuarios y grupos**, seleccione **Usuarios**.

     ![Seleccionar usuarios](media/azure-dsr_image9.png)

4. En la hoja **Usuarios y grupos: Usuarios**, seleccione un usuario de la lista y, a continuación, en el módulo para el usuario seleccionado, seleccione **Perfil** para ver la información de perfil de usuario que puede contener datos personales.

    ![Seleccionar perfil](media/azure-dsr_image5.png)

5. Si necesita agregar o cambiar la información de perfil de usuario, puede hacerlo y, a continuación, en la barra de comandos, seleccione **Guardar.**

#### <a name="service-specific-interfaces"></a>Interfaces específicas del servicio

Microsoft proporciona la capacidad de detectar datos de clientes directamente a través de interfaces de programación de aplicaciones (API) o interfaces de usuario (UI) ya existentes para servicios específicos. Los detalles se describen en la documentación de referencia de los respectivos servicios, que describen las operaciones CRUD (creación, lectura, actualización y eliminación) aplicables.

### <a name="step-2-access"></a>Paso 2: Acceso

Cuando haya encontrado los datos de clientes que contengan datos personales que puedan responder a una solicitud de interesado, depende de usted y de su organización decidir qué datos proporcionar al interesado. Puede proporcionarle una copia del documento, una versión redactada o una captura de pantalla con las porciones que considere adecuado compartir. Para cada una de estas respuestas a una petición de acceso, deberá recuperar una copia del documento u otro objeto que contenga los datos de respuesta.

Al proporcionar una copia al interesado, deberá quitar o censurar información personal sobre otros interesados, además de la información confidencial.

#### <a name="azure-active-directory"></a>Azure Active Directory

Microsoft ofrece un portal y experiencias de producto que proporcionan al administrador de espacio empresarial del cliente empresarial la capacidad de gestionar peticiones de acceso de interesado. Las peticiones de acceso de interesado permiten acceder a los datos personales del usuario, incluyendo (a) información de identificación sobre un usuario final y (b) registros generados por el servicio.

#### <a name="service-specific-interfaces"></a>Interfaces específicas del servicio

Microsoft proporciona la capacidad de detectar datos de clientes directamente a través de interfaces de programación de aplicaciones (API) o interfaces de usuario (UI) ya existentes para servicios específicos. Los detalles se describen en la documentación de referencia de los respectivos servicios, que describen las operaciones CRUD (creación, lectura, actualización y eliminación) aplicables.

### <a name="step-3-rectify"></a>Paso 3: Rectificar

Si un interesado le ha solicitado rectificar los datos personales que se encuentran en los datos de su organización, su organización y usted deberán determinar si es adecuado acceder a dicha petición. Rectificar los datos puede requerir llevar a cabo acciones como editar, censurar o eliminar datos personales de un documento u otro tipo de elemento. La forma más expeditiva de hacerlo para el Soporte técnico de Microsoft y FastTrack es la proporcionada a continuación.

#### <a name="azure-active-directory"></a>Azure Active Directory

Los clientes empresariales tienen la capacidad de administrar solicitudes de interesado de rectificación, incluidas características de edición limitadas por la naturaleza de un servicio específico de Microsoft. Como procesador datos, Microsoft no ofrece la posibilidad de corregir los registros generados por el sistema, pues reflejan actividades y constituyen el historial de los eventos de los servicios de Microsoft. Con respecto a Azure Active Directory, existen características de edición limitadas para corregir la información de identificación personal sobre el usuario, tal y como se describe más adelante.

##### <a name="azure-active-directory-rectifycorrect-inaccurate-or-incomplete-personal-data"></a>Azure Active Directory: rectificar y corregir datos personales inexactos o incompletos

Puede corregir, actualizar o eliminar información de identificación personal sobre los usuarios finales, como clientes y los perfiles de usuario de empleado e información de trabajo que contiene datos personales, como nombre de usuario, puesto de trabajo, dirección o número de teléfono, en el entorno [Azure Active Directory](https://azure.microsoft.com/services/active-directory/) (AAD) usando [Azure Portal](https://portal.azure.com/). Debe iniciar sesión con una cuenta de administrador global para el directorio.

###### <a name="how-do-i-correct-or-update-user-profile-and-work-information-in-azure-active-directory"></a>¿Cómo corregir o actualizar el perfil de usuario y la información de trabajo en Azure Active Directory?

1. Inicie sesión en [Azure Portal](https://portal.azure.com/) con una cuenta de administrador global para el directorio.

2. Seleccione **Todos los servicios**, escriba **Usuarios y grupos** en el cuadro de texto y, después, seleccione **Entrar**.

    ![Seleccionar todos los servicios](media/azure-dsr_image3.png)

3. En la hoja **Usuarios y grupos**, seleccione **Usuarios**.

    ![Seleccionar usuarios](media/azure-dsr_image9.png)

4. En la hoja **Usuarios y grupos: Usuarios**, seleccione un usuario de la lista y, a continuación, en el módulo para el usuario seleccionado, seleccione **Perfil** para ver la información que debe corregirse o actualizarse.

    ![Seleccionar perfil](media/azure-dsr_image5.png)

5. Corrija o actualice la información y, a continuación, en la barra de comandos, seleccione **Guardar.**

6. En la hoja del usuario seleccionado, elija **Información de trabajo** para ver la información de trabajo del usuario que requiera corregirse o actualizarse.

    ![Seleccionar información de trabajo](media/azure-dsr_image4.png)

7. Corrija o actualice la información de trabajo del usuario y, a continuación, en la barra de comandos, seleccione **Guardar.**

#### <a name="service-specific-interfaces"></a>Interfaces específicas del servicio

Microsoft proporciona la capacidad de detectar datos de clientes directamente a través de interfaces de programación de aplicaciones (API) o interfaces de usuario (UI) ya existentes para servicios específicos. Los detalles se describen en la documentación de referencia de los respectivos servicios, que describen las operaciones CRUD (creación, lectura, actualización y eliminación) aplicables.

### <a name="step-4-restrict"></a>Paso 4: Restringir

Los interesados pueden pedir que restrinja el procesamiento de sus datos personales. Proporcionamos tanto Azure Portal como interfaces de programación de aplicaciones (API) o interfaces de usuario (IU) ya existentes. Estas experiencias proporcionan al administrador del cliente empresarial la capacidad de administrar solicitudes de interesado a través de una combinación de exportación y eliminación de datos. Un cliente puede (1) exportar una copia electrónica de los datos personales del usuario, incluyendo (a) cuentas, (b) registros generados por el sistema y (c) registros asociados, seguido de (2) la eliminación de la cuenta y datos asociados que residen en los sistemas de Microsoft.

### <a name="step-5-delete"></a>Paso 5: Eliminar

El “derecho a la eliminación” de datos personales de los datos de cliente de una organización es una protección clave en el RGPD. Cuando se quitan datos personales, esto conlleva quitar todos los datos personales y los registros generados por el sistema, salvo la información de registros de auditoría. Cuando un usuario se **elimina temporalmente** (ver los detalles a continuación), la cuenta se deshabilita durante 30 días. Si no se lleva a cabo ninguna otra acción durante este periodo de 30 días, el usuario se **elimina de forma permanente** (consulte los detalles a continuación). Al **eliminar de forma permanente** una cuenta de usuario, la cuenta de usuario, los datos personales y los registros generados por el sistema se eliminan en un plazo adicional de 30 días. Si un administrador de espacios empresariales emite inmediatamente una **eliminación permanente**, se eliminan la cuenta del usuario, los datos personales y los registros generados por el sistema en un plazo de 30 días desde la emisión.

> [!IMPORTANT]
> Debe ser un administrador del espacio empresarial para eliminar un usuario de en dicho espacio.

#### <a name="delete-a-user-and-associated-data-through-the-azure-portal"></a>Eliminar un usuario y los datos asociados a través de Azure Portal

Después de recibir una solicitud de eliminación por parte de un interesado, puede usar Azure Portal para eliminar tanto un usuario como la información personal asociada, además de los registros generados por el sistema.

Eliminar datos también supone la eliminación del usuario del inquilino. Los usuarios sufren una eliminación temporal inicial, lo que significa que un administrador de inquilinos puede recuperar la cuenta en los 30 días siguientes a la eliminación temporal. Después de 30 días, se elimina la cuenta automáticamente y de forma permanente del inquilino. Antes de que transcurran dichos 30 días, puede eliminar manualmente de la Papelera de reciclaje un usuario eliminado temporalmente.

Este es el proceso de alto nivel para eliminar usuarios de su inquilino.

1. Vaya a Azure Portal y encuentre el usuario.

2. Eliminar el usuario. Al eliminar el usuario al principio, la cuenta del usuario se envía a la Papelera de reciclaje. **En este momento, el usuario se encuentra eliminado temporalmente, lo que significa que se deshabilita la cuenta, pero no se elimina de Azure Active Directory.**

3. Vaya a la lista de usuarios eliminados recientemente y elimine al usuario de forma permanente. **En este momento el usuario se elimina permanentemente, lo que significa que la cuenta se ha depuración de Azure Active Directory**

###### <a name="to-delete-a-user-from-an-azure-tenant"></a>Para eliminar un usuario de un inquilino de Azure

1. Abra Azure Portal, seleccione la hoja **Azure Active Directory** y seleccione **Usuarios**.

    Aparece la hoja **Usuario, Todos los usuarios**.

    ![Encontrar al usuario](media/azure-dsr_image8.png)

2. Active la casilla situada junto al usuario que desea eliminar, seleccione **Eliminar usuario** y después seleccione **Sí** en el cuadro que le pregunta si desea eliminar el usuario.

    ![Administración de usuarios](media/azure-dsr_image9.png)

3. En el cuadro **Mostrar** de lista desplegable, seleccione **Usuarios eliminados recientemente**.

    ![Ver perfil del usuario](media/azure-dsr_image10.png)

4. Seleccione de nuevo el nombre de usuario, seleccione **Eliminar permanentemente** y después seleccione **Sí** en el cuadro que le pregunta si está seguro.

>[!IMPORTANT]  
>Tenga en cuenta que al hacer clic en **Sí** eliminará el usuario y todos los datos y registros generados por el sistema asociados de forma permanente e irrevocable. Si hace esto por error, tendrá que volver a agregar al usuario al cliente de forma manual. Los datos asociados y los registros generados por el sistema no se pueden recuperar.

   ![Ver información de trabajo del usuario](media/azure-dsr_image11.png)

#### <a name="service-specific-interfaces"></a>Interfaces específicas del servicio

Microsoft proporciona la capacidad de detectar datos de clientes directamente a través de interfaces de programación de aplicaciones (API) o interfaces de usuario (UI) ya existentes para servicios específicos. Los detalles se describen en la documentación de referencia de los respectivos servicios, que describen las operaciones CRUD (creación, lectura, actualización y eliminación) aplicables.

## <a name="step-6-export"></a>Paso 6: Exportar

El "derecho de portabilidad de datos" permite a un interesado solicitar una copia de sus datos personales en formato electrónico (es decir, un “formato estructurado, de uso común, compatible con dispositivos electrónicos e interoperable”) que pueda transmitirse a otro responsable de los datos. Azure soporta esto al permitir que su organización exporte los datos en formato nativo JSON a su contenedor de almacenamiento de Azure especificado.

>[!IMPORTANT]
>Debe ser un administrador de espacios empresariales para exportar datos de usuario del espacio empresarial.

### <a name="azure-active-directory"></a>Azure Active Directory

Con respecto a los datos de clientes, Microsoft ofrece un portal y las experiencias del producto para proporcionar al administrador de inquilinos del cliente empresarial la capacidad de exportar solicitudes de información de identificación sobre un usuario final.

### <a name="service-specific-interfaces"></a>Interfaces específicas del servicio

Microsoft proporciona la capacidad de detectar datos de clientes directamente a través de interfaces de programación de aplicaciones (API) o interfaces de usuario (UI) ya existentes para servicios específicos. Los detalles se describen en la documentación de referencia de los respectivos servicios, que describen las operaciones CRUD (creación, lectura, actualización y eliminación) aplicables.

## <a name="part-2-system-generated-logs"></a>Parte 2: Registros generados por el sistema

Microsoft también le proporciona la capacidad de acceso, eliminación y exportación de determinados registros generados por el sistema asociados con el uso de un usuario de Azure.

>[!IMPORTANT]
> No se admite la capacidad para restringir o rectificar registros generados por el sistema. Los registros generados por el sistema constituyen acciones realizadas en la nube de Microsoft y datos de diagnóstico y modificar este tipo de datos comprometería los registros históricos de acciones, lo que aumentaría el fraude y los riesgos a la seguridad.

### <a name="executing-dsrs-against-system-generated-logs"></a>Ejecutar solicitudes de interesado en registros generados por el sistema.

Microsoft proporciona la capacidad de acceso, eliminación y exportación de determinados registros generados por el sistema a través de Azure Portal y también directamente a través de interfaces de programación o interfaces de usuario para obtener servicios específicos. Los detalles se describen en la documentación de referencia de los servicios correspondientes.

>[!IMPORTANT]  
> Los servicios compatibles con solicitudes de interesado en el producto requieren el uso directo de una interfaz de programación de aplicaciones (API) o de una interfaz de usuario (UI). Por lo tanto, la ejecución de la solicitud de interesado en un producto **debe realizarse además con la ejecución de una solicitud de interesado en Azure Portal para completar toda la solicitud de un interesado. Consulte la documentación de referencia de los servicios específicos para obtener más detalles.**

### <a name="step-1-access"></a>Paso 1: Acceso

El administrador de inquilinos es la única persona de su organización con acceso a los registros generados por el sistema asociados con el uso de un usuario determinado de Azure. Los datos que se recuperan de una solicitud de acceso se ofrecen en un formato legible y se incluirán en los archivos que permiten al usuario saber qué servicios están asociados a los datos. Como se indicó anteriormente, los datos recuperados no incluirán datos que pueden poner en peligro la seguridad del servicio.

#### <a name="azure-active-directory"></a>Azure Active Directory

Microsoft ofrece un portal y experiencias de producto que proporcionan al administrador espacio empresarial del cliente empresarial la capacidad de gestionar peticiones de acceso de interesado. Las peticiones de acceso de interesado permiten acceder a los datos personales del usuario, incluyendo (a) información de identificación sobre un usuario final y (b) registros generados por el servicio. El proceso es idéntico al descrito en la sección de Azure Active Directory de la Parte 1, Paso 2: Acceso.

#### <a name="service-specific-interfaces"></a>Interfaces específicas del servicio

Microsoft proporciona la capacidad de detectar datos de clientes directamente a través de interfaces de programación de aplicaciones (API) o interfaces de usuario (UI) ya existentes para servicios específicos. Los detalles se describen en la documentación de referencia de los respectivos servicios, que describen las operaciones CRUD (creación, lectura, actualización y eliminación) aplicables.

### <a name="step-2-delete"></a>Paso 2: Eliminar

El Administrador de inquilinos es la única persona de su organización que puede ejecutar una petición de eliminación de una solicitud de interesado para un usuario concreto en un inquilino de Azure.

#### <a name="azure-active-directory"></a>Azure Active Directory

Microsoft ofrece tanto un portal como experiencias de producto para proporcionar al administrador de inquilinos del cliente empresarial la capacidad de administrar peticiones de eliminación de solicitudes de interesado. Este proceso es igual al descrito en la sección dedicada a la eliminación de un usuario y sus datos asociados mediante Azure Portal de la Parte 1, paso 5: Eliminar

#### <a name="service-specific-interfaces"></a>Interfaces específicas del servicio

Microsoft proporciona la capacidad de detectar datos de clientes directamente a través de interfaces de programación de aplicaciones (API) o interfaces de usuario (UI) ya existentes para servicios específicos. Los detalles se describen en la documentación de referencia de los respectivos servicios, que describen las operaciones CRUD (creación, lectura, actualización y eliminación) aplicables.

### <a name="step-3-export"></a>Paso 3: Exportar

El administrador de inquilinos es la única persona de su organización con acceso a los registros generados por el sistema asociados con el uso de un usuario determinado de Azure. Los datos que se recuperan de una solicitud de exportación se ofrecen en un formato legible y se incluirán en los archivos que permiten al usuario saber qué servicios están asociados a los datos. Como se indicó anteriormente, los datos recuperados no incluirán datos que pueden poner en peligro la seguridad o estabilidad del servicio.

#### <a name="export-system-generated-logs-using-the-azure-portal"></a>Exportar registros generados por el sistema mediante Azure Portal

Después de recibir una solicitud de exportación para un interesado, puede usar Azure Portal para exportar registros generados por el sistema asociados a un usuario determinado.

Este es el proceso de alto nivel para exportar datos de su inquilino.

1. Vaya a Azure Portal y cree una solicitud de exportación en nombre del usuario.
2. Exporte los datos y envíe el archivo al usuario.

###### <a name="to-export-a-users-info-from-an-azure-tenant"></a>Para exportar la información de un usuario de un inquilino de Azure

1. Abra Azure Portal, seleccione **Todos los servicios**, escriba *directiva* en el filtro y seleccione **Directiva**.

     ![Filtro Todos los servicios ](media/azure-dsr_image12.png)

2. En la hoja **Directiva**, seleccione **Privacidad del usuario**, a continuación **Administrar las solicitudes de usuario** y después **Agregar solicitud de exportación**.

    ![Agregar solicitud de exportación ](media/azure-dsr_image13.png)

3. Completar la **solicitud de exportación de datos**:

    ![Nueva solicitud de exportación de datos](media/azure-dsr_image14.png)

- **Usuario.** Escriba la dirección de correo electrónico del usuario de Azure Active Directory que solicita la exportación.
- **Suscripción.** Seleccione la cuenta que usa para informar del uso de recursos y para facturar por servicios. Esta también es la ubicación de la cuenta de almacenamiento de Azure.
- **Cuenta de almacenamiento.** Seleccione la ubicación de su Azure Storage (Blob). Para obtener más información, consulte el artículo [Introducción a Microsoft Azure Storage, almacenamiento de blobs](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage).
- **Contenedor.** Cree un nuevo contenedor (o seleccione uno existente) como la ubicación de almacenamiento para los datos de privacidad exportados del usuario.

4. Seleccione **Crear**.

La solicitud de exportación pasa al estado **Pendiente**. Puede ver el informe de estado en la hoja **Privacidad del usuario: Información general**.

>[!IMPORTANT]  
>Como los datos personales pueden proceder de varios sistemas, es posible que el proceso de exportación tarde hasta un mes en completarse.

#### <a name="service-specific-interfaces"></a>Interfaces específicas del servicio

Microsoft proporciona la capacidad de detectar datos de clientes directamente a través de interfaces de programación de aplicaciones (API) o interfaces de usuario (UI) ya existentes para servicios específicos. Los detalles se describen en la documentación de referencia de los respectivos servicios, que describen las operaciones CRUD (creación, lectura, actualización y eliminación) aplicables.

### <a name="notify-about-exporting-or-deleting-issues"></a>Notificar sobre los problemas de exportación o eliminación

Si tiene problemas al exportar o eliminar datos desde Azure Portal, vaya a la hoja **Ayuda + soporte** de Azure Portal y envíe un nuevo vale en **Administración de suscripción > Otras solicitudes de seguridad y cumplimiento > Solicitudes de RGPD y la hoja de privacidad**.

## <a name="learn-more"></a>Más información

- [Centro de confianza de Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)