---
title: Probar los permisos de un usuario (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 83a03b85-ea7f-4b4a-b19b-f7eca534ffae
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8c109eebb4bf06bf7605ca3b7b5930ce18951e41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673742"
---
# <a name="test-a-user39s-permissions-master-data-services"></a><span data-ttu-id="06a42-102">Probar los permisos de un usuario (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="06a42-102">Test a User&#39;s Permissions (Master Data Services)</span></span>
  <span data-ttu-id="06a42-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], puede crear un usuario y un registro de pruebas en la aplicación web para probar los permisos. Cuando un usuario intenta tener acceso a la dirección URL de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , se autentican las credenciales del usuario.</span><span class="sxs-lookup"><span data-stu-id="06a42-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can create a test user and log into the web application to test permissions.When a user attempts to access the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] URL, the user's credentials are authenticated.</span></span> <span data-ttu-id="06a42-104">En Internet Explorer, la configuración de seguridad controla si esto ocurre automáticamente o si el usuario debe escribir un nombre de usuario y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="06a42-104">In Internet Explorer, security settings control whether this occurs automatically or if the user must enter a user name and password.</span></span> <span data-ttu-id="06a42-105">Para cambiar estos valores, complete los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="06a42-105">To change these settings, complete the following steps:</span></span>  
  
### <a name="to-test-a-users-security"></a><span data-ttu-id="06a42-106">Para probar la seguridad de un usuario</span><span class="sxs-lookup"><span data-stu-id="06a42-106">To test a user's security</span></span>  
  
1.  <span data-ttu-id="06a42-107">En Internet Explorer 7 y versiones posteriores, haga clic en **Herramientas**, **Opciones de Internet**y, a continuación, haga clic en la pestaña **Seguridad** .</span><span class="sxs-lookup"><span data-stu-id="06a42-107">In Internet Explorer 7 and later, click **Tools**, **Internet Options**, and then click the **Security** tab.</span></span>  
  
2.  <span data-ttu-id="06a42-108">Haga clic en **Intranet local** y, a continuación, en el botón **Nivel personalizado** .</span><span class="sxs-lookup"><span data-stu-id="06a42-108">Click **Local Intranet** and then the **Custom Level** button.</span></span>  
  
3.  <span data-ttu-id="06a42-109">En la sección **Autenticación de usuario** , elija **Preguntar por el nombre de usuario y la contraseña**.</span><span class="sxs-lookup"><span data-stu-id="06a42-109">In the **User Authentication** section, choose **Prompt for user name and password**.</span></span>  
  
4.  <span data-ttu-id="06a42-110">La próxima vez que abra la ventana explorador, se le solicitará un nombre de usuario y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="06a42-110">The next time you open the browser window, you will be prompted for a user name and password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06a42-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="06a42-111">See Also</span></span>  
 [<span data-ttu-id="06a42-112">Seguridad &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="06a42-112">Security &#40;Master Data Services&#41;</span></span>](security-master-data-services.md)  
  
  
