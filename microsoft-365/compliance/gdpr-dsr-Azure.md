---
title: Solicitudes de titulares de los datos de Azure para el RGPD y la CCPA
description: Aprenda a utilizar los productos, servicios y herramientas de administración de Microsoft para encontrar y actuar sobre los datos personales para responder a los DSR.
keywords: Microsoft 365, Educación de Microsoft 365, documentación de Microsoft 365, RGPD, CCPA
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
hideEdit: true
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b22baa48293e48567d801227996d080e8ee1cce2
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2020
ms.locfileid: "47416654"
---
# <a name="azure-data-subject-requests-for-the-gdpr-and-ccpa"></a>Solicitudes de titulares de los datos de Azure para el RGPD y la CCPA

## <a name="introduction-to-data-subject-requests-dsrs"></a>Introducción a las solicitudes de interesados

El [Reglamento de protección de datos (RGPD)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) de la Unión Europea ofrece derechos a las personas (que se denominan *interesados* en el reglamento) para administrar los datos personales recopilados por una empresa u otro tipo de agencia u organización (es decir, el *responsable de los datos* o simplemente *responsable*). Los datos personales se definen de forma muy amplia según el RGPD como cualquier dato relacionado con una persona física, ya sea identificada o identificable. El RGPD ofrece a los interesados derechos específicos sobre sus datos personales, como la obtención de copias de sus datos, la solicitud de correcciones, impedir su procesamiento o eliminación, o el envío en formato electrónico para transferirlos a otro responsable. Las solicitudes formales realizadas por un interesado a un responsable para realizar una acción con sus datos personales se denominan *solicitudes de interesado* DSR, por sus siglas en inglés.

De forma similar, la Ley de Privacidad del Consumidor de California (CCPA, por sus siglas en inglés), ofrece derechos y obligaciones de privacidad a los consumidores de California, incluyendo derechos similares a los Derechos del Interesado de GDPR, como el derecho de eliminar, acceder y recibir (portabilidad) su información personal. La CCPA también prevé casos de divulgación de información, protecciones contra la discriminación en el ejercicio de derechos y requisitos de "cancelación/suscripción" para ciertas transferencias de datos clasificadas como "ventas". Las ventas se definen de forma amplia para incluir el uso compartido de datos con ánimo de lucro. Para obtener más información sobre la CCPA, consulte la [Ley de privacidad de los consumidores California](offering-ccpa.md) y las [Preguntas más frecuentes sobre la privacidad del consumidor de California](ccpa-faq.md).

La guía trata sobre cómo utilizar los productos, servicios y herramientas administrativas de Microsoft para ayudar a nuestros clientes controladores a encontrar y actuar sobre los datos personales para responder a los DSR. Específicamente, esto incluye cómo encontrar, acceder y actuar sobre los datos personales que residen en la nube de Microsoft. Este es un breve resumen de los procesos descritos en esta guía:

- **Búsqueda**: use herramientas de búsqueda y detección para encontrar más fácilmente los datos personales que pueden ser objeto de una solicitud de DSR. Una vez recopilados los documentos de respuesta, puede realizar una o varias de las acciones de DSR siguientes para responder a la solicitud. También puede determinar que la solicitud no cumple con las directrices de la organización para responder a las solicitudes de sujeto de datos.
- **Acceso:** recupere datos personales que residan en la nube de Microsoft y, si se le pide, realice una copia para proporcionársela al titular de los datos.
- **Rectificación:** realice cambios o implemente otras acciones solicitadas en los datos personales, si corresponde.
- **Restricción:** restrinja el tratamiento de datos personales, ya sea al quitar las licencias de distintos servicios de Azure o al desactivar los servicios que quiera, siempre que sea posible. También puede quitar datos de la nube de Microsoft y conservarlos de manera local o en otra ubicación.
- **Eliminación:** elimine de forma permanente los datos personales que residen en la nube de Microsoft.
- **Exportar o recibir (portabilidad):** envíe una copia electrónica (en un formato legible por máquina) de datos o información personal al titular de los datos. La información personal bajo la CCPA es cualquier información relacionada con una persona identificada o identificable. No hay distinción entre los roles privados, públicos o laborales de una persona. La definición de la CCPA de la "información personal" es a grandes rasgos similar a la que el RGPD hace de los "datos personales". Sin embargo, la CCPA también incluye datos domésticos y familiares. Para obtener más información sobre la CCPA, consulte la [Ley de Privacidad de los Consumidores California](offering-ccpa.md) y las [Preguntas más frecuentes sobre la privacidad del consumidor de California](ccpa-faq.md).

