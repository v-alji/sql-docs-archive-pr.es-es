---
title: Enlazar un informe o un modelo con un origen de datos compartido (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- shared data sources [Reporting Services]
- data sources [Reporting Services], shared
ms.assetid: 23cc15f2-2883-48e2-bc6c-fa0ab61a2e21
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 596caba042d476173b3c49d1ad18e79d0827fe89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745058"
---
# <a name="bind-a-report-or-model-to-a-shared-data-source-ssrs"></a><span data-ttu-id="39cb6-102">Enlazar un informe o un modelo con un origen de datos compartido (SSRS)</span><span class="sxs-lookup"><span data-stu-id="39cb6-102">Bind a Report or Model to a Shared Data Source (SSRS)</span></span>
  <span data-ttu-id="39cb6-103">En algunos casos (por ejemplo, al mover un informe o un modelo de un servidor de prueba a un servidor de producción), puede que desee guardar el archivo en el equipo local y, a continuación, cargarlo en otro servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="39cb6-103">In some situations, such as when you move a report or model from a test server to a production server, you might want to save the file to your local computer and then upload it to a different report server.</span></span> <span data-ttu-id="39cb6-104">Al cargar el informe o el modelo en el servidor nuevo, debe volver a enlazarlo con un origen de datos compartido almacenado en el servidor de informes nuevo.</span><span class="sxs-lookup"><span data-stu-id="39cb6-104">When you upload the report or model to the new server, you need to rebind it to a shared data source that is stored on the new report server.</span></span> <span data-ttu-id="39cb6-105">Si no vuelve a enlazar el informe o el modelo, no funcionará correctamente cuando se obtenga acceso a él desde el servidor de informes nuevo.</span><span class="sxs-lookup"><span data-stu-id="39cb6-105">If you don't rebind the report or model, it will not work correctly when accessed from the new report server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="39cb6-106">Para poder volver a enlazar un informe o un modelo con un origen de datos compartido, el origen de datos debe existir en el servidor de informes o en la biblioteca de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="39cb6-106">Before rebinding a report or model to a shared data source, the data source must already exist on the report server or SharePoint library.</span></span> <span data-ttu-id="39cb6-107">Para más información sobre orígenes de datos, vea [Crear, modificar y eliminar orígenes de datos compartidos &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="39cb6-107">For more information about data sources, see [Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span></span>  
  
### <a name="to-bind-a-report-or-model-to-a-shared-data-source-on-a-report-server-running-in-native-mode"></a><span data-ttu-id="39cb6-108">Para enlazar un informe o un modelo con un origen de datos compartido en un servidor de informes que se ejecuta en modo nativo</span><span class="sxs-lookup"><span data-stu-id="39cb6-108">To bind a report or model to a shared data source on a report server running in native mode</span></span>  
  
1.  <span data-ttu-id="39cb6-109">En el **Administrador de informes**, haga clic en el nombre del informe o el modelo cargado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="39cb6-109">In **Report Manager**, click the name of the report or model that you uploaded to the server.</span></span>  
  
     <span data-ttu-id="39cb6-110">Se abre la pestaña Propiedades.</span><span class="sxs-lookup"><span data-stu-id="39cb6-110">The Properties tab opens.</span></span>  
  
2.  <span data-ttu-id="39cb6-111">Haga clic en **Orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="39cb6-111">Click **Data Sources**.</span></span>  
  
3.  <span data-ttu-id="39cb6-112">Haga clic en **Examinar**y, a continuación, navegue hasta el origen de datos con el que desea enlazar el informe o el modelo.</span><span class="sxs-lookup"><span data-stu-id="39cb6-112">Click **Browse**, and then navigate to the data source to which you want to bind the report or model.</span></span>  
  
4.  <span data-ttu-id="39cb6-113">Seleccione el origen de datos y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="39cb6-113">Select the data source and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="39cb6-114">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="39cb6-114">Click **Apply**.</span></span>  
  
     <span data-ttu-id="39cb6-115">El informe o el modelo ya está enlazado con el origen de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="39cb6-115">The report or model is now bound to the data source that you selected.</span></span>  
  
### <a name="to-bind-a-report-or-model-to-a-shared-data-source-on-a-report-server-running-in-sharepoint-integrated-mode"></a><span data-ttu-id="39cb6-116">Para enlazar un informe o un modelo con un origen de datos compartido en un servidor de informes que se ejecuta en el modo integrado de SharePoint</span><span class="sxs-lookup"><span data-stu-id="39cb6-116">To bind a report or model to a shared data source on a report server running in SharePoint integrated mode</span></span>  
  
1.  <span data-ttu-id="39cb6-117">Si la biblioteca aún no está abierta, haga clic en su nombre en la barra Inicio rápido.</span><span class="sxs-lookup"><span data-stu-id="39cb6-117">If the library is not already open, click its name on the Quick Launch bar.</span></span> <span data-ttu-id="39cb6-118">Si no aparece el nombre de la biblioteca, haga clic en **Ver todo el contenido del sitio**y, a continuación, haga clic en el nombre de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="39cb6-118">If the name of your library does not appear, click **View All Site Content**, and then click the name of your library.</span></span>  
  
2.  <span data-ttu-id="39cb6-119">Seleccione el informe o el modelo y haga clic en la flecha hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="39cb6-119">Point to the report or model and click the down arrow.</span></span>  
  
3.  <span data-ttu-id="39cb6-120">Haga clic en **Administrar orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="39cb6-120">Click **Manage Data Sources**.</span></span>  
  
4.  <span data-ttu-id="39cb6-121">Haga clic en **dataSource1**.</span><span class="sxs-lookup"><span data-stu-id="39cb6-121">Click **dataSource1**.</span></span>  
  
5.  <span data-ttu-id="39cb6-122">En el área **Tipo de conexión** , compruebe si está seleccionado **Origen de datos compartido** .</span><span class="sxs-lookup"><span data-stu-id="39cb6-122">In the **Connection Type** area, verify that **Shared data source** is selected.</span></span>  
  
6.  <span data-ttu-id="39cb6-123">En el área **Vínculo a origen de datos**, haga clic en el botón de puntos suspensivos (...).</span><span class="sxs-lookup"><span data-stu-id="39cb6-123">In the **Data Source Link** area, click the ellipsis (...) button.</span></span>  
  
7.  <span data-ttu-id="39cb6-124">Busque el origen de datos que desee usar.</span><span class="sxs-lookup"><span data-stu-id="39cb6-124">Locate the data source you want to use.</span></span>  
  
8.  <span data-ttu-id="39cb6-125">Seleccione el origen de datos y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="39cb6-125">Select the data source and **click OK**.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
10. <span data-ttu-id="39cb6-126">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="39cb6-126">Click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39cb6-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="39cb6-127">See Also</span></span>  
 <span data-ttu-id="39cb6-128">[Cargar un archivo o informe &#40;Administrador de informes&#41;](../reports/upload-a-file-or-report-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="39cb6-128">[Upload a File or Report &#40;Report Manager&#41;](../reports/upload-a-file-or-report-report-manager.md) </span></span>  
 <span data-ttu-id="39cb6-129">[Cargar documentos en una biblioteca de SharePoint &#40;Reporting Services en modo de SharePoint&#41;](../upload-documents-to-a-sharepoint-library-reporting-services-in-sharepoint-mode.md) </span><span class="sxs-lookup"><span data-stu-id="39cb6-129">[Upload Documents to a SharePoint Library &#40;Reporting Services in SharePoint Mode&#41;](../upload-documents-to-a-sharepoint-library-reporting-services-in-sharepoint-mode.md) </span></span>  
 <span data-ttu-id="39cb6-130">[Crear y administrar orígenes de datos compartidos &#40;Reporting Services en el modo integrado de SharePoint&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md) </span><span class="sxs-lookup"><span data-stu-id="39cb6-130">[Create and Manage Shared Data Sources &#40;Reporting Services in SharePoint Integrated Mode&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md) </span></span>  
 <span data-ttu-id="39cb6-131">[Crear, eliminar o modificar un origen de datos compartido &#40;Administrador de informes&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="39cb6-131">[Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span></span>  
 <span data-ttu-id="39cb6-132">[Conexiones de datos, orígenes de datos y cadenas de conexión en Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="39cb6-132">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="39cb6-133">Orígenes de datos admitidos por Reporting Services &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="39cb6-133">Data Sources Supported by Reporting Services &#40;SSRS&#41;</span></span>](../create-deploy-and-manage-mobile-and-paginated-reports.md)  
  
  
