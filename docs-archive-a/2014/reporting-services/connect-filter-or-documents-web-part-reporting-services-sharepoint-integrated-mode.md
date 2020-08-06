---
title: Conectar el elemento Web filtro o documentos (Reporting Services en el modo integrado de SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Filter Web Part [Reporting Services]
- SharePoint integration [Reporting Services], Web Parts
- Report Viewer Web Part [Reporting Services]
- Documents Web Part [Reporting Services]
ms.assetid: 6a303135-c0ef-44cd-a423-1cea8df3dcf3
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5ea7b9f9aba128052ae6ac7f05ef40517eb50e6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670330"
---
# <a name="connect-filter-or-documents-web-part-reporting-services-in-sharepoint-integrated-mode"></a><span data-ttu-id="a1579-102">Conectar un elemento web Filtro o Documentos (Reporting Services en el modo integrado de SharePoint)</span><span class="sxs-lookup"><span data-stu-id="a1579-102">Connect Filter or Documents Web Part (Reporting Services in SharePoint Integrated Mode)</span></span>
  <span data-ttu-id="a1579-103">Si utiliza un producto de SharePoint, puede crear un panel o una página de elementos web que incluya un elemento web Filtro o un elemento web Documentos, y un elemento web Visor de informes.</span><span class="sxs-lookup"><span data-stu-id="a1579-103">If you are using a SharePoint product, you can create a dashboard or Web Part Page that includes a Filter Web Part or Documents Web part and a Report Viewer Web Part.</span></span> <span data-ttu-id="a1579-104">Las versiones admitidas son [!INCLUDE[SPF2010](../includes/spf2010-md.md)] o [!INCLUDE[SPS2010](../includes/sps2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1579-104">Supported versions are [!INCLUDE[SPF2010](../includes/spf2010-md.md)] or [!INCLUDE[SPS2010](../includes/sps2010-md.md)].</span></span> <span data-ttu-id="a1579-105">También se admiten [!INCLUDE[winSPServ3](../includes/winspserv3-md.md)] u [!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2007.</span><span class="sxs-lookup"><span data-stu-id="a1579-105">Also supported are [!INCLUDE[winSPServ3](../includes/winspserv3-md.md)] or [!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2007.</span></span> <span data-ttu-id="a1579-106">Mediante la conexión de un elemento web Filtro, los usuarios que seleccionan valores de filtro en un elemento web Filtro pueden enviar el valor a un informe con parámetros en la misma página.</span><span class="sxs-lookup"><span data-stu-id="a1579-106">By connecting a Filter Web Part, users who select filter values in a Filter Web Part can send the value to a parameterized report on the same page.</span></span> <span data-ttu-id="a1579-107">Mediante la conexión de un elemento web Documentos, los usuarios que hacen clic en informes en la biblioteca de documentos pueden ver el informe en un elemento web Visor de informes adyacente.</span><span class="sxs-lookup"><span data-stu-id="a1579-107">By connecting a Documents Web Part, users who click on reports in the Documents library can view the report in an adjacent Report Viewer Web Part.</span></span>  
  
 <span data-ttu-id="a1579-108">El elemento web Filtro sirve para enviar valores a uno o varios parámetros de un informe.</span><span class="sxs-lookup"><span data-stu-id="a1579-108">The Filter Web Part is used to send values to one or more parameters on a report.</span></span> <span data-ttu-id="a1579-109">Para utilizar un elemento web Filtro, el informe debe tener parámetros definidos que sean compatibles con los valores, tipo de datos y formato que haya enviado el elemento web.</span><span class="sxs-lookup"><span data-stu-id="a1579-109">To use a Filter Web Part, the report must have parameters defined for it that are compatible with the values, data type, and format sent by the Web Part.</span></span>  
  
 <span data-ttu-id="a1579-110">El elemento web Documentos está asociado a la biblioteca de documentos del sitio principal.</span><span class="sxs-lookup"><span data-stu-id="a1579-110">The Documents Web Part is associated with the Documents library of the Home site.</span></span> <span data-ttu-id="a1579-111">Para ver, agregar o quitar elementos de la biblioteca de documentos, haga clic en **Ver todo el contenido del sitio**.</span><span class="sxs-lookup"><span data-stu-id="a1579-111">To view, add, or remove items from the Documents library, click **View All Site Content**.</span></span> <span data-ttu-id="a1579-112">En Bibliotecas, haga clic en **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="a1579-112">In Libraries, click **Documents**.</span></span> <span data-ttu-id="a1579-113">Puede utilizar los menús **Nuevo**, **Cargar**y **Acciones** para administrar los elementos de la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="a1579-113">You can use the **New**, **Upload**, and **Actions** menu to manage the items in the Documents library.</span></span>  
  
### <a name="to-connect-a-filter-web-part"></a><span data-ttu-id="a1579-114">Para conectar un elemento web Filtro</span><span class="sxs-lookup"><span data-stu-id="a1579-114">To connect a Filter Web Part</span></span>  
  
1.  <span data-ttu-id="a1579-115">Abra o cree un panel o una página de elementos web.</span><span class="sxs-lookup"><span data-stu-id="a1579-115">Open or create the Web Part page or dashboard.</span></span>  
  
2.  <span data-ttu-id="a1579-116">En el menú **Acciones del sitio** , haga clic en **Editar página**.</span><span class="sxs-lookup"><span data-stu-id="a1579-116">On the **Site Actions** menu, click **Edit Page**.</span></span>  
  
3.  <span data-ttu-id="a1579-117">Haga clic en **Agregar un elemento Web**.</span><span class="sxs-lookup"><span data-stu-id="a1579-117">Click **Add a Web Part**.</span></span>  
  
4.  <span data-ttu-id="a1579-118">En **todos los elementos Web**, en la categoría **varios** , seleccione **SQL Server Reporting Services visor de informes**.</span><span class="sxs-lookup"><span data-stu-id="a1579-118">In **All Web Parts**, in the **Miscellaneous** category, select **SQL Server Reporting Services Report Viewer**.</span></span>  
  
5.  <span data-ttu-id="a1579-119">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a1579-119">Click **Add**.</span></span> <span data-ttu-id="a1579-120">El elemento web se agregará a la parte superior de la zona.</span><span class="sxs-lookup"><span data-stu-id="a1579-120">The Web Part is added at the top of the zone.</span></span>  
  
6.  <span data-ttu-id="a1579-121">En otra zona de la misma página o panel de elementos Web, haga clic en **Agregar un elemento Web**.</span><span class="sxs-lookup"><span data-stu-id="a1579-121">On another zone in the same Web Part page or dashboard, click **Add a Web Part**.</span></span>  
  
7.  <span data-ttu-id="a1579-122">En **todos los elementos Web**, en la sección **filtros** , seleccione un elemento Web.</span><span class="sxs-lookup"><span data-stu-id="a1579-122">In **All Web Parts**, in the **Filters** section, select a Web Part.</span></span>  
  
8.  <span data-ttu-id="a1579-123">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a1579-123">Click **Add**.</span></span> <span data-ttu-id="a1579-124">El elemento web se agregará a la parte superior de la zona.</span><span class="sxs-lookup"><span data-stu-id="a1579-124">The Web Part is added at the top of the zone.</span></span>  
  
9. <span data-ttu-id="a1579-125">En la zona que contiene el elemento web, haga clic en el menú **Edición** del elemento web, seleccione **Conexiones**, **Enviar valores de filtro a**y, después, elija **Visor de informes** - *nombre de informe*.</span><span class="sxs-lookup"><span data-stu-id="a1579-125">In the zone that contains the Web Part, click the Web Part **edit** menu, point to **Connections**, point to **Send Filter Values To**, and then select **Report Viewer** - *report name*.</span></span>  
  
10. <span data-ttu-id="a1579-126">Proteja sus cambios y guarde la página.</span><span class="sxs-lookup"><span data-stu-id="a1579-126">Check in your changes and save the page.</span></span>  
  
### <a name="to-connect-a-documents-web-part"></a><span data-ttu-id="a1579-127">Para conectar un elemento web Documentos</span><span class="sxs-lookup"><span data-stu-id="a1579-127">To connect a Documents Web Part</span></span>  
  
1.  <span data-ttu-id="a1579-128">Abra o cree un panel o una página de elementos web.</span><span class="sxs-lookup"><span data-stu-id="a1579-128">Open or create the Web Part page or dashboard.</span></span>  
  
2.  <span data-ttu-id="a1579-129">En el menú **Acciones del sitio** , haga clic en **Editar página**.</span><span class="sxs-lookup"><span data-stu-id="a1579-129">On the **Site Actions** menu, click **Edit Page**.</span></span>  
  
3.  <span data-ttu-id="a1579-130">Haga clic en **Agregar un elemento Web**.</span><span class="sxs-lookup"><span data-stu-id="a1579-130">Click **Add a Web Part**.</span></span>  
  
4.  <span data-ttu-id="a1579-131">En **Todos los elementos web**, en la sección **Listas y bibliotecas** , seleccione **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="a1579-131">In **All Web Parts**, in the **Lists and Library** section, select **Documents.**</span></span>  
  
5.  <span data-ttu-id="a1579-132">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a1579-132">Click **Add**.</span></span> <span data-ttu-id="a1579-133">El elemento web se agregará a la parte superior de la zona.</span><span class="sxs-lookup"><span data-stu-id="a1579-133">The Web Part is added at the top of the zone.</span></span>  
  
6.  <span data-ttu-id="a1579-134">Haga clic en **Aplicar** en la parte inferior del panel de herramientas y, a continuación, haga clic en **Aceptar** para cerrar el panel.</span><span class="sxs-lookup"><span data-stu-id="a1579-134">Click **Apply** at the bottom of the tool pane, and then click **OK** to close the pane.</span></span>  
  
7.  <span data-ttu-id="a1579-135">En otra zona de la misma página o panel de elementos Web, haga clic en **Agregar un elemento Web**.</span><span class="sxs-lookup"><span data-stu-id="a1579-135">On another zone in the same Web Part page or dashboard, click **Add a Web Part**.</span></span>  
  
8.  <span data-ttu-id="a1579-136">En **Todos los elementos web**, en la categoría **Varios** , seleccione **Visor de informes de SQL Reporting Services.**</span><span class="sxs-lookup"><span data-stu-id="a1579-136">In **All Web Parts**, in the **Miscellaneous** category, select **SQL Server Reporting Services Report Viewer.**</span></span>  
  
9. <span data-ttu-id="a1579-137">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a1579-137">Click **Add**.</span></span> <span data-ttu-id="a1579-138">El elemento web se agregará a la parte superior de la zona.</span><span class="sxs-lookup"><span data-stu-id="a1579-138">The Web Part is added at the top of the zone.</span></span>  
  
10. <span data-ttu-id="a1579-139">En la zona que contiene el elemento web, haga clic en el menú **Edición** del elemento web, seleccione **Conexiones**, **Ruta de acceso del sistema de archivos al archivo de definición del informe**y **Documentos**.</span><span class="sxs-lookup"><span data-stu-id="a1579-139">In the zone that contains the Web Part, click the Web Part **edit** menu, point to **Connections**, point to **Get report definitions from**, and then select **Documents**.</span></span>  
  
11. <span data-ttu-id="a1579-140">Proteja sus cambios y guarde la página.</span><span class="sxs-lookup"><span data-stu-id="a1579-140">Check in your changes and save the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1579-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a1579-141">See Also</span></span>  
 <span data-ttu-id="a1579-142">[Agregar el elemento Web visor de informes a una página web &#40;Reporting Services en el modo integrado de SharePoint&#41;](report-server-sharepoint/add-reporting-services-content-types-to-a-sharepoint-library.md) </span><span class="sxs-lookup"><span data-stu-id="a1579-142">[Add the Report Viewer Web Part to a Web Page &#40;Reporting Services in SharePoint Integrated Mode&#41;](report-server-sharepoint/add-reporting-services-content-types-to-a-sharepoint-library.md) </span></span>  
 <span data-ttu-id="a1579-143">[Elemento Web visor de informes en un sitio de SharePoint](../../2014/reporting-services/report-viewer-web-part-on-a-sharepoint-site.md) </span><span class="sxs-lookup"><span data-stu-id="a1579-143">[Report Viewer Web Part on a SharePoint Site](../../2014/reporting-services/report-viewer-web-part-on-a-sharepoint-site.md) </span></span>  
 [<span data-ttu-id="a1579-144">Personalizar el elemento web Visor de informes</span><span class="sxs-lookup"><span data-stu-id="a1579-144">Customize the Report Viewer Web Part</span></span>](../../2014/reporting-services/customize-the-report-viewer-web-part.md)  
  
  