Cada sección de esta guía describe los procedimientos técnicos que puede realizar una organización responsable de los datos para responder a una solicitud del interesado de datos personales en la nube de Microsoft.

## <a name="terminology"></a>Terminología

A continuación se ofrecen definiciones de términos relacionados con esta guía.

- **Poseedor:** la persona física o jurídica, entidad pública, agencia u organismo que, solo o junto a otras personas, determina los fines y los medios del procesamiento de datos personales; donde los fines y los medios de dicho procesamiento están determinados por la ley de la Unión Europea o de los Estados miembros, el poseedor o los criterios específicos para su designación pueden estar proporcionados por la ley de la Unión Europea o de los Estados miembros.
- **Datos personales y titular de los datos:** cualquier información sobre una persona física identificada o identificable ("interesado"); una persona física identificable es una que puede identificarse, directa o indirectamente, especialmente en referencia a un identificador, con un nombre, un número de identificación, datos de ubicación, un identificador en línea o uno o más factores específicos físicos, fisiológicos, genéticos, mentales, económicos, culturales o de identidad social de esa persona física.
- **Procesador:** persona física o jurídica, entidad pública, agencia u otro organismo que procesa datos personales en nombre del poseedor.
- **Datos de cliente:** todos los datos, incluidos todos los archivos de texto, sonido, vídeo o imagen, y software, proporcionados a Microsoft por un cliente o en su representación mediante el uso del servicio empresarial. Los datos del cliente incluyen tanto (1) información identificable de los usuarios finales (por ejemplo, nombres de usuario e información de contacto en Azure Active Directory) como el contenido del cliente que un cliente carga o crea en servicios específicos (por ejemplo, el contenido del cliente en una cuenta de Azure Storage, el contenido del cliente de Azure SQL Database o la imagen de la máquina virtual de un cliente en máquinas virtuales Azure).
- **Registros generados por el sistema:** registros y datos relacionados generados por Microsoft que ayudan a Microsoft a proporcionar servicios empresariales a los usuarios. Los registros generados por el sistema contienen principalmente datos pseudonimizados, como identificadores únicos (por lo general, un número generado por el sistema que se usa para ofrecer los servicios a los usuarios, pero no puede identificar a un individuo). Los registros generados por el sistema también pueden contener información identificable sobre los usuarios finales, como un nombre de usuario.

## <a name="how-to-use-this-guide"></a>Uso de esta guía

Esta guía consta de dos partes:

- **Parte 1: responda a las solicitudes de los datos de los clientes:** En la parte 1 de esta guía se explica cómo tener acceso a los datos, rectificarlos, restringirlos, eliminarlos y exportarlos desde aplicaciones en las que haya creado datos. En esta sección, se explica cómo ejecutar DSRs en el contenido de los clientes y también la información que puede identificar los usuarios finales.
- **Parte 2: Responder a las solicitudes de los sujetos de datos para los registros generados por el sistema:** Cuando se utilizan los servicios empresariales de Microsoft, Microsoft genera cierta información, conocida como registros generados por el sistema, con el fin de proporcionar el servicio. En la parte 2 de esta guía se explica cómo tener acceso, eliminar y exportar este tipo de información para Azure.

## <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-service-accounts"></a>Comprender las solicitudes de los interesados para Azure Active Directory y las cuentas de servicio de Microsoft

Al plantear servicios proporcionados a clientes empresariales, siempre debe entenderse la ejecución de solicitudes de interesados en el contexto de un inquilino específico de Azure Active Directory (AAD). En concreto, este siempre se ejecuta en un inquilino AAD determinado. Si un usuario forma parte de varios inquilinos, es importante destacar que una solicitud de interesado *solo* se ejecuta en el contexto del inquilino específico que ha recibido la solicitud. Esto es importante para comprender que la ejecución de una solicitud de interesado por parte de un cliente empresarial **no** afecta a los datos de otro cliente empresarial adyacente.

