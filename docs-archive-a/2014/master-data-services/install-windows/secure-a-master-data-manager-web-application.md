---
title: Proteger una aplicación web de Master Data Manager | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: e360ba3a-e96b-4f85-b588-ed1f767fa973
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8f2ee807c2cd474542f701226d08427ade8279e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748829"
---
# <a name="secure-a-master-data-manager-web-application"></a><span data-ttu-id="438a8-102">Proteger una aplicación web Master Data Services</span><span class="sxs-lookup"><span data-stu-id="438a8-102">Secure a Master Data Manager Web Application</span></span>
  <span data-ttu-id="438a8-103">Puede proteger la aplicación web de [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] con HTTPS.</span><span class="sxs-lookup"><span data-stu-id="438a8-103">You can secure the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application with HTTPS.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="438a8-104">La aplicación web de [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] puede usa HTTP o HTTPS, pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="438a8-104">The [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application can use either HTTP or HTTPS, but not both.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="438a8-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="438a8-105">Prerequisites</span></span>  
 <span data-ttu-id="438a8-106">Para realizar el procedimiento:</span><span class="sxs-lookup"><span data-stu-id="438a8-106">To perform the procedure:</span></span>  
  
-   <span data-ttu-id="438a8-107">Debe ser administrador en el servidor web donde está instalado [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="438a8-107">You must be an administrator on the web server where [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] is installed.</span></span>  
  
-   <span data-ttu-id="438a8-108">MDS debe estar instalado en el servidor web y debe existir una aplicación web.</span><span class="sxs-lookup"><span data-stu-id="438a8-108">MDS must be installed on the web server, and a web application must exist.</span></span> <span data-ttu-id="438a8-109">Para obtener más información, vea [Instalar Master Data Services](install-master-data-services.md) y [Crear una aplicación web de Master Data Manager &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="438a8-109">For more information, see [Install Master Data Services](install-master-data-services.md) and [Create a Master Data Manager Web Application &#40;Master Data Services&#41;](create-a-master-data-manager-web-application-master-data-services.md).</span></span>  
  
### <a name="to-secure-the-master-data-manager-web-application-with-https"></a><span data-ttu-id="438a8-110">Para proteger la aplicación web Administrador de datos maestros con HTTP</span><span class="sxs-lookup"><span data-stu-id="438a8-110">To secure the Master Data Manager web application with HTTPS</span></span>  
  
1.  <span data-ttu-id="438a8-111">Después de confirmar que la aplicación web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] está configurada correctamente con HTTP, cree un certificado en IIS.</span><span class="sxs-lookup"><span data-stu-id="438a8-111">After you have confirmed that the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application is configured correctly with HTTP, create a certificate in IIS.</span></span> <span data-ttu-id="438a8-112">Para obtener más información, vea [Configurar certificados de servidor en IIS 7](https://technet.microsoft.com/library/cc732230\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="438a8-112">For more information, see [Configuring Server Certificates in IIS 7](https://technet.microsoft.com/library/cc732230\(WS.10\).aspx).</span></span>  
  
2.  <span data-ttu-id="438a8-113">En el panel **Conexiones** , debajo de **Sitios**, haga clic en en el sitio que hospeda la aplicación web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="438a8-113">In the **Connections** pane, under **Sites**, click the site that hosts the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application.</span></span>  
  
3.  <span data-ttu-id="438a8-114">En el panel **Acciones**, haga clic en **Enlaces**.</span><span class="sxs-lookup"><span data-stu-id="438a8-114">In the **Actions** pane, click **Bindings**.</span></span>  
  
4.  <span data-ttu-id="438a8-115">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="438a8-115">Click **Add**.</span></span>  
  
5.  <span data-ttu-id="438a8-116">En la lista, seleccione **https**.</span><span class="sxs-lookup"><span data-stu-id="438a8-116">From the list, select **https**.</span></span>  
  
6.  <span data-ttu-id="438a8-117">Seleccione el certificado SSL.</span><span class="sxs-lookup"><span data-stu-id="438a8-117">Select the SSL certificate.</span></span>  
  
7.  <span data-ttu-id="438a8-118">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="438a8-118">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="438a8-119">Opcional.</span><span class="sxs-lookup"><span data-stu-id="438a8-119">Optional.</span></span> <span data-ttu-id="438a8-120">Para quitar HTTP de modo que los usuarios puedan tener acceso al sitio solo con HTTP, en la lista, haga clic en la fila con **http**.</span><span class="sxs-lookup"><span data-stu-id="438a8-120">To remove HTTP so that users can access the site with HTTPS only, from the list, click the row with **http**.</span></span> <span data-ttu-id="438a8-121">Haga clic en **Quitar** y, en el cuadro de diálogo de confirmación, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="438a8-121">Click **Remove** and on the confirmation dialog box, click **Yes**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="438a8-122">Debe cambiar las configuraciones basicHttp y wsHttpBinding después de quitar HTTP.</span><span class="sxs-lookup"><span data-stu-id="438a8-122">You must change basicHttp and wsHttpBinding configurations after removing HTTP.</span></span>  
  
9. <span data-ttu-id="438a8-123">Para cerrar el cuadro de diálogo **Enlaces de sitios** , haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="438a8-123">To close the **Site Bindings** dialog box, click **Close**.</span></span>  
  
10. <span data-ttu-id="438a8-124">Abra ahora el archivo web.config desde *drive*:\Archivos de programa\Microsoft SQL Server\120\Master Data Services\WebApplication.</span><span class="sxs-lookup"><span data-stu-id="438a8-124">Now open the web.config file from *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\WebApplication.</span></span>  
  
11. <span data-ttu-id="438a8-125">Busque la cadena `<security mode="Message">` y cámbiela a `<security mode="Transport">`.</span><span class="sxs-lookup"><span data-stu-id="438a8-125">Find the string `<security mode="Message">` and change it to `<security mode="Transport">`.</span></span>  
  
12. <span data-ttu-id="438a8-126">Guarde y cierre el archivo.</span><span class="sxs-lookup"><span data-stu-id="438a8-126">Save and close the file.</span></span> <span data-ttu-id="438a8-127">Si obtiene un error, podría deberse a que ha habilitado UAC.</span><span class="sxs-lookup"><span data-stu-id="438a8-127">If you get an error, it could be because you have UAC enabled.</span></span> <span data-ttu-id="438a8-128">Para obtener más información, vea [Desactivar Control de cuentas de usuario](https://technet.microsoft.com/library/cc709691\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="438a8-128">For more information, see [Turn off User Account Control](https://technet.microsoft.com/library/cc709691\(WS.10\).aspx).</span></span> <span data-ttu-id="438a8-129">Ahora los usuarios deben poder usar HTTPS para tener acceso al sitio.</span><span class="sxs-lookup"><span data-stu-id="438a8-129">Users should now be able to use HTTPS to access the site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="438a8-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="438a8-130">See Also</span></span>  
 [<span data-ttu-id="438a8-131">Crear una aplicación web de Master Data Manager &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="438a8-131">Create a Master Data Manager Web Application &#40;Master Data Services&#41;</span></span>](create-a-master-data-manager-web-application-master-data-services.md)  
  
  
