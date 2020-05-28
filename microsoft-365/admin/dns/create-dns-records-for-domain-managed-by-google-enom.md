---
title: Crear registros DNS cuando Google (eNom) administra su dominio
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 3c490fbf-7833-4e43-be34-ed0dc3cce5e3
description: Obtenga información sobre cómo obtener acceso a eNom y crear DNS a través de la Página Google Domains.
ms.openlocfilehash: 6c6698f3d11f42cd0298bdb66710ec3c62bac5ca
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400261"
---
# <a name="create-dns-records-when-your-domain-is-managed-by-google-enom"></a>Crear registros DNS cuando Google (eNom) administra su dominio

 **[Consulte Preguntas más frecuentes acerca de los dominios](../setup/domains-faq.md)** si no encuentra lo que busca. 
  
Para migrar las cuentas de correo a Microsoft, debe crear un registro DNS en el registrador de dominios.
  
Si compró el dominio a través de Google al registrarse para su cuenta **de Google Apps for work** , Google administra los registros DNS, pero se registra con eNom. 
  
Puede tener acceso a eNom y crear DNS a través de la Página Google **Domains** . Solo tiene que seguir los pasos de este artículo. 
  
## <a name="create-the-dns-record"></a>Crear el registro DNS

1. En la [consola de administración de Google](https://www.google.com/work/apps/business), seleccione **iniciar sesión**.
    
    ![Google-Apps-Configure-1-1-0](../../media/37a6e9f6-319e-4c02-aa18-d8d06df7953d.png)
  
2. Escriba su nombre de dominio y, después, seleccione **ir**.
    
    ![Google-Apps-Configure-1-1-1](../../media/2caf8dcb-4d40-4cfa-bc40-d634e454e699.png)
  
3. En la parte inferior de la página, seleccione **más controles**.
    
    ![Google-Apps-Configure-1-2-0](../../media/1518ff78-035b-423e-85a3-c16d7faa0968.png)
  
4. Seleccione **Dominios**.
    
    ![Google-Apps-Configure-1-2-1](../../media/c2972c06-9bca-43bd-9876-2cee63043bf1.png)
  
5. En la página **dominios** , seleccione **Agregar o quitar dominios**.
    
    ![Google-Apps-Configure-1-2-2](../../media/07b8068f-9a05-40aa-a041-fc495c729a18.png)
  
6. En la página **dominios** , seleccione **Configuración avanzada de DNS**.
    
    > [!NOTE]
    > Si no ha comprado un nombre de dominio a través de Google al registrar su cuenta de **Google Apps for Work**, no tendrá **configuración avanzada de DNS** en su página **Dominios**. En su lugar, debe ir directamente al sitio web de su host de su dominio para acceder a la configuración de DNS y para realizar este paso y los siguientes. Consulte [tener acceso a la configuración del dominio de G Suite](https://support.google.com/a/answer/54693?hl=en) para obtener más información. 
  
    ![Google-Apps-eNom-configure-1-3](../../media/b244b29c-e479-40be-b380-4ffa0f74b421.png)
  
7. En la página **Configuración avanzada de DNS** , seleccione **iniciar sesión en la consola DNS**. Anote la información del **nombre de inicio de sesión** y la **contraseña**. La necesitará en el siguiente paso. 
    
    ![Google-Apps-eNom-configure-1-4](../../media/056a2767-462f-4847-acee-d01e3f773add.png)
  
8. Inicie sesión en el **Administrador de dominios** de Google con el **nombre de inicio de sesión** y la **contraseña** de la página **Configuración avanzada de DNS**. 
    
    ![Google-Apps-eNom-configure-1-5](../../media/08b74652-8cdb-4560-a5fd-0899f86deee8.png)
  
9. En la página ***domain_name*** , en la sección **registros de host** , seleccione **Editar**.
    
    ![Google-Apps-eNom-configure-1-6](../../media/d54fec18-b9d1-4796-8397-0393c964eade.png)
  
10. En la sección **registros de host** , seleccione **Agregar nuevo**.
    
    ![Google-Apps-eNom-configure-1-7](../../media/3562806a-4328-4e60-a717-0566841204cf.png)
  
11. En los cuadros para el nuevo registro, escriba o copie y pegue los valores de la tabla siguiente.
    
    |**HOST**|**TXT VALUE**|**TIPO DE REGISTRO**|
    |:-----|:-----|:-----|
    |@  <br/> ||TXT  <br/> |

    > [!NOTE]
    > This is an example. Utilice aquí su valor de **Dirección de destino**, desde la tabla. 
  
    [¿Cómo puedo encontrar esto?](../get-help-with-domains/information-for-dns-records.md)
  
12. Haga clic en **Guardar**.
    
    ![Google-Apps-eNom-configure-1-9](../../media/7a6f7b45-8f79-487b-afe4-05949c2c04e8.png)
  
13. Seleccione **Guardar cambios**.
    
    ![Google-Apps-Configure-1-11](../../media/7f321236-33fb-4a7d-9d03-26605e9e558c.png)
  
> [!NOTE]
>  Por lo general, los cambios de DNS tardan unos 15 minutos en aplicarse. Sin embargo, a veces los cambios pueden necesitar más tiempo para aplicarse en todo el sistema DNS de Internet. Si tiene problemas con el flujo de correo u otros problemas después de agregar registros DNS, consulte [Solucionar problemas después de cambiar el nombre del dominio o los registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