Lo mismo se aplica a las cuentas de servicio de Microsoft (MSA) en el contexto de los servicios proporcionados por un cliente empresarial: la ejecución de una solicitud de interesado de una cuenta MSA *asociada a un cliente AAD* **solo** estará relacionada con los datos del cliente. Además, es importante comprender lo siguiente al gestionar cuentas MSA en un cliente:

- Si un usuario MSA crea una suscripción de Azure, la suscripción se tratará como si fuera un inquilino AAD. Por lo tanto, las solicitudes de interesado se rastrean en el interior del cliente tal y como se ha descrito anteriormente.
- Si se elimina una suscripción de Azure creada con una cuenta MSA, esta última **no se verá afectada**.Como se indicó anteriormente, las solicitudes de interesado que se ejecutan en la suscripción de Azure se limitan al ámbito del mismo inquilino.

Las solicitudes de interesados en una cuenta de MSA, **fuera de un determinado inquilino**, se ejecutan mediante el panel de privacidad del consumidor. Consulte la Guía de solicitud de datos de Windows para obtener más información.

## <a name="part-1-dsr-guide-for-customer-data"></a>Parte 1: Guía de solicitud de interesado para datos de cliente

### <a name="executing-dsrs-against-customer-data"></a>Ejecutar solicitudes de interesado en datos de cliente

Microsoft ofrece la posibilidad de acceder a determinados datos de cliente, eliminarlos y exportarlos a través de Azure Portal y también directamente a través de interfaces de programación de aplicaciones (API) o interfaces de usuario (UI) existentes para servicios específicos (también denominados *experiencias de producto*). Los detalles sobre estas experiencias de producto se describen en la documentación de referencia de los servicios respectivos.

>[!IMPORTANT]  
> Los servicios que admiten DSR en el producto requieren el uso directo de una interfaz de programación de aplicaciones (API) o de una interfaz de usuario (UI) del servicio, que describa las operaciones CRUD (crear, leer, actualizar y eliminar) aplicables. Por lo tanto, la ejecución de una DSR en un servicio específico debe realizarse de manera adicional a la ejecución de una DSR en Azure Portal a fin de completar la solicitud de un interesado. Consulte la documentación de referencia de los servicios específicos para obtener más detalles.

### <a name="step-1-discover"></a>Paso 1: Detección

El primer paso para responder a una solicitud de derechos del interesado es buscar los datos de cliente que sean el objeto de la solicitud. Este primer paso (buscar y revisar los datos personales que sean objeto de la solicitud) le permitirá determinar si la solicitud del titular de los datos cumple con los requisitos de la organización para aceptarla o rechazarla. Por ejemplo, después de encontrar y revisar los datos personales en cuestión, puede determinar que la solicitud no cumple los requisitos de su organización porque al hacerlo puede afectar negativamente a los derechos y libertades de los demás.

Después de encontrar los datos, puede realizar la acción específica para satisfacer la solicitud del interesado.

