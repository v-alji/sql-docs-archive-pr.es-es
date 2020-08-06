---
title: Publicación de una base de datos (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 98b2914e-7147-40af-ba7d-87253bbe8bf9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 652f2341d24c19e6c5ce34196b0e1c4dc5b09084
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672092"
---
# <a name="publish-a-database-sql-server-management-studio"></a><span data-ttu-id="031ff-102">Publicar una base de datos (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="031ff-102">Publish a Database (SQL Server Management Studio)</span></span>
  <span data-ttu-id="031ff-103">Puede usar el **Asistente Generar y publicar scripts** para publicar una base de datos completa u objetos de base de datos individuales en un proveedor de hospedaje web.</span><span class="sxs-lookup"><span data-stu-id="031ff-103">You can use the **Generate and Publish Scripts Wizard** to publish an entire database or individual database objects to a Web hosting provider.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="031ff-104">La funcionalidad descrita en este tema solía proporcionarla el Asistente para publicar bases de datos.</span><span class="sxs-lookup"><span data-stu-id="031ff-104">The functionality described in this topic used to be provided by the Publish Database Wizard.</span></span> <span data-ttu-id="031ff-105">La funcionalidad de publicación se ha agregado al Asistente Generar y publicar scripts y el Asistente para publicar bases de datos ha desparecido.</span><span class="sxs-lookup"><span data-stu-id="031ff-105">The publishing functionality has been added to the Generate and Publish Scripts Wizard, and the Publish Database Wizard has been discontinued.</span></span>  
  
## <a name="generate-and-publish-scripts-wizard"></a><span data-ttu-id="031ff-106">Asistente generar y publicar scripts</span><span class="sxs-lookup"><span data-stu-id="031ff-106">Generate and Publish Scripts Wizard</span></span>  
 <span data-ttu-id="031ff-107">El Asistente Generar y publicar scripts puede usarse para publicar una base de datos u objetos seleccionados de una base de datos en un proveedor de hospedaje web.</span><span class="sxs-lookup"><span data-stu-id="031ff-107">The Generate and Publish Scripts Wizard can be used to publish a database or selected database objects to a Web hosting provider.</span></span> <span data-ttu-id="031ff-108">Un proveedor de hospedaje web de SQL Server es una interfaz de conectividad con un servicio web.</span><span class="sxs-lookup"><span data-stu-id="031ff-108">A SQL Server Web hosting provider is a connectivity interface to a Web service.</span></span> <span data-ttu-id="031ff-109">El servicio web se crea usando el proyecto Database Publishing Services de SQL Server Hosting Toolkit en CodePlex.</span><span class="sxs-lookup"><span data-stu-id="031ff-109">The Web service is created by using the Database Publishing Services project from the SQL Server Hosting Toolkit on CodePlex.</span></span> <span data-ttu-id="031ff-110">El servicio web facilita a los clientes del anfitrión web publicar sus bases de datos en el servicio usando el Asistente Generar y publicar scripts.</span><span class="sxs-lookup"><span data-stu-id="031ff-110">The Web service makes it easy for the Web hoster customers to publish their databases to the service by using the Generate and Publish Scripts Wizard.</span></span> <span data-ttu-id="031ff-111">Para obtener más información sobre cómo descargar el SQL Server Hosting Toolkit, vea [SQL Server Database Publishing Services](https://go.microsoft.com/fwlink/?LinkId=142025).</span><span class="sxs-lookup"><span data-stu-id="031ff-111">For more information about downloading the SQL Server Hosting Toolkit, see [SQL Server Database Publishing Services](https://go.microsoft.com/fwlink/?LinkId=142025).</span></span>  
  
 <span data-ttu-id="031ff-112">El Asistente Generar y publicar scripts también se puede usar para crear un script para transferir una base de datos.</span><span class="sxs-lookup"><span data-stu-id="031ff-112">The Generate and Publish Scripts Wizard can also be used to create a script for transferring a database.</span></span>  
  
#### <a name="to-publish-a-database-to-a-web-service"></a><span data-ttu-id="031ff-113">Para publicar una base de datos en un servicio web</span><span class="sxs-lookup"><span data-stu-id="031ff-113">To publish a database to a Web service</span></span>  
  
1.  <span data-ttu-id="031ff-114">En el Explorador de objetos, expanda **Bases de datos**, haga clic con el botón derecho en una base de datos, seleccione **Tareas**y, después, haga clic en **Generar y publicar scripts**.</span><span class="sxs-lookup"><span data-stu-id="031ff-114">In Object Explorer, expand **Databases**, right-click a database, point to **Tasks**, and then click **Generate and Publish Scripts**.</span></span> <span data-ttu-id="031ff-115">Siga las instrucciones del asistente para incluir los objetos de la base de datos en el script para su publicación.</span><span class="sxs-lookup"><span data-stu-id="031ff-115">Follow the steps in the wizard to script the database objects for publishing.</span></span>  
  
2.  <span data-ttu-id="031ff-116">En la página **Elegir objetos** , seleccione los objetos que se van a publicar en el servicio de hospedaje web.</span><span class="sxs-lookup"><span data-stu-id="031ff-116">On the **Choose Objects** page, select the objects to be published to the Web hosting service.</span></span>  
  
3.  <span data-ttu-id="031ff-117">En la página **Establecer opciones de scripting** , seleccione **Publicar en servicio web**.</span><span class="sxs-lookup"><span data-stu-id="031ff-117">On the **Set Scripting Options** page, select **Publish to Web Service**.</span></span>  
  
    1.  <span data-ttu-id="031ff-118">En el cuadro **Proveedor** , especifique el proveedor para su servicio web.</span><span class="sxs-lookup"><span data-stu-id="031ff-118">In the **Provider** box, specify the provider for your Web service.</span></span> <span data-ttu-id="031ff-119">Si no ha configurado un proveedor de hospedaje web, seleccione **Proveedores administrados** y use el diálogo **Proveedores administrados** para configurar un proveedor para su servicio web.</span><span class="sxs-lookup"><span data-stu-id="031ff-119">If you have not configured a Web hosting provider, select **Manage Providers** and use the **Manage Providers** dialog box to configure a provider for your Web service.</span></span>  
  
    2.  <span data-ttu-id="031ff-120">Para especificar opciones de publicación avanzadas, seleccione el botón **Avanzadas** en la sección **Publicar en servicio web** .</span><span class="sxs-lookup"><span data-stu-id="031ff-120">To specify advanced publishing options, select the **Advanced** button in the **Publish to Web Service** section.</span></span>  
  
4.  <span data-ttu-id="031ff-121">En la página **Resumen** , revise sus selecciones.</span><span class="sxs-lookup"><span data-stu-id="031ff-121">On the **Summary** page, review your selections.</span></span> <span data-ttu-id="031ff-122">Haga clic en **Anterior** para cambiar sus selecciones.</span><span class="sxs-lookup"><span data-stu-id="031ff-122">Click **Previous** to change your selections.</span></span> <span data-ttu-id="031ff-123">Haga clic en **Siguiente** para publicar los objetos que seleccionó.</span><span class="sxs-lookup"><span data-stu-id="031ff-123">Click **Next** to publish the objects you selected.</span></span>  
  
5.  <span data-ttu-id="031ff-124">En la página **Guardar o publicar scripts** , supervise el progreso de la publicación.</span><span class="sxs-lookup"><span data-stu-id="031ff-124">On the **Save or Publish Scripts** page, monitor the progress of the publication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="031ff-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="031ff-125">See Also</span></span>  
 <span data-ttu-id="031ff-126">[Generar scripts &#40;SQL Server Management Studio&#41;](../scripting/generate-scripts-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="031ff-126">[Generate Scripts &#40;SQL Server Management Studio&#41;](../scripting/generate-scripts-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="031ff-127">Copiar bases de datos en otros servidores</span><span class="sxs-lookup"><span data-stu-id="031ff-127">Copy Databases to Other Servers</span></span>](copy-databases-to-other-servers.md)  
  
  
