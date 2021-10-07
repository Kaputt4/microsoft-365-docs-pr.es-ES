---
title: Escritura diferida de contraseña para el entorno de prueba de Microsoft 365
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/22/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Resumen: configure la escritura diferida de contraseña para el entorno de prueba de Microsoft 365'
ms.openlocfilehash: 0c0660008aea4a676da4be3c13e8d5c15cb3a51d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60166843"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>Escritura diferida de contraseña para el entorno de prueba de Microsoft 365

*Esta Guía del laboratorio de pruebas solo se puede usar Microsoft 365 entornos de prueba empresariales.*

Los usuarios pueden usar la reescribición de contraseñas para actualizar sus contraseñas a través de Azure Active Directory (Azure AD), que luego se replica en los Servicios de dominio de Active Directory (AD DS) locales. Con la reescribición de contraseñas, los usuarios no tienen que actualizar sus contraseñas a través del AD DS local donde se almacenan sus cuentas de usuario originales. Esto ayuda a los usuarios móviles o remotos que no tienen una conexión de acceso remoto a su red local.

En este artículo se describe cómo configurar el entorno Microsoft 365 prueba para la reescribición de contraseñas.

La configuración del entorno de prueba para la reescribición de contraseñas implica dos fases:
- [Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fase 2: Habilitar la escritura diferida de contraseña para el dominio TESTLAB de AD DS.](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Guías del laboratorio de pruebas para la nube de Microsoft.](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para obtener una asignación visual a todos los artículos de la pila Microsoft 365 guía del laboratorio de pruebas de empresa, vaya a Microsoft 365 enterprise [Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365

En primer lugar, siga las instrucciones de sincronización [de hash de contraseña.](password-hash-sync-m365-ent-test-environment.md) La configuración resultante tiene este aspecto:
  
![La empresa simulada con el entorno de prueba de sincronización de hash de contraseña.](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Esta configuración se compone de:
  
- Una suscripción de prueba o de pago de Microsoft 365 E5.
- Una intranet de organización simplificada conectada a Internet, formada por las máquinas virtuales DC1, APP1 y CLIENT1 en una subred de una red virtual de Azure.
- Azure AD Connect se ejecuta en APP1 para sincronizar el dominio TESTLAB de AD DS con el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365.

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a>Fase 2: Habilitar la escritura diferida de contraseña para el dominio TESTLAB de AD DS.

En primer lugar, configure la cuenta del Usuario 1 con el rol de administrador global.

1. Desde el [Centro de administración de Microsoft 365](https://portal.microsoft.com), inicie sesión con su cuenta de administrador global.

2. Seleccione **Usuarios activos**.
 
3. En la **página Usuarios activos,** seleccione la **cuenta user1,**

4. En el **panel user1,** seleccione **Editar** junto a **Roles**.

5. En el **panel Editar roles de** usuario para user1, seleccione Administrador **global**, **Seleccione** Guardar y, a continuación, **seleccione Cerrar**.

A continuación, configure la cuenta de Usuario 1 con la configuración de seguridad que le permite cambiar las contraseñas en nombre de otros usuarios en el dominio de TESTLAB AD DS.

1. Desde el [Azure Portal](https://portal.azure.com), inicie sesión con su cuenta de administrador global y, a continuación, conéctese a APP1 con la cuenta TESTLAB\Usuario1.

2. En el escritorio de APP1, seleccione **Inicio**, escriba **activo** y, a continuación, **seleccione Usuarios y equipos de Active Directory**.

3. En la barra de menús, seleccione **Ver**. Si **las características avanzadas** no están habilitadas, selecciónelo para habilitarlo.

4. En el panel de árbol, seleccione y mantenga presionado (o haga clic con el botón secundario) en el dominio, seleccione **Propiedades** y, a continuación, seleccione la **pestaña** Seguridad.

5. Seleccione **Opciones avanzadas**.

6. En la **pestaña Permisos,** seleccione **Agregar**.

7. Seleccione **Seleccionar una entidad de** seguridad, escriba **User1** y, a continuación, seleccione **Aceptar**.

8. En **Se aplica a**, seleccione **Objetos de usuario descendiente**.

9. En **Permisos**, seleccione lo siguiente:

    - **Cambiar contraseña**
    - **Restablecer contraseña**

10. En **Propiedades**, seleccione lo siguiente:
    - **Escribir lockoutTime**
    - **Escribir pwdLastSet**

11. Seleccione **Aceptar** tres veces para guardar los cambios.

12. Cierre **Usuarios y equipos de Active Directory**.

A continuación, configure Azure AD Connect en APP1 para la escritura diferida de contraseña.

1. Si es necesario, conéctese a APP1 con la cuenta TESTLAB\Usuario1.

2. Desde el escritorio de APP1, haga doble clic en **Azure AD Connect**.

3. En la **página de bienvenida,** seleccione **Configurar**.

4. En la **página Tareas adicionales,** seleccione **Personalizar opciones de sincronización** y, a continuación, seleccione **Siguiente**.

5. En la **Conectar a Azure AD,** escriba las credenciales de su cuenta de administrador global y, a continuación, **seleccione Siguiente**.

6. En los **directorios Conectar** y páginas de filtrado **dominio/ou,** seleccione **Siguiente**.

7. En la **página Características opcionales,** seleccione **Reescribición de** contraseña y, a continuación, **seleccione Siguiente**.

8. En la **página Listo para configurar,** seleccione **Configurar** y espere a que finalice el proceso.

9. Cuando vea que la configuración finaliza, seleccione **Salir**.

Ahora está listo para probar la escritura de escritura por contraseña para los usuarios en equipos que no están conectados a la red virtual de la intranet simulada.

La configuración resultante tiene este aspecto:

![La empresa simulada con entorno de prueba de autenticación de paso a través.](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Esta configuración se compone de:

- Una Microsoft 365 E5 de prueba o de pago con el dominio DNS TESTLAB.\<*your domain name*> registrado.
- Una intranet de organización simplificada conectada a Internet, formada por las máquinas virtuales DC1, APP1 y CLIENT1 en una subred de una red virtual de Azure.
- Azure AD Connect se ejecuta en APP1 para sincronizar la lista de cuentas y grupos desde el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365 con el dominio de TESTLAB AD DS.
- La escritura diferida de contraseña está habilitada para que los usuarios puedan cambiar sus contraseñas a través de Azure AD sin tener que estar conectados a la intranet simplificada.

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](/microsoft-365-enterprise/)