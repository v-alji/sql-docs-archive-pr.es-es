---
title: Conceder permisos a los usuarios y alertar a los administradores | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 166808e1-ada7-48d2-bda8-8f7c017fb3aa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5bf7f030871287379ce9fb32a1789b95cff0fc0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676876"
---
# <a name="grant-permissions-to-users-and-alerting-administrators"></a><span data-ttu-id="08abf-102">Conceder permisos a los usuarios y alertar a los administradores</span><span class="sxs-lookup"><span data-stu-id="08abf-102">Grant Permissions to Users and Alerting Administrators</span></span>
  <span data-ttu-id="08abf-103">Para que los usuarios y administradores de alertas puedan crear, modificar, eliminar y ver las alertas de datos, se les deben conceder permisos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="08abf-103">Before users and alerting administrators can create, edit, delete, and view data alerts they must be granted SharePoint permissions.</span></span> <span data-ttu-id="08abf-104">No hay que usar permisos especiales con la característica de alertas de datos de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] (se usan los permisos integrados de SharePoint).</span><span class="sxs-lookup"><span data-stu-id="08abf-104">There are no special permissions to use with the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] data alerting feature, you use the built-in SharePoint permissions.</span></span>  
  
 <span data-ttu-id="08abf-105">**Trabajadores de la información**: se les deben conceder los permisos de SharePoint Crear alertas y Ver elementos.</span><span class="sxs-lookup"><span data-stu-id="08abf-105">**Information workers**-Permissions must include the Create Alert and View Items SharePoint permissions.</span></span> <span data-ttu-id="08abf-106">Los niveles de permisos integrados de SharePoint denominados Diseño, Colaborar, Leer y Solo ver incluyen los permisos de SharePoint Crear alertas y Ver elementos.</span><span class="sxs-lookup"><span data-stu-id="08abf-106">The built-in SharePoint permission levels named Design, Contribute, Read, and View Only include the Create Alert and View Items SharePoint permissions.</span></span> <span data-ttu-id="08abf-107">También se puede crear un nivel de permiso personalizado con los permisos necesarios para permitir que los usuarios creen, modifiquen, ejecuten y vean las alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="08abf-107">You can also create a custom permission level with the permissions required to support users that create, edit, run, and view data alerts.</span></span>  
  
 <span data-ttu-id="08abf-108">**Administradores de alertas**: los permisos deben incluir el permiso administrar alertas de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="08abf-108">**Alerting administrators**-Permissions must include the Manage Alert SharePoint permission.</span></span> <span data-ttu-id="08abf-109">De forma predeterminada, solo en nivel de permiso Control total incluye este permiso para los sitios creados con la plantilla de sitio Sitio de equipo.</span><span class="sxs-lookup"><span data-stu-id="08abf-109">By default only the Full Control permission level includes this permission for sites created with the Team Site site template.</span></span> <span data-ttu-id="08abf-110">Si utiliza otras plantillas de sitio, verá lista diferentes de grupos de SharePoint predeterminados.</span><span class="sxs-lookup"><span data-stu-id="08abf-110">If you use other site templates, you will see different lists of default SharePoint groups.</span></span> <span data-ttu-id="08abf-111">Puede agregar el permiso Administrar alertas a uno de los niveles de permisos integrados o crear un nivel de permiso personalizado con el permiso requerido para permitir que los administradores de alertas vean y eliminen las alertas de datos.</span><span class="sxs-lookup"><span data-stu-id="08abf-111">You can add the Manage Alert permission to one of the built-in permission levels or create a custom permission level with the permission required to support alerting administrators that view and delete data alerts.</span></span>  
  
 <span data-ttu-id="08abf-112">Para más información sobre los permisos de SharePoint, vea [Permisos de usuario y niveles de permisos (SharePoint Server 2010)](https://technet.microsoft.com/library/cc721640.aspx).</span><span class="sxs-lookup"><span data-stu-id="08abf-112">To learn more about SharePoint permissions, see [User permissions and permission levels (SharePoint Server 2010)](https://technet.microsoft.com/library/cc721640.aspx).</span></span>  
  
### <a name="to-grant-permissions"></a><span data-ttu-id="08abf-113">Para conceder permisos</span><span class="sxs-lookup"><span data-stu-id="08abf-113">To grant permissions</span></span>  
  
1.  <span data-ttu-id="08abf-114">Vaya al sitio de SharePoint para el que desea conceder permisos.</span><span class="sxs-lookup"><span data-stu-id="08abf-114">Go to the SharePoint site to which you want to grant permissions.</span></span>  
  
2.  <span data-ttu-id="08abf-115">En la barra de herramientas, haga clic **Acciones del sitio** y en **Permisos de sitio**.</span><span class="sxs-lookup"><span data-stu-id="08abf-115">On the toolbar, click **Site Actions** and then click **Site Permissions**.</span></span>  
  
     <span data-ttu-id="08abf-116">Si no aparece esta opción, no tiene permisos suficientes para conceder permisos a otros.</span><span class="sxs-lookup"><span data-stu-id="08abf-116">If you do not see this option, you do not sufficient permission to grant permissions to others.</span></span>  
  
3.  <span data-ttu-id="08abf-117">Haga clic en **Concesión de permisos**.</span><span class="sxs-lookup"><span data-stu-id="08abf-117">Click **Grant Permissions**.</span></span>  
  
4.  <span data-ttu-id="08abf-118">En **Usuarios/Grupos**, escriba los nombres de usuario, los nombres de grupo o las direcciones de correo electrónico a los que quiere conceder permiso.</span><span class="sxs-lookup"><span data-stu-id="08abf-118">In **Users/Groups**, type the user names, group names, or e-mail addresses you want grant permission to.</span></span>  
  
5.  <span data-ttu-id="08abf-119">Seleccione la opción **Agregar usuarios a un grupo de SharePoint** o **Conceder permisos a los usuarios directamente** .</span><span class="sxs-lookup"><span data-stu-id="08abf-119">Select the **Add users to a SharePoint group** or **Grant users permission directly** option.</span></span> <span data-ttu-id="08abf-120">Dependiendo de si seleccionó **Agregar usuarios a un grupo de SharePoint** o **Conceder permisos a los usuarios directamente** , siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="08abf-120">Depending on whether you selected **Add users to a SharePoint group** or **Grant users permissions directly** do one of the following:</span></span>  
  
    -   <span data-ttu-id="08abf-121">Si ha seleccionado **Agregar usuarios a un grupo de SharePoint**, seleccione un nivel de permisos en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="08abf-121">If you selected **Add users to a SharePoint group**, select a permission level in the drop-down list.</span></span>  
  
    -   <span data-ttu-id="08abf-122">Si ha seleccionado **Conceder permisos a los usuarios directamente**, seleccione un nivel de permiso.</span><span class="sxs-lookup"><span data-stu-id="08abf-122">If you selected **Grant users permissions directly**, select a permission level.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="08abf-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="08abf-123">See Also</span></span>  
 <span data-ttu-id="08abf-124">[Establecer permisos para elementos del servidor de informes en un sitio de SharePoint &#40;Reporting Services en el modo integrado de SharePoint&#41;](security/set-permissions-for-report-server-items-on-a-sharepoint-site.md) </span><span class="sxs-lookup"><span data-stu-id="08abf-124">[Set Permissions for Report Server Items on a SharePoint Site &#40;Reporting Services in SharePoint Integrated Mode&#41;](security/set-permissions-for-report-server-items-on-a-sharepoint-site.md) </span></span>  
 [<span data-ttu-id="08abf-125">Alertas de datos de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="08abf-125">Reporting Services Data Alerts</span></span>](../ssms/agent/alerts.md)  
  
  
