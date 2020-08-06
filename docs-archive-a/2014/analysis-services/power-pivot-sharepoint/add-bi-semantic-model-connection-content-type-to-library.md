---
title: Agregar un tipo de contenido de conexión de modelo semántico de BI a una biblioteca (PowerPivot para SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 145505ed-50bc-4528-912b-2a5cd2566011
author: minewiskan
ms.author: owend
ms.openlocfilehash: ecd40193b382aa692beeadd55ab8f9388c328620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676215"
---
# <a name="add-a-bi-semantic-model-connection-content-type-to-a-library-powerpivot-for-sharepoint"></a><span data-ttu-id="bb68d-102">Agregar un tipo de contenido de conexión de modelo semántico de BI a una biblioteca (PowerPivot para SharePoint)</span><span class="sxs-lookup"><span data-stu-id="bb68d-102">Add a BI Semantic Model Connection Content Type to a Library (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="bb68d-103">Se crea una conexión de modelo semántico de BI en SharePoint y proporciona redirección a los datos de modelo semántico de Business Intelligence en un libro de PowerPivot o una base de datos de modelo tabular de Analysis Services en un servidor de red.</span><span class="sxs-lookup"><span data-stu-id="bb68d-103">A BI semantic model connection is created in SharePoint and provides redirection to business intelligence semantic model data in a PowerPivot workbook or Analysis Services tabular model database on a network server.</span></span> <span data-ttu-id="bb68d-104">Para poder crear una conexión de modelo semántico de BI en SharePoint, debe ampliar una biblioteca de documentos para permitir la creación de un archivo .bism.</span><span class="sxs-lookup"><span data-stu-id="bb68d-104">Before you can create a BI semantic model connection in SharePoint, you must extend a document library to allow the creation of a .bism file.</span></span> <span data-ttu-id="bb68d-105">Solo es necesario realizar este paso una vez para cada biblioteca, pero tendrá que repetirla con cualquier biblioteca a partir de la que desee crear archivos .bism.</span><span class="sxs-lookup"><span data-stu-id="bb68d-105">This step only needs to be performed once for each library, but you will need to repeat it for any library from which you want to create .bism files.</span></span> <span data-ttu-id="bb68d-106">Es recomendable crear una biblioteca centralizada para almacenar los archivos .bism para poder administrar los permisos en un solo lugar.</span><span class="sxs-lookup"><span data-stu-id="bb68d-106">Best practices recommend that you create a centralized library for storing .bism files so that you can manage permissions in one place.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb68d-107">Si ya utiliza las bibliotecas de conexiones de datos de SharePoint, el tipo de contenido de conexión de modelo semántico de BI se agregará automáticamente a dicha plantilla de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="bb68d-107">If you already use SharePoint Data Connection Libraries, the BI Semantic Model Connection content type is automatically added to that library template.</span></span> <span data-ttu-id="bb68d-108">Puede omitir los pasos de esta sección si utiliza una biblioteca de conexiones de datos que ya le permita crear documentos de conexión de modelo semántico de BI.</span><span class="sxs-lookup"><span data-stu-id="bb68d-108">You can skip the steps in this section if you use a data connection library that already lets you create new BI semantic model connection documents.</span></span>  
  
##  <a name="add-the-content-type-to-a-document-library"></a><a name="bkmk_addtype"></a> <span data-ttu-id="bb68d-109">Agregar el tipo de contenido a una biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="bb68d-109">Add the content type to a document library</span></span>  
 <span data-ttu-id="bb68d-110">Para agregar y configurar un tipo de contenido, debe tener al menos el permiso Administrar listas.</span><span class="sxs-lookup"><span data-stu-id="bb68d-110">You must have at least the Manage Lists permission to add and configure a content type.</span></span> <span data-ttu-id="bb68d-111">Este permiso se integra en el nivel de permisos de diseño y superiores.</span><span class="sxs-lookup"><span data-stu-id="bb68d-111">This permission is built into the Design permission level and above.</span></span>  
  
 <span data-ttu-id="bb68d-112">El sitio que contiene la biblioteca de documentos debe tener la activación de características para PowerPivot para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bb68d-112">The site that contains the document library must have feature activation for PowerPivot for SharePoint.</span></span> <span data-ttu-id="bb68d-113">Para obtener más información, vea [activar la integración de características de PowerPivot para colecciones de sitios en administración central](activate-power-pivot-integration-for-site-collections-in-ca.md).</span><span class="sxs-lookup"><span data-stu-id="bb68d-113">For more information, see [Activate PowerPivot Feature Integration for Site Collections in Central Administration](activate-power-pivot-integration-for-site-collections-in-ca.md).</span></span>  
  
1.  <span data-ttu-id="bb68d-114">Abra la biblioteca de documentos para la que desee habilitar el tipo de contenido Conexión de modelo semántico de BI.</span><span class="sxs-lookup"><span data-stu-id="bb68d-114">Open the document library for which you want to enable the BI Semantic Model Connection content type.</span></span>  
  
2.  <span data-ttu-id="bb68d-115">En la cinta de opciones de SharePoint, en Herramientas de biblioteca, haga clic en **Biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="bb68d-115">On the SharePoint ribbon, in Library Tools, click **Library**.</span></span>  
  
3.  <span data-ttu-id="bb68d-116">Haga clic en **Configuración de la biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="bb68d-116">Click **Library Settings**.</span></span>  
  
4.  <span data-ttu-id="bb68d-117">En Configuración general, haga clic en **Configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="bb68d-117">In General Settings, click **Advanced settings**.</span></span>  
  
5.  <span data-ttu-id="bb68d-118">En Tipos de contenido, en la sección "¿Desea permitir la administración de tipos de contenido?"</span><span class="sxs-lookup"><span data-stu-id="bb68d-118">In Content Types, in the "Allow management of content types?"</span></span> <span data-ttu-id="bb68d-119">haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="bb68d-119">section, click **Yes**.</span></span>  
  
6.  <span data-ttu-id="bb68d-120">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb68d-120">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="bb68d-121">En la sección Tipos de contenido, haga clic en **Agregar a partir de tipos de contenido de sitio**.</span><span class="sxs-lookup"><span data-stu-id="bb68d-121">In the Content Types section, click **Add from existing site content types**.</span></span> <span data-ttu-id="bb68d-122">Si no ve esta página, regrese al sitio, haga clic en **Biblioteca** en Herramientas de biblioteca y, a continuación, haga clic en **Configuración de la biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="bb68d-122">If you do not see this page, go back to the site, click **Library** in Library Tools, and then click **Library Settings**.</span></span>  
  
8.  <span data-ttu-id="bb68d-123">En Tipos de contenido, haga clic en **Agregar a partir de tipos de contenido de sitio**.</span><span class="sxs-lookup"><span data-stu-id="bb68d-123">In Content Types, click **Add from existing site content types**.</span></span>  
  
9. <span data-ttu-id="bb68d-124">En Seleccionar tipos de contenido de sitio de:, seleccione **Business Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="bb68d-124">In Select site content types from:, select **Business Intelligence**.</span></span>  
  
10. <span data-ttu-id="bb68d-125">En Tipos de contenido de sitio disponibles, haga clic en **Archivo de conexión de modelo semántico de BI**y, a continuación, haga clic en **Agregar** para mover el tipo de contenido seleccionado a la lista Tipos de contenido que agregar.</span><span class="sxs-lookup"><span data-stu-id="bb68d-125">In Available Site Content Types, click **BI Semantic Model Connection File**, and then click **Add** to move the selected content type to the Content types to add list.</span></span>  
  
11. <span data-ttu-id="bb68d-126">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb68d-126">Click **OK**.</span></span>  
  
12. <span data-ttu-id="bb68d-127">Para comprobar que se ha agregado el tipo de contenido, vuelva a la biblioteca y haga clic en **Nuevo documento** en el área de documentos de la cinta de bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="bb68d-127">To verify you added the content type, go back to the library and click **New Document** on the Documents area of the library ribbon.</span></span> <span data-ttu-id="bb68d-128">En la lista Nuevos documentos, debería ver **Archivo de conexión de modelo semántico de BI** .</span><span class="sxs-lookup"><span data-stu-id="bb68d-128">You should see **BI Semantic Model Connection File** in the New Documents list.</span></span>  
  
     <span data-ttu-id="bb68d-129">![Submenú Nuevo documento en una biblioteca de SharePoint](../media/ssas-bismconnection-new.gif "Submenú Nuevo documento en una biblioteca de SharePoint")</span><span class="sxs-lookup"><span data-stu-id="bb68d-129">![New Document submenu in a SharePoint library](../media/ssas-bismconnection-new.gif "New Document submenu in a SharePoint library")</span></span>  
  
 <span data-ttu-id="bb68d-130">Después de habilitar el tipo de contenido de conexión de modelo semántico de BI para una biblioteca, puede crear una conexión que proporcione redirección a los datos de modelo semántico empresarial que se pueden usar en Excel o en los informes de [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb68d-130">After you enable the BI semantic model connection content type for a library, you can create a connection that provides redirection to business semantic model data that can be used by Excel or [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] reports.</span></span> <span data-ttu-id="bb68d-131">Elija uno de los siguientes vínculos para obtener más información acerca de este siguiente paso:</span><span class="sxs-lookup"><span data-stu-id="bb68d-131">Choose from the following links to learn more about this next step:</span></span>  
  
 [<span data-ttu-id="bb68d-132">Creación de una conexión de modelo semántico de BI a un libro de PowerPivot</span><span class="sxs-lookup"><span data-stu-id="bb68d-132">Create a BI Semantic Model Connection to a PowerPivot Workbook</span></span>](create-a-bi-semantic-model-connection-to-a-power-pivot-workbook.md)  
  
 [<span data-ttu-id="bb68d-133">Crear una conexión de modelo semántico de BI a una base de datos de modelo tabular</span><span class="sxs-lookup"><span data-stu-id="bb68d-133">Create a BI Semantic Model Connection to a Tabular Model Database</span></span>](create-a-bi-semantic-model-connection-to-a-tabular-model-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="bb68d-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bb68d-134">See Also</span></span>  
 <span data-ttu-id="bb68d-135">[Conexión de modelo semántico de BI PowerPivot &#40;. Bism&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span><span class="sxs-lookup"><span data-stu-id="bb68d-135">[PowerPivot BI Semantic Model Connection &#40;.bism&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span></span>  
 [<span data-ttu-id="bb68d-136">Usar una conexión de modelo semántico de BI en Excel o Reporting Services</span><span class="sxs-lookup"><span data-stu-id="bb68d-136">Use a BI Semantic Model Connection in Excel or Reporting Services</span></span>](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md)  
  
  