[Azure Active Directory](https://azure.microsoft.com/services/active-directory/) es el directorio de Microsoft y el servicio de administración de identidades basado en la nube. Puede localizar información identificable de los usuarios finales, como perfiles de usuario de clientes y empleados e información de trabajo de los usuarios que contengan datos personales en su entorno de [Azure Active Directory](https://azure.microsoft.com/services/active-directory/) (AAD) utilizando el[ Azure Portal](https://portal.azure.com/).

Esto es particularmente útil si se desea encontrar o modificar los datos personales de un usuario específico. También puede agregar o cambiar el perfil del usuario y la información de su trabajo. Debe iniciar sesión con una cuenta que sea un administrador global del directorio.

#### <a name="how-do-i-locate-or-view-user-profile-and-work-information"></a>¿Cómo buscar o ver perfiles de usuario e información de trabajo?

1. Inicie sesión en [Azure Portal](https://portal.azure.com/) con una cuenta de administrador global para el directorio.

2. Seleccione **Azure Active Directory**.

     ![Seleccionar todos los servicios](../media/gdpr-azure-dsr-azure-portal.png)

3. Seleccione **Usuarios**.

     ![Seleccionar a los usuarios](../media/gdpr-azure-dsr-azure-all-users.png)

4. En la hoja **Todos los usuarios**, seleccione un usuario de la lista y, a continuación, en el módulo para el usuario seleccionado, seleccione **Perfil** para ver la información de perfil de usuario que puede contener datos personales.

    ![Seleccionar perfil](../media/gdpr-azure-dsr-azure-user-profile.png)

5. Si necesita agregar o cambiar la información de perfil del usuario, puede hacerlo seleccionando **Editar** en la barra de comandos y, a continuación **Guardar** después de realizar los cambios.

#### <a name="service-specific-interfaces"></a>Interfaces específicas del servicio

Microsoft proporciona la capacidad de detectar datos de clientes directamente a través de interfaces de programación de aplicaciones (API) o interfaces de usuario (UI) ya existentes para servicios específicos. Los detalles se describen en la documentación de referencia de los respectivos servicios, que describen las operaciones CRUD (creación, lectura, actualización y eliminación) aplicables.

### <a name="step-2-access"></a>Paso 2: Acceso

Una vez que haya encontrado datos de clientes que contengan datos personales que puedan corresponder a una DSR, dependerá de usted y de su organización decidir qué datos proporcionar al interesado. Puede proporcionarle una copia del documento, una versión con los datos censurados o una captura de pantalla con las porciones que considere adecuado compartir. Para cada una de estas respuestas a una solicitud de acceso, deberá recuperar una copia del documento u otro elemento que contenga los datos correspondientes.

Al proporcionar una copia al interesado, deberá quitar o censurar información personal sobre otros interesados, además de la información confidencial.

#### <a name="azure-active-directory"></a>Azure Active Directory

Microsoft ofrece tanto un portal como experiencias de productos que proporcionan al administrador del arrendatario de la empresa la capacidad de gestionar las solicitudes de acceso al DSR. Las peticiones de acceso de interesado permiten acceder a los datos personales del usuario, incluyendo (a) información de identificación sobre un usuario final y (b) registros generados por el servicio.

#### <a name="service-specific-interfaces"></a>Interfaces específicas del servicio

Microsoft proporciona la capacidad de detectar datos de clientes directamente a través de interfaces de programación de aplicaciones (API) o interfaces de usuario (UI) ya existentes para servicios específicos. Los detalles se describen en la documentación de referencia de los respectivos servicios, que describen las operaciones CRUD (creación, lectura, actualización y eliminación) aplicables.

### <a name="step-3-rectify"></a>Paso 3: Rectificar

Si un interesado le ha pedido que rectifique los datos personales que residen en los datos de su organización, usted y su organización tendrán que determinar si es apropiado aceptar la petición. La rectificación de los datos puede incluir la adopción de medidas como la edición, la redacción o la eliminación de datos personales de un documento u otro tipo o elemento. La forma más expeditiva de hacerlo para los datos de Soporte técnico de Microsoft y FastTrack se proporciona a continuación.

#### <a name="azure-active-directory"></a>Azure Active Directory

Los clientes empresariales tienen la capacidad de administrar solicitudes de interesado de rectificación, incluidas características de edición limitadas por la naturaleza de un servicio específico de Microsoft. Como procesador datos, Microsoft no ofrece la posibilidad de corregir los registros generados por el sistema, pues reflejan actividades y constituyen el historial de los eventos de los servicios de Microsoft. Con respecto a Azure Active Directory, existen características de edición limitadas para corregir la información de identificación personal sobre el usuario, tal y como se describe más adelante.

##### <a name="azure-active-directory-rectifycorrect-inaccurate-or-incomplete-personal-data"></a>Azure Active Directory: rectificar y corregir datos personales inexactos o incompletos

Usted puede corregir, actualizar o eliminar información identificable sobre los usuarios finales, como los perfiles de usuario de clientes y empleados y la información de trabajo de los usuarios que contienen datos personales, como el nombre, el cargo, la dirección o el número de teléfono del usuario, en su entorno del [Azure Active Directory](https://azure.microsoft.com/services/active-directory/)(AAD) utilizando el [Azure Portal](https://portal.azure.com/). Debe iniciar sesión con una cuenta que sea un administrador global del directorio.

###### <a name="how-do-i-correct-or-update-user-profile-and-work-information-in-azure-active-directory"></a>¿Cómo corregir o actualizar el perfil de usuario y la información de trabajo en Azure Active Directory?

1. Inicie sesión en [Azure Portal](https://portal.azure.com/) con una cuenta de administrador global para el directorio.

2. Seleccione **Azure Active Directory**.

    ![Seleccionar todos los servicios](../media/gdpr-azure-dsr-azure-portal.png)

3. Seleccione **Usuarios**.

    ![Seleccionar a los usuarios](../media/gdpr-azure-dsr-azure-all-users.png)

4. En la hoja **Todos los usuarios**, seleccione un usuario de la lista y, a continuación, en el módulo para el usuario seleccionado, seleccione **Perfil** para ver la información que debe corregirse o actualizarse.

    ![Seleccionar perfil](../media/gdpr-azure-dsr-azure-user-profile.png)

5. Para corregir o actualizar la información de perfil del usuario, incluida la información de trabajo, seleccionando **Editar** en la barra de comandos y, a continuación  **Guardar** después de realizar los cambios.

    ![Seleccionar perfil](../media/gdpr-azure-dsr-azure-edit-user-profile.png)

#### <a name="service-specific-interfaces"></a>Interfaces específicas del servicio

Microsoft proporciona la capacidad de detectar datos de clientes directamente a través de interfaces de programación de aplicaciones (API) o interfaces de usuario (UI) ya existentes para servicios específicos. Los detalles se describen en la documentación de referencia de los respectivos servicios, que describen las operaciones CRUD (creación, lectura, actualización y eliminación) aplicables.

### <a name="step-4-restrict"></a>Paso 4: Restricción

Los interesados pueden pedir que restrinja el procesamiento de sus datos personales. Proporcionamos tanto Azure Portal como interfaces de programación de aplicaciones (API) o interfaces de usuario (IU) ya existentes. Estas experiencias proporcionan al administrador del arrendatario de la empresa la capacidad de gestionar esos DSR mediante una combinación de exportación y eliminación de datos. Un cliente puede (1) exportar una copia electrónica de los datos personales del usuario, incluyendo (a) cuentas, (b) registros generados por el sistema y (c) registros asociados, seguido de (2) la eliminación de la cuenta y datos asociados que residen en los sistemas de Microsoft.

### <a name="step-5-delete"></a>Paso 5: Eliminar

El “derecho a la eliminación” de datos personales de los datos de clientes de una organización es una protección clave en el GDPR. Cuando se quitan datos personales, esto conlleva quitar todos los datos personales y los registros generados por el sistema, salvo la información de registros de auditoría. Cuando un usuario se **elimina temporalmente** (ver los detalles a continuación), la cuenta se deshabilita durante 30 días. Si no se lleva a cabo ninguna otra acción durante este periodo de 30 días, el usuario se **elimina de forma permanente** (consulte los detalles a continuación). Tras una **eliminación permanente**, la cuenta del usuario, los datos personales y los registros generados por el sistema se eliminan en un plazo adicional de 30 días. Si un administrador del arrendatario emite inmediatamente una **eliminación permanente**, la cuenta del usuario, los datos personales y los registros generados por el sistema se eliminan en un plazo de 30 días a partir de la emisión.

> [!IMPORTANT]
> Debe ser un administrador del espacio empresarial para eliminar un usuario de en dicho espacio.

#### <a name="delete-a-user-and-associated-data-through-the-azure-portal"></a>Eliminar un usuario y los datos asociados a través de Azure Portal

Después de recibir una solicitud de eliminación por parte de un interesado, puede usar Azure Portal para eliminar tanto un usuario como la información personal asociada, además de los registros generados por el sistema.

Eliminar datos también supone la eliminación del usuario del inquilino. Los usuarios sufren una eliminación temporal inicial, lo que significa que un administrador de inquilinos puede recuperar la cuenta en los 30 días siguientes a la eliminación temporal. Después de 30 días, se elimina la cuenta automáticamente y de forma permanente del inquilino. Antes de que transcurran dichos 30 días, puede eliminar manualmente de la Papelera de reciclaje un usuario eliminado temporalmente.

Este el proceso de alto nivel para borrar usuarios de su inquilino.

1. Vaya a Azure Portal y encuentre el usuario.

2. Eliminar este usuario Cuando se elimina inicialmente el usuario, la cuenta del usuario se envía a la Papelera de reciclaje. **En este punto, el usuario es eliminado temporalmente, lo que significa que la cuenta está deshabilitada, pero no eliminada de Azure Active Directory.**

3. Vaya a la lista de usuarios eliminados recientemente y elimine al usuario de forma permanente. **En este momento el usuario se elimina permanentemente, lo que significa que la cuenta se ha depuración de Azure Active Directory**

###### <a name="to-delete-a-user-from-an-azure-tenant"></a>Para eliminar un usuario de un inquilino de Azure

1. Iniciar sesión en el [Azure Portal](https://portal.azure.com/) con una cuenta de administrador global para el directorio.

2. Seleccione **Azure Active Directory**.

    ![Seleccionar todos los servicios](../media/gdpr-azure-dsr-azure-portal.png)

3. Seleccione **Usuarios**.

    ![Seleccionar a los usuarios](../media/gdpr-azure-dsr-azure-all-users.png)

4. Active la casilla situada junto al usuario que desea eliminar, seleccione **Eliminar usuario** y después seleccione **Sí** en el cuadro que le pregunta si desea eliminar el usuario.

    ![Administración de usuarios](../media/gdpr-azure-dsr-azure-selected-user.png)

5. En **Todos los usuarios** en la hoja, seleccione **Usuarios eliminados**.

    ![Ver el perfil del usuario](../media/gdpr-azure-dsr-azure-deleted-user.png)

4. Vuelva a seleccionar el mismo usuario, seleccione  **Eliminar permanentemente** en la barra de comandos y luego seleccione **Sí**  en el cuadro que le pregunta si está seguro.

>[!IMPORTANT]  
>Tenga en cuenta que al hacer clic en **S**í está eliminando de forma permanente e irrevocable al usuario y todos los datos asociados y los registros generados por el sistema. Si lo hace por error, tendrá que volver a agregar manualmente el usuario al inquilino. Los datos asociados y los registros generados por el sistema no son recuperables.

   ![Ver información de trabajo del usuario](../media/gdpr-azure-dsr-azure-permanently-deleted-user.png)

#### <a name="service-specific-interfaces"></a>Interfaces específicas del servicio

Microsoft proporciona la capacidad de detectar datos de clientes directamente a través de interfaces de programación de aplicaciones (API) o interfaces de usuario (UI) ya existentes para servicios específicos. Los detalles se describen en la documentación de referencia de los respectivos servicios, que describen las operaciones CRUD (creación, lectura, actualización y eliminación) aplicables.

## <a name="step-6-export"></a>Paso 6: Exportar

El "derecho de portabilidad de datos" permite a un interesado solicitar una copia de sus datos personales en formato electrónico (es decir, un “formato estructurado, de uso común, compatible con dispositivos electrónicos e interoperable”) que pueda transmitirse a otro responsable de los datos. Azure soporta esto al permitir que su organización exporte los datos en formato nativo JSON a su contenedor de almacenamiento de Azure especificado.

>[!IMPORTANT]
>Debe ser un administrador de espacios empresariales para exportar datos de usuario del espacio empresarial.

### <a name="azure-active-directory"></a>Azure Active Directory

Con respecto a los datos de clientes, Microsoft ofrece un portal y las experiencias del producto para proporcionar al administrador de espacios empresariales del cliente empresarial la capacidad de exportar solicitudes de información de identificación sobre un usuario final.

### <a name="service-specific-interfaces"></a>Interfaces específicas del servicio

Microsoft proporciona la capacidad de detectar datos de clientes directamente a través de interfaces de programación de aplicaciones (API) o interfaces de usuario (UI) ya existentes para servicios específicos. Los detalles se describen en la documentación de referencia de los respectivos servicios, que describen las operaciones CRUD (creación, lectura, actualización y eliminación) aplicables.

## <a name="part-2-system-generated-logs"></a>Parte 2: Registros generados por el sistema

Microsoft también le ofrece la posibilidad de acceder, borrar y exportar ciertos registros generados por el sistema asociados con el uso de Azure por parte de un usuario..

>[!IMPORTANT]
> No se admite la capacidad para restringir o rectificar registros generados por el sistema. Los registros generados por el sistema constituyen acciones realizadas en la nube de Microsoft y datos de diagnóstico y modificar este tipo de datos comprometería los registros históricos de acciones, lo que aumentaría el fraude y los riesgos a la seguridad.

### <a name="executing-dsrs-against-system-generated-logs"></a>Ejecutar solicitudes de interesado en registros generados por el sistema.

Microsoft ofrece la posibilidad de acceder, borrar y exportar ciertos registros generados por el sistema a través del Azure Portal y también directamente a través de interfaces programáticas o interfaces de usuario para servicios específicos. Los detalles se describen en la documentación de referencia de los servicios respectivos.

>[!IMPORTANT]  
> Los servicios de apoyo a los DSR en producto requieren el uso directo de la interfaz de programación de aplicaciones (API) o la interfaz de usuario (UI) del servicio. Por consiguiente, la ejecución de un DSR en producto **debe hacerse además de la ejecución de un DSR dentro del Azure Portal para completar una solicitud de un sujeto de datos determinado. Por favor, consulte la documentación de referencia de los servicios específicos para obtener más detalles.**

### <a name="step-1-access"></a>Paso 1: Acceso

El administrador del arrendatario es la única persona de su organización que puede acceder a los registros generados por el sistema asociados con el uso de Azure por parte de un usuario en particular. Los datos recuperados para una solicitud de acceso se proporcionarán en un formato legible por máquina y se facilitarán en archivos que permitirán al usuario conocer los servicios a los que se asocian los datos. Como se ha señalado anteriormente, los datos recuperados no incluirán datos que puedan comprometer la seguridad del servicio.

#### <a name="azure-active-directory"></a>Azure Active Directory

Microsoft ofrece tanto un portal como experiencias de productos que proporcionan al administrador del arrendatario de la empresa la capacidad de gestionar las solicitudes de acceso. Las peticiones de acceso de interesado permiten acceder a los datos personales del usuario, incluyendo (a) información de identificación sobre un usuario final y (b) registros generados por el servicio. El proceso es idéntico al descrito en la sección de Azure Active Directory de la Parte 1, Paso 2: Acceso.

#### <a name="service-specific-interfaces"></a>Interfaces específicas del servicio

Microsoft proporciona la capacidad de detectar datos de clientes directamente a través de interfaces de programación de aplicaciones (API) o interfaces de usuario (UI) ya existentes para servicios específicos. Los detalles se describen en la documentación de referencia de los respectivos servicios, que describen las operaciones CRUD (creación, lectura, actualización y eliminación) aplicables.

### <a name="step-2-delete"></a>Paso 2: Eliminar

El Administrador de inquilinos es la única persona de su organización que puede ejecutar una petición de eliminación de una solicitud de interesado para un usuario concreto en un inquilino de Azure.

#### <a name="azure-active-directory"></a>Azure Active Directory

Microsoft ofrece tanto un portal como experiencias de productos que proporcionan al administrador del arrendatario de la empresa la capacidad de gestionar las solicitudes de eliminación de DSR. Las solicitudes de eliminación del DSR siguen el mismo procedimiento que se describe en la sección Eliminar un usuario y los datos asociados a través del Azure Portal de la Parte 1, Paso 5: Eliminar.

#### <a name="service-specific-interfaces"></a>Interfaces específicas del servicio

Microsoft proporciona la capacidad de detectar datos de clientes directamente a través de interfaces de programación de aplicaciones (API) o interfaces de usuario (UI) ya existentes para servicios específicos. Los detalles se describen en la documentación de referencia de los respectivos servicios, que describen las operaciones CRUD (creación, lectura, actualización y eliminación) aplicables.

### <a name="step-3-export"></a>Paso 3: Exportar

El administrador del arrendatario es la única persona de su organización que puede acceder a los registros generados por el sistema asociados con el uso de Azure por parte de un usuario en particular. Los datos recuperados para una solicitud de exportación se proporcionarán en un formato legible por máquina y se facilitarán en archivos que permitirán al usuario conocer los servicios a los que se asocian los datos. Como se ha señalado anteriormente, los datos recuperados no incluirán datos que puedan comprometer la seguridad o la estabilidad del servicio.

#### <a name="export-system-generated-logs-using-the-azure-portal"></a>Exportar registros generados por el sistema mediante Azure Portal

Después de recibir una solicitud de exportación para un interesado, puede usar Azure Portal para exportar registros generados por el sistema asociados a un usuario determinado.

Aquí está el proceso de alto nivel para exportar los datos de su inquilino.

1. Vaya a Azure Portal y cree una solicitud de exportación en nombre del usuario.
2. Exporte los datos y envíe el archivo al usuario.

###### <a name="to-export-a-users-info-from-an-azure-tenant"></a>Para exportar la información de un usuario de un inquilino de Azure

1. Abra Azure Portal, seleccione **Todos los servicios**, escriba *directiva* en el filtro y seleccione **Directiva**.

     ![Filtro Todos los servicios ](../media/gdpr-azure-dsr-azure-policy.png)

2. En la hoja **Directiva**, seleccione **Privacidad del usuario**, a continuación **Administrar las solicitudes de usuario** y después **Agregar solicitud de exportación**.

    ![Agregar solicitud de exportación ](../media/gdpr-azure-dsr-azure-add-export-request.png)

3. Completar la **solicitud de exportación de datos**:

    ![Nueva solicitud de exportación de datos](../media/gdpr-azure-dsr-azure-export-data-request.png)

- **Usuario.** Escriba la dirección de correo electrónico del usuario de Azure Active Directory que solicita la exportación.
- **Suscripción.** Seleccione la cuenta que usa para informar del uso de recursos y para facturar por servicios. Esta también es la ubicación de la cuenta de almacenamiento de Azure.
- **Cuenta de almacenamiento.** Seleccione la ubicación de su Azure Storage (Blob). Para obtener más información, consulte el artículo [Introducción a Microsoft Azure Storage, almacenamiento de blobs](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage).
- **Contenedor.** Crear un nuevo contenedor (o seleccionar uno existente) como lugar de almacenamiento de los datos de privacidad exportados por el usuario.

4. Seleccione **Crear**.

La solicitud de exportación pasa al estado **Pendiente**. Puede ver el informe de estado en la hoja **Privacidad del usuario: Información general**.

>[!IMPORTANT]  
>Debido a que los datos personales pueden provenir de múltiples sistemas, es posible que el proceso de exportación pueda tardar hasta un mes en completarse.

#### <a name="service-specific-interfaces"></a>Interfaces específicas del servicio

Microsoft proporciona la capacidad de detectar datos de clientes directamente a través de interfaces de programación de aplicaciones (API) o interfaces de usuario (UI) ya existentes para servicios específicos. Los detalles se describen en la documentación de referencia de los respectivos servicios, que describen las operaciones CRUD (creación, lectura, actualización y eliminación) aplicables.

### <a name="notify-about-exporting-or-deleting-issues"></a>Notificar sobre los problemas de exportación o eliminación

Si tiene problemas al exportar o eliminar datos desde Azure Portal, vaya a la hoja **Ayuda + soporte** de Azure Portal y envíe un nuevo vale en **Administración de suscripción > Otras solicitudes de seguridad y cumplimiento > Solicitudes de RGPD y la hoja de privacidad**.

## <a name="learn-more"></a>Más información

- [Centro de confianza de Microsoft](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
