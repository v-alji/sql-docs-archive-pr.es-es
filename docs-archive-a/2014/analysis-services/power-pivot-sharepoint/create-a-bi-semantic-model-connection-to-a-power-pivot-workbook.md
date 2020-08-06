---
title: Crear una conexión de modelo semántico de BI a un libro PowerPivot | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b2e3f97f-18a8-42b6-9030-b4f818afc3b9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7ea4ddcc38328acc6ff8cfb5387b13056b689a24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675573"
---
# <a name="create-a-bi-semantic-model-connection-to-a-powerpivot-workbook"></a><span data-ttu-id="9ce51-102">Creación de una conexión de modelo semántico de BI a un libro de PowerPivot</span><span class="sxs-lookup"><span data-stu-id="9ce51-102">Create a BI Semantic Model Connection to a PowerPivot Workbook</span></span>
  <span data-ttu-id="9ce51-103">Utilice la información de este tema para configurar una conexión de modelo semántico de BI que redirija a un libro PowerPivot de la misma granja.</span><span class="sxs-lookup"><span data-stu-id="9ce51-103">Use the information in this topic to set up a BI semantic model connection that redirects to a PowerPivot workbook in the same farm.</span></span>  
  
 <span data-ttu-id="9ce51-104">Después de crear una conexión de modelo semántico de BI y configurar los permisos de SharePoint, puede utilizarla como origen de datos para Excel o informes de [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9ce51-104">After you create a BI semantic model connection and configure SharePoint permissions, you can use it as a data source for Excel or [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] reports.</span></span>  
  
 <span data-ttu-id="9ce51-105">En este tema se incluyen las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="9ce51-105">This topic includes the following sections.</span></span> <span data-ttu-id="9ce51-106">Realice cada tarea en el orden indicado.</span><span class="sxs-lookup"><span data-stu-id="9ce51-106">Perform each task in the order given.</span></span>  
  
 [<span data-ttu-id="9ce51-107">Requisitos previos de revisión</span><span class="sxs-lookup"><span data-stu-id="9ce51-107">Review Prerequisites</span></span>](#bkmk_prereq)  
  
 [<span data-ttu-id="9ce51-108">Crear una conexión</span><span class="sxs-lookup"><span data-stu-id="9ce51-108">Create a Connection</span></span>](#bkmk_create)  
  
 [<span data-ttu-id="9ce51-109">Configurar permisos de SharePoint en la conexión de modelo semántico de BI</span><span class="sxs-lookup"><span data-stu-id="9ce51-109">Configure SharePoint Permissions on the BI Semantic Model Connection</span></span>](#bkmk_permissions)  
  
 [<span data-ttu-id="9ce51-110">Configurar permisos de SharePoint en el libro</span><span class="sxs-lookup"><span data-stu-id="9ce51-110">Configure SharePoint Permissions on the Workbook</span></span>](#bkmk_userdb)  
  
 [<span data-ttu-id="9ce51-111">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9ce51-111">Next Steps</span></span>](#bkmk_next)  
  
##  <a name="review-prerequisites"></a><a name="bkmk_prereq"></a><span data-ttu-id="9ce51-112">Revisar los requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9ce51-112">Review Prerequisites</span></span>  
 <span data-ttu-id="9ce51-113">Debe tener permisos de contribución o superiores para poder crear un archivo de conexión de modelo semántico de BI.</span><span class="sxs-lookup"><span data-stu-id="9ce51-113">You must have Contribute permissions or above to create a BI semantic model connection file.</span></span>  
  
 <span data-ttu-id="9ce51-114">Debe tener una biblioteca que admita el tipo de contenido de la conexión de modelo semántico de BI.</span><span class="sxs-lookup"><span data-stu-id="9ce51-114">You must have a library that supports the BI semantic model connection content type.</span></span> <span data-ttu-id="9ce51-115">Para obtener más información, vea [Agregar un tipo de contenido de conexión de modelo semántico de BI a una biblioteca &#40;PowerPivot para SharePoint&#41;](add-bi-semantic-model-connection-content-type-to-library.md).</span><span class="sxs-lookup"><span data-stu-id="9ce51-115">For more information, see [Add a BI Semantic Model Connection Content Type to a Library &#40;PowerPivot for SharePoint&#41;](add-bi-semantic-model-connection-content-type-to-library.md).</span></span>  
  
 <span data-ttu-id="9ce51-116">Debe conocer la dirección URL del libro PowerPivot para el que está configurando una conexión de modelo semántico de BI (por ejemplo, http://adventure-works/shared documentos/myworkbook.xlsx).</span><span class="sxs-lookup"><span data-stu-id="9ce51-116">You must know the URL of the PowerPivot workbook for which you are setting up a BI semantic model connection (for example, http://adventure-works/shared documents/myworkbook.xlsx).</span></span> <span data-ttu-id="9ce51-117">El libro debe estar en la misma granja.</span><span class="sxs-lookup"><span data-stu-id="9ce51-117">The workbook must be in the same farm.</span></span>  
  
 <span data-ttu-id="9ce51-118">Todos los equipos y usuarios que forman parte de la secuencia de conexión deben estar en el mismo dominio o en dominios de confianza (confianza bidireccional).</span><span class="sxs-lookup"><span data-stu-id="9ce51-118">All computers and users that participate in the connection sequence must be in the same domain or trusted domain (two-way trust).</span></span>  
  
##  <a name="create-a-connection"></a><a name="bkmk_create"></a><span data-ttu-id="9ce51-119">Crear una conexión</span><span class="sxs-lookup"><span data-stu-id="9ce51-119">Create a Connection</span></span>  
  
1.  <span data-ttu-id="9ce51-120">En la biblioteca que contendrá la conexión de modelo semántico de BI, haga clic en **Documentos** en la cinta de opciones de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9ce51-120">In the library that will contain the BI semantic model connection, click **Documents** on the SharePoint ribbon.</span></span> <span data-ttu-id="9ce51-121">Haga clic en la flecha abajo en Nuevo documento y seleccione **Archivo de conexión BISM** para abrir la página Nueva conexión de modelo semántico de BI.</span><span class="sxs-lookup"><span data-stu-id="9ce51-121">Click the down arrow on New Document, and select **BISM Connection File** to open the New BI Semantic Model Connection page.</span></span>  
  
     <span data-ttu-id="9ce51-122">![Submenú Nuevo documento en una biblioteca de SharePoint](../media/ssas-bismconnection-new.gif "Submenú Nuevo documento en una biblioteca de SharePoint")</span><span class="sxs-lookup"><span data-stu-id="9ce51-122">![New Document submenu in a SharePoint library](../media/ssas-bismconnection-new.gif "New Document submenu in a SharePoint library")</span></span>  
  
2.  <span data-ttu-id="9ce51-123">Establezca la propiedad del **servidor** en la dirección URL de SharePoint del libro PowerPivot (por ejemplo, \*\* http://mysharepoint/shared documentos/myWorkbook.xlsx\*\*.</span><span class="sxs-lookup"><span data-stu-id="9ce51-123">Set the **Server** property to the SharePoint URL of the PowerPivot workbook (for example, **http://mysharepoint/shared documents/myWorkbook.xlsx**.</span></span> <span data-ttu-id="9ce51-124">En una implementación de PowerPivot para SharePoint, los datos se pueden cargar en cualquier servidor de la granja.</span><span class="sxs-lookup"><span data-stu-id="9ce51-124">In a PowerPivot for SharePoint deployment, data can be loaded on any server in the farm.</span></span> <span data-ttu-id="9ce51-125">Por este motivo, las conexiones de origen de datos a datos PowerPivot especifican solo la ruta de acceso al libro.</span><span class="sxs-lookup"><span data-stu-id="9ce51-125">For this reason, data source connections to PowerPivot data specify just the path to the workbook.</span></span> <span data-ttu-id="9ce51-126">El Servicio de sistema de PowerPivot determina qué servidor carga los datos.</span><span class="sxs-lookup"><span data-stu-id="9ce51-126">The PowerPivot System Service determines which server loads the data.</span></span>  
  
     <span data-ttu-id="9ce51-127">No use la propiedad de **base de datos** ; no se utiliza al especificar la ubicación de un libro PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="9ce51-127">Do not use the **Database** property; it is not used when specifying the location of a PowerPivot workbook.</span></span>  
  
     <span data-ttu-id="9ce51-128">El aspecto de su página deberá ser parecido al de la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="9ce51-128">Your page should look similar to the following illustration.</span></span>  
  
     <span data-ttu-id="9ce51-129">![Página de conexión de BISM que muestra la dirección URL al libro](../media/ssas-bismconnection-ppvtds.gif "Página de conexión de BISM que muestra la dirección URL al libro")</span><span class="sxs-lookup"><span data-stu-id="9ce51-129">![BISM connection page showing URL to workbook](../media/ssas-bismconnection-ppvtds.gif "BISM connection page showing URL to workbook")</span></span>  
  
     <span data-ttu-id="9ce51-130">Opcionalmente, si tiene permisos de SharePoint para el libro, realice un paso adicional de validación para asegurarse de que la ubicación es válida.</span><span class="sxs-lookup"><span data-stu-id="9ce51-130">Optionally, if you have SharePoint permissions to the workbook, an extra validation step is performed, ensuring that the location is valid.</span></span> <span data-ttu-id="9ce51-131">Si no tiene permiso para obtener acceso a los datos, se le ofrecerá la opción de guardar la conexión de modelo semánticos de BI sin la respuesta de validación.</span><span class="sxs-lookup"><span data-stu-id="9ce51-131">If you do not have permission to access the data, you are given the option of saving the BI semantic model connection without the validation response.</span></span>  
  
##  <a name="configure-sharepoint-permissions-on-the-bi-semantic-model-connection"></a><a name="bkmk_permissions"></a><span data-ttu-id="9ce51-132">Configurar permisos de SharePoint en la conexión de modelo semántico de BI</span><span class="sxs-lookup"><span data-stu-id="9ce51-132">Configure SharePoint Permissions on the BI Semantic Model Connection</span></span>  
 <span data-ttu-id="9ce51-133">La capacidad de utilizar una conexión de modelo semántico de BI como origen de datos en un libro de Excel o un informe de Reporting Services requiere permisos de **Lectura** en el elemento de conexión de modelo semántico de BI de una biblioteca de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9ce51-133">Ability to use a BI semantic model connection as a data source for an Excel workbook or Reporting Services report requires **Read** permissions on the BI semantic model connection item in a SharePoint library.</span></span> <span data-ttu-id="9ce51-134">El nivel de permiso de lectura incluye el permiso **Abrir elementos** , que permite descargar la información de la conexión de modelo semántico de BI en una aplicación de escritorio de Excel.</span><span class="sxs-lookup"><span data-stu-id="9ce51-134">The Read permission level includes the **Open Items** permission that enables downloading BI semantic model connection information to an Excel desktop application.</span></span>  
  
 <span data-ttu-id="9ce51-135">Hay varias maneras de conceder permisos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9ce51-135">There are several ways to grant permissions in SharePoint.</span></span> <span data-ttu-id="9ce51-136">Las instrucciones siguientes explican cómo crear un grupo denominado **Usuarios de BISM** que tenga el nivel de permiso de **Lectura** .</span><span class="sxs-lookup"><span data-stu-id="9ce51-136">The following instructions explain how to create a new group called **BISM Users** that have the **Read** permission level.</span></span>  
  
 <span data-ttu-id="9ce51-137">Debe ser propietario del sitio para cambiar los permisos.</span><span class="sxs-lookup"><span data-stu-id="9ce51-137">You must be a site owner to change permissions.</span></span>  
  
1.  <span data-ttu-id="9ce51-138">En Acciones del sitio, haga clic en **Permisos de sitio**.</span><span class="sxs-lookup"><span data-stu-id="9ce51-138">In Site Actions, click **Site Permissions**.</span></span>  
  
2.  <span data-ttu-id="9ce51-139">Haga clic **Crear grupo** y asigne al nuevo grupo el nombre **Usuarios de BISM**.</span><span class="sxs-lookup"><span data-stu-id="9ce51-139">Click **Create Group** and name the new group **BISM Users**.</span></span>  
  
3.  <span data-ttu-id="9ce51-140">Elija el nivel de permiso de **Lectura** y haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="9ce51-140">Choose the **Read** permission level and click **Create**.</span></span>  
  
4.  <span data-ttu-id="9ce51-141">Seleccione **Usuarios de BISM** en usuarios y grupos.</span><span class="sxs-lookup"><span data-stu-id="9ce51-141">Select **BISM Users** in People and Groups.</span></span>  
  
5.  <span data-ttu-id="9ce51-142">Seleccione Nuevo, haga clic en **Agregar usuarios**y, a continuación, agregue cuentas de usuario o grupo.</span><span class="sxs-lookup"><span data-stu-id="9ce51-142">Point to New, click **Add Users**, and then add user or group accounts.</span></span>  
  
     <span data-ttu-id="9ce51-143">Estos usuarios y grupos tendrán ahora permisos de Lectura en el sitio, incluidas todas las bibliotecas y las listas que hereden permisos del nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="9ce51-143">These users and groups will now have Read permissions throughout the site, including all libraries and lists that inherit permissions from the site level.</span></span> <span data-ttu-id="9ce51-144">Si estos permisos son demasiado elevados, puede quitar selectivamente este grupo de determinadas bibliotecas, listas, o elementos.</span><span class="sxs-lookup"><span data-stu-id="9ce51-144">If these permissions are too high, you can selectively remove this group from specific libraries, lists, or items.</span></span>  
  
 <span data-ttu-id="9ce51-145">Para quitar selectivamente permisos en el nivel de elemento, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9ce51-145">To selectively remove permissions at the item level, do the following:</span></span>  
  
1.  <span data-ttu-id="9ce51-146">En una biblioteca, seleccione un documento.</span><span class="sxs-lookup"><span data-stu-id="9ce51-146">In a library, select a document.</span></span> <span data-ttu-id="9ce51-147">Haga clic en la flecha abajo a la derecha y después haga clic en **Administrar permisos**.</span><span class="sxs-lookup"><span data-stu-id="9ce51-147">Click the right down arrow and then click **Manage Permissions**.</span></span>  
  
2.  <span data-ttu-id="9ce51-148">Un elemento hereda, de forma predeterminada, los permisos.</span><span class="sxs-lookup"><span data-stu-id="9ce51-148">By default, an item inherits permissions.</span></span> <span data-ttu-id="9ce51-149">Para cambiar los permisos de documentos individuales en esta biblioteca, haga clic en **Dejar de heredar permisos**.</span><span class="sxs-lookup"><span data-stu-id="9ce51-149">To change the permissions of individual documents in this library, click **Stop Inheriting Permissions**.</span></span>  
  
3.  <span data-ttu-id="9ce51-150">Active la casilla junto a **Usuarios de BISM**.</span><span class="sxs-lookup"><span data-stu-id="9ce51-150">Select the checkbox next to **BISM Users**.</span></span>  
  
4.  <span data-ttu-id="9ce51-151">Haga clic en **Quitar permisos de usuario**.</span><span class="sxs-lookup"><span data-stu-id="9ce51-151">Click **Remove User Permissions**.</span></span>  
  
##  <a name="configure-sharepoint-permissions-on-the-workbook"></a><a name="bkmk_userdb"></a><span data-ttu-id="9ce51-152">Configurar permisos de SharePoint en el libro</span><span class="sxs-lookup"><span data-stu-id="9ce51-152">Configure SharePoint Permissions on the Workbook</span></span>  
 <span data-ttu-id="9ce51-153">Si utiliza una base de datos de PowerPivot en un libro de Excel, los permisos de SharePoint del libro de Excel determinarán el acceso a los datos a través de la conexión de modelo semántico de BI.</span><span class="sxs-lookup"><span data-stu-id="9ce51-153">If you are using a PowerPivot database inside an Excel workbook, the SharePoint permissions on the Excel workbook determine data access via the BI semantic model connection.</span></span> <span data-ttu-id="9ce51-154">Todos los usuarios que tengan acceso al libro deben tener permisos de Lectura en el libro para poder utilizarlo como origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="9ce51-154">All users who access the workbook must have Read permissions on the workbook in order to use it as an external data source.</span></span>  
  
 <span data-ttu-id="9ce51-155">Si creó un grupo de **usuarios de BISM** utilizando las instrucciones de la sección anterior, las cuentas de usuario y de grupo que pertenecen a los **usuarios de BISM** tendrán permisos suficientes en el libro, así como el archivo de conexión de modelo semántico de BI, suponiendo que el libro utilice permisos heredados.</span><span class="sxs-lookup"><span data-stu-id="9ce51-155">If you created a **BISM Users** group using the instructions in the previous section, user and group accounts that are members of **BISM Users** will have sufficient permission on the workbook as well as the BI semantic model connection file, assuming the workbook uses inherited permissions.</span></span>  
  
##  <a name="next-steps"></a><a name="bkmk_next"></a> <span data-ttu-id="9ce51-156">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9ce51-156">Next Steps</span></span>  
 <span data-ttu-id="9ce51-157">Después de crear y proteger una conexión de modelo semántico de BI, podrá especificarla como origen de datos.</span><span class="sxs-lookup"><span data-stu-id="9ce51-157">After you create and secure a BI semantic model connection, you can specify it as a data source.</span></span> <span data-ttu-id="9ce51-158">Para obtener más información, vea [Usar una conexión de modelo semántico de BI en Excel o Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="9ce51-158">For more information, see [Use a BI Semantic Model Connection in Excel or Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ce51-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9ce51-159">See Also</span></span>  
 <span data-ttu-id="9ce51-160">[Conexión de modelo semántico de BI PowerPivot &#40;. Bism&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span><span class="sxs-lookup"><span data-stu-id="9ce51-160">[PowerPivot BI Semantic Model Connection &#40;.bism&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span></span>  
 <span data-ttu-id="9ce51-161">[Usar una conexión de modelo semántico de BI en Excel o Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="9ce51-161">[Use a BI Semantic Model Connection in Excel or Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md) </span></span>  
 [<span data-ttu-id="9ce51-162">Crear una conexión de modelo semántico de BI a una base de datos de modelo tabular</span><span class="sxs-lookup"><span data-stu-id="9ce51-162">Create a BI Semantic Model Connection to a Tabular Model Database</span></span>](create-a-bi-semantic-model-connection-to-a-tabular-model-database.md)  
  
  
